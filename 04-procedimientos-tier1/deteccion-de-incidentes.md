
# 🔍 Detección de Incidentes en un SOC

Este diagrama muestra un flujo típico de **detección y análisis de incidentes** en un Centro de Operaciones de Seguridad (SOC).  
Incluye la identificación de alertas desde distintas fuentes (SIEM, EDR, logs), el análisis inicial por un analista de nivel 1, la escalación a niveles superiores si es necesario, notificaciones a áreas afectadas y el cierre de incidentes confirmados o falsos positivos.  

Se refleja también el enriquecimiento con inteligencia de amenazas (Threat Intelligence) y la documentación en plataformas de gestión de incidentes para asegurar trazabilidad y aprendizaje continuo.

```mermaid
flowchart TD
    subgraph Fuentes
        SIEM[SIEM / Correlación de eventos]
        EDR[EDR / Endpoint Detection]
        Logs[Registros de aplicaciones y red]
    end

    subgraph Analista_L1["Analista SOC Tier 1"]
        A1[Recibe alerta]
        A2[Revisión inicial]
        A3{Determina acción}
    end

    subgraph Escalacion["Escalación y Gestión"]
        T2[Escala a Tier 2 si es complejo]
        Notifica[Notifica a área afectada]
        Cierra[Falso positivo / cierre]
        Documenta[Documenta en TheHive / sistema de gestión]
    end

    subgraph Enriquecimiento["Threat Intelligence"]
        MISP[MISP / IOC Lookup]
    end

    %% Flujo principal
    SIEM --> A1
    EDR --> A1
    Logs --> A1
    A1 --> A2
    A2 --> A3
    A3 -->|Escalar| T2
    A3 -->|Notificar| Notifica
    A3 -->|Falso positivo| Cierra
    T2 --> Documenta
    Notifica --> Documenta
    Cierra --> Documenta
    A2 --> MISP
    MISP --> A2

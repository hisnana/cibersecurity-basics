# 🕵️‍♂️ Proceso de Investigación de una Alerta (con ejemplos y herramientas)

Este diagrama muestra el flujo típico que sigue un analista de SOC para investigar una alerta, incluyendo **qué fijarse** y **herramientas útiles** en cada paso.  
Se incluye la posibilidad de **escalar, notificar al cliente o cerrar como falso positivo** según el análisis.

```mermaid
flowchart TD
    %% Fuentes de alerta
    SIEM[SIEM / Correlación de eventos] --> Analista[Recibe alerta]
    EDR[EDR / Endpoint Detection] --> Analista
    Logs[Logs de red y aplicaciones] --> Analista

    %% Investigación inicial
    Analista --> Recolectar[Recolecta información]
    Recolectar --> Fijarse[Fijarse en IP, usuario, endpoint, timestamp]
    Fijarse --> Herramientas1[Kibana, Splunk, ELK, Wireshark]

    Recolectar --> Enriquecer[Enriquecer con Threat Intelligence]
    Enriquecer --> Herramientas2[MISP, VirusTotal, OpenCTI]

    Enriquecer --> Analizar[Analiza contexto y criticidad]
    Analizar --> Herramientas3[MITRE ATT&CK, SIEM dashboards, Python scripts]

    %% Decisión principal
    Analizar --> Decision{¿Es amenaza real?}
    Decision -->|Sí| Escalar[Escala a Tier 2 / equipo especializado]
    Decision -->|Notificar| Notificar[Notifica al cliente / área afectada]
    Decision -->|No| Cerrar[Falso positivo / cierre]

    %% Acciones tras escalado
    Escalar --> Mitigar[Implementa medidas de mitigación o contención]
    Mitigar --> Documentar[Documenta hallazgos en TheHive / sistema de gestión]

    %% Acciones tras notificación
    Notificar --> Documentar

    %% Acciones tras cierre
    Cerrar --> Documentar

    %% Feedback para mejorar reglas
    Documentar --> SIEM
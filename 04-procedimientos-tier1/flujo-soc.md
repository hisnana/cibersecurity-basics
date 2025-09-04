## Análisis de alerta en SIEM

Paso a paso para revisar y escalar una alerta en el SIEM.

```mermaid
flowchart TD
    A[SIEM detecta alerta] --> B[Analista revisa evento]
    B --> C{Necesita escalar?}
    C -->|Sí| D[Escala a Tier 2]
    C -->|No| E[Cierra como falso positivo]


# 🖼️ Flujo SOC Básico

Este diagrama ilustra, de forma simplificada, el ciclo típico de gestión de una alerta en un Centro de Operaciones de Seguridad (SOC).  
Muestra cómo una alerta detectada en el SIEM se procesa a través de la automatización (SOAR), se enriquece con inteligencia de amenazas (MISP), se gestiona como caso en TheHive y finalmente es revisada por el analista SOC, quien retroalimenta el sistema con nueva información.

```mermaid
flowchart TD
    SIEM["SIEM (Correlación de eventos)"] -->|Alerta generada| XSOAR["SOAR (Automatización)"]
    XSOAR -->|Consulta de IOCs| MISP["MISP (Threat Intelligence)"]
    XSOAR -->|Crea caso| TheHive["TheHive (Gestión de incidentes)"]
    TheHive -->|Asignación y análisis| Analista["Analista SOC"]
    Analista -->|Feedback de investigación| MISP

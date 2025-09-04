## Análisis de alerta en SIEM

Paso a paso para revisar y escalar una alerta en el SIEM.

```mermaid
flowchart TD
    A[SIEM detecta alerta] --> B[Analista revisa evento]
    B --> C{Necesita escalar?}
    C -->|Sí| D[Escala a Tier 2]
    C -->|No| E[Cierra como falso positivo]

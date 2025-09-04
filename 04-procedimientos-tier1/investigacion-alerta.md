# 🕵️‍♂️ Proceso de Investigación de una Alerta (con ejemplos y herramientas)

Este diagrama muestra el flujo habitual que sigue un analista de SOC para investigar una alerta, incluyendo **qué fijarse** y **herramientas útiles** en cada paso.

```mermaid
flowchart TD
    %% Fuentes de alerta
    SIEM[SIEM / Correlación de eventos] --> Analista[Analista recibe alerta\n(Ej: Evento anómalo de firewall, alerta EDR)]
    EDR[EDR / Endpoint Detection] --> Analista
    Logs[Logs de red y aplicaciones] --> Analista

    %% Investigación inicial
    Analista --> Recolectar[Recolecta información\n- Fijarse en IP, usuario, endpoint, timestamp\n- Herramientas: Kibana, Splunk, ELK, Wireshark]
    Recolectar --> Enriquecer[Enriquecer con Threat Intelligence\n- Verificar IOC, reputación IP, dominios sospechosos\n- Herramientas: MISP, VirusTotal, OpenCTI]

    %% Análisis y decisión
    Enriquecer --> Analizar[Analiza contexto y criticidad\n- Tipo de amenaza, impacto potencial, patrones similares\n- Herramientas: MITRE ATT&CK, SIEM dashboards, Python scripts]
    Analizar --> Decision{¿Es amenaza real?}
    Decision -->|Sí| Escalar[Escala a Tier 2 / equipo especializado\n- Adjuntar evidencia y contexto\n- Herramientas: TheHive, Jira, Confluence]
    Decision -->|No| Cerrar[Cierra como falso positivo\n- Documentar razones, ajustar reglas de detección\n- Herramientas: SIEM, repositorios internos]

    %% Acciones tras escalado
    Escalar --> Mitigar[Implementa medidas de mitigación o contención\n- Bloqueo de IP, cuarentena de endpoint, cambio de credenciales\n- Herramientas: Firewall, EDR, scripts de automatización]
    Mitigar --> Documentar[Documenta hallazgos en TheHive / sistema de gestión\n- Adjuntar logs, screenshots, IOC y recomendaciones]

    %% Acciones tras cierre
    Cerrar --> Documentar

    %% Feedback para mejorar reglas
    Documentar --> SIEM

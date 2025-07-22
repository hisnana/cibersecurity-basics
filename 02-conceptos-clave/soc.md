## ¿Qué es un SOC (Security Operations Center)?

Un **SOC** (Centro de Operaciones de Seguridad) es un equipo centralizado, compuesto por personas, procesos y tecnología, que **monitorea, detecta, analiza y responde a incidentes de ciberseguridad** en tiempo real.

Su objetivo principal es **proteger la infraestructura de TI** de una organización frente a amenazas internas y externas.

---

## Estructura típica de un SOC

Un SOC suele estar organizado en **niveles o capas (tiers)** con funciones específicas:

### 🧑‍💻 Nivel 1 - Analistas de monitoreo (Tier 1)
- Monitorean alertas en tiempo real (SIEM, EDR, etc.).
- Realizan triage inicial: determinan si una alerta es real o un falso positivo.
- Escalan incidentes si es necesario.

### 🕵️ Nivel 2 - Analistas de investigación (Tier 2)
- Analizan incidentes confirmados con mayor profundidad.
- Correlacionan datos de múltiples fuentes (XDR, logs, tráfico de red).
- Realizan contención manual (bloqueo de IPs, aislamiento de equipos).

### 🧠 Nivel 3 - Analistas de amenazas / Threat Hunters (Tier 3)
- Proactivos: buscan amenazas que no hayan generado alertas.
- Usan inteligencia de amenazas (Threat Intelligence).
- Mejoran reglas y detección del SIEM o EDR.

### 🛠️ Ingenieros de seguridad
- Mantienen las herramientas del SOC (SIEM, SOAR, firewalls, etc.).
- Automatizan procesos (SOAR).
- Ayudan a integrar nuevas fuentes de datos.

### 👨‍✈️ Jefe del SOC / Coordinador
- Supervisa al equipo y coordina la respuesta a incidentes graves.
- Informa al CISO (Chief Information Security Officer).
- Define procedimientos y asegura cumplimiento de normativas.

---

## Herramientas típicas en un SOC

- **SIEM** (ej. Splunk, QRadar, Chronicle, Sentinel, Elastic)
- **EDR/XDR** (ej. CrowdStrike, Microsoft Defender XDR)
- **SOAR** (ej. Cortex XSOAR, Splunk SOAR, Chronicle SOAR)
- **Firewall / IPS / IDS**
- **Sistemas de ticketing** (ej. ServiceNow, Jira)
- **Threat Intelligence Platforms**

---

Un SOC puede ser **interno**, **externo (outsourced/MSSP)** o **híbrido**, dependiendo del tamaño y necesidades de la organización.

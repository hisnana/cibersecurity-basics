## ¿Qué es un SOC (Security Operations Center)?

Un **SOC** (Centro de Operaciones de Seguridad) es un equipo centralizado, compuesto por personas, procesos y tecnología, que **monitorea, detecta, analiza y responde a incidentes de ciberseguridad** en tiempo real.

Su objetivo principal es **proteger la infraestructura de TI** de una organización frente a amenazas internas y externas.

---

## Estructura típica de un SOC

Un SOC suele estar organizado en **niveles o capas (tiers)** con funciones específicas:

# Roles comunes en un SOC (Centro de Operaciones de Seguridad)

## 1. Analista de Seguridad - Nivel 1 (Tier 1)
- Monitorea alertas de seguridad y eventos.
- Realiza la primera clasificación y escalado de incidentes.
- Ejecuta análisis básicos y confirma falsos positivos.

## 2. Analista de Seguridad - Nivel 2 (Tier 2) / Equipo de Correlación y Threat Modeling
- Investiga incidentes complejos.
- Realiza análisis forense y respuesta a incidentes.
- Correlaciona datos de múltiples fuentes para identificar amenazas.
- Desarrolla y mantiene modelos de amenazas (threat modeling) para anticipar posibles vectores de ataque.
- Crea y ajusta reglas de correlación para mejorar la detección de incidentes sofisticados.

## 3. Analista de Seguridad - Nivel 3 (Tier 3) / Experto en Incidentes
- Maneja incidentes críticos y avanzados.
- Diseña y mejora procesos de detección y respuesta.
- Colabora en la definición de estrategias de seguridad.

## 4. Ingeniero de Seguridad / Arquitecto SOC
- Diseña y mantiene la infraestructura del SOC.
- Configura y optimiza herramientas de seguridad (SIEM, IDS/IPS).
- Implementa reglas y casos de uso para detección.

## 5. Gerente o Líder del SOC
- Supervisa operaciones y personal del SOC.
- Coordina la comunicación con otras áreas y la alta dirección.
- Define políticas, procesos y métricas del SOC.

## 6. Ciberinteligencia (Cyber Intelligence)
- Recopila y analiza información sobre amenazas actuales y emergentes.
- Proporciona contexto para priorizar y enriquecer alertas.
- Trabaja con equipos de respuesta para anticipar ataques.

## 7. Desarrollador / Ingeniero DevOps SOAR
- Diseña y mantiene automatizaciones y orquestaciones en plataformas SOAR.
- Integra herramientas de seguridad y automatiza flujos de trabajo.
- Optimiza la eficiencia operativa del SOC mediante desarrollo y despliegue continuo.

## 8. Especialista en Forense Digital
- Realiza análisis detallados de incidentes y recuperación de evidencia.
- Apoya en investigaciones internas y cumplimiento legal.

## 9. Especialista en Gestión de Vulnerabilidades
- Escanea y evalúa vulnerabilidades en sistemas y aplicaciones.
- Prioriza remediaciones y comunica riesgos a equipos técnicos.

## 10. Especialista en Cumplimiento y Auditoría
- Asegura que el SOC cumpla con normativas y estándares.
- Realiza auditorías y reporta hallazgos.

---

## Resumen en tabla

| Rol                         | Descripción breve                                                                                   |
|-----------------------------|--------------------------------------------------------------------------------------------------|
| Analista de Seguridad Tier 1| Monitoreo y primer análisis de alertas                                                           |
| Analista de Seguridad Tier 2| Investigación, análisis profundo, correlación de datos y desarrollo de modelos de amenazas       |
| Analista de Seguridad Tier 3| Manejo de incidentes críticos y estrategia                                                       |
| Ingeniero / Arquitecto SOC  | Diseño y mantenimiento de infraestructura y herramientas                                        |
| Gerente / Líder SOC         | Gestión del equipo y estrategia global del SOC                                                   |
| Ciberinteligencia           | Análisis y provisión de inteligencia sobre amenazas                                             |
| DevOps / Desarrollador SOAR | Automatización y orquestación de procesos de seguridad                                          |
| Forense Digital             | Análisis de incidentes y recuperación de evidencia                                              |
| Gestión de Vulnerabilidades | Evaluación y priorización de vulnerabilidades                                                    |
| Cumplimiento y Auditoría    | Aseguramiento de cumplimiento normativo y auditorías                                             |





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

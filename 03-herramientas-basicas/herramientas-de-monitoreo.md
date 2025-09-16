# Herramientas en SOC por Rol y Tarea (Actualizado)

---

## Tier 1 - Monitorización y Alerta

### 1. Recepción y análisis inicial de alertas

- **Splunk**
  - Plataforma SIEM que recolecta y correlaciona logs, genera alertas y dashboards para monitorización en tiempo real.

- **Elastic SIEM (Elastic Stack)**
  - Sistema open source para ingestión, búsqueda y análisis de logs con visualizaciones y alertas configurables.

- **IBM QRadar**
  - SIEM empresarial con capacidades avanzadas de correlación y análisis de eventos.

- **TheHive**
  - Plataforma open source para gestión y análisis colaborativo de incidentes y alertas, con integración a fuentes SIEM.

### 2. Gestión de incidentes y tickets

- **ServiceNow**
  - Plataforma ITSM para gestión y seguimiento de tickets, con integración a sistemas SOC para escalar incidentes.

- **JIRA**
  - Sistema de gestión de proyectos que permite crear y administrar tareas e incidencias dentro del SOC.

- **TheHive**
  - Además de análisis, facilita la gestión de casos (case management) integrando múltiples fuentes y equipos.

### 3. Validación básica de alertas

- **Consola Cisco ASA**
  - Interfaz para revisar logs y tráfico en firewalls Cisco, útil para confirmar alertas relacionadas con la red.

- **CrowdStrike Falcon (visión básica)**
  - Plataforma EDR que ofrece visibilidad inicial sobre eventos sospechosos en endpoints.

- **VirusTotal**
  - Servicio en línea para analizar archivos o URLs sospechosos y verificar si son maliciosos.

- **VirusTotal Enterprise**
  - Versión avanzada con APIs para integrarse y automatizar análisis de archivos y URLs sospechosas.

### 4. Comunicación interna y colaboración

- **Slack**
  - Plataforma de mensajería para comunicación rápida entre analistas y equipos.

- **Microsoft Teams**
  - Herramienta colaborativa para chats, videollamadas y coordinación en tiempo real.

---

## Tier 2 - Investigación y Respuesta Avanzada

### 1. Análisis y enriquecimiento avanzado

- **Splunk Enterprise Security**
  - Versión avanzada de Splunk con funcionalidades específicas para análisis profundo, hunting y generación de reportes.

- **CrowdStrike Falcon**
  - Plataforma EDR/XDR que permite investigar comportamiento avanzado, realizar búsquedas históricas y tomar acciones remotas.

- **VirusTotal Enterprise**
  - Versión avanzada para análisis profundo de malware con sandboxing y enriquecimiento contextual.

- **MISP (Malware Information Sharing Platform)**
  - Plataforma open source para compartir inteligencia y enriquecer datos sobre amenazas.

- **Threat Intelligence Platforms (TIPs)**
  - Ej: Recorded Future, Anomali — para recopilación, análisis y priorización de inteligencia.

### 2. Análisis forense y malware

- **FTK (Forensic Toolkit)**
  - Herramienta especializada para análisis forense digital y recuperación de evidencia en discos y memorias.

- **EnCase**
  - Plataforma forense para adquisición, análisis y preservación de datos digitales en investigaciones.

- **Cuckoo Sandbox**
  - Sandbox open source para ejecutar y analizar malware en entorno controlado.

### 3. Automatización y orquestación

- **Palo Alto Cortex XSOAR**
  - Plataforma SOAR para automatizar tareas repetitivas, integrar herramientas y orquestar respuestas a incidentes.

- **Splunk Phantom**
  - Plataforma SOAR que permite automatizar tareas de seguridad y orquestar flujos entre distintas herramientas.

- **n8n**
  - Herramienta de automatización open source, visual y extensible, útil para crear flujos de trabajo personalizados en SOC.

- **TheHive + Cortex**
  - TheHive integra con Cortex para análisis automatizado de alertas y respuestas coordinadas.

- **Python / PowerShell**
  - Lenguajes de scripting utilizados para crear herramientas personalizadas y automatizar flujos de trabajo en el SOC.

---

## Equipo de Correlación / Threat Modeling

### 1. Creación y gestión de reglas de correlación

- **QRadar**
  - SIEM con potente motor de reglas para correlacionar eventos complejos y detectar patrones avanzados.

- **Splunk Enterprise Security**
  - Permite diseñar reglas personalizadas y casos de uso para mejorar la detección basada en análisis contextual.

- **Elastic SIEM con EQL**
  - Utiliza el lenguaje EQL para definir reglas sofisticadas de correlación y alertas.

### 2. Modelado de amenazas y frameworks

- **MITRE ATT&CK Navigator**
  - Herramienta para visualizar y mapear tácticas y técnicas usadas por atacantes, ayudando a diseñar defensas.

- **ThreatConnect**
  - Plataforma para gestión de inteligencia de amenazas y modelado estratégico, integrando fuentes diversas.

### 3. Análisis avanzado y machine learning

- **ELK Stack (Elasticsearch, Logstash, Kibana)**
  - Suite open source para ingestión, análisis y visualización de grandes volúmenes de datos.

- **Splunk Machine Learning Toolkit**
  - Extensión para Splunk que permite crear modelos predictivos y detección avanzada basada en aprendizaje automático.

### 4. Automatización y orquestación

- **Palo Alto Cortex XSOAR**
  - Plataforma que integra sistemas, automatiza respuestas y mejora la eficiencia mediante playbooks.

- **Splunk Phantom**
  - Plataforma SOAR que permite automatizar tareas de seguridad y orquestar flujos entre distintas herramientas.

### 5. Simulación y testing

- **Caldera (MITRE)**
  - Framework open source para simular ataques reales y probar la eficacia de las defensas.

- **Atomic Red Team**
  - Colección de pruebas automatizadas para validar controles de seguridad y detección basados en ATT&CK.


# Ejemplos de Integraciones Comunes en un SOC

A continuación, se detallan integraciones comunes que se realizan en un SOC para automatizar, centralizar y enriquecer el análisis y respuesta ante incidentes.

---

## 🔗 SIEM Integrado con Fuentes de Logs

### 1. **Firewall (Perimetral / Interno)** → SIEM (Splunk, Elastic, QRadar)
- **Objetivo**: Detectar accesos no autorizados, escaneo de puertos, tráfico malicioso.
- **Ejemplo**:
  - Dispositivo: Cisco ASA, Fortinet FortiGate, Palo Alto.
  - Log: Syslog vía UDP/TCP al colector del SIEM.
  - Resultado: Registros visibles en dashboards de red.

### 2. **EDR (Endpoint Detection & Response)** → SIEM
- **Objetivo**: Monitorear procesos sospechosos en endpoints.
- **Ejemplo**:
  - Herramienta: CrowdStrike Falcon, SentinelOne, Microsoft Defender for Endpoint.
  - Integración: API REST o forwarding nativo de eventos al SIEM.
  - Resultado: Eventos correlacionados con actividad de red o acceso a sistemas.

### 3. **Microsoft 365 / Azure AD** → SIEM
- **Objetivo**: Detección de accesos sospechosos, MFA fallido, logins inusuales.
- **Integración**:
  - Conectores de logs vía API o Azure Sentinel.
  - Logs como: `AuditLogs`, `SignInLogs`, `ExchangeLogs`.
  - Resultado: Alertas por login desde ubicaciones anómalas o sin MFA.

---

# Ejemplos de Integraciones Comunes en un SOC

A continuación, se detallan integraciones comunes que se realizan en un SOC para automatizar, centralizar y enriquecer el análisis y respuesta ante incidentes.

---

## 🔗 SIEM Integrado con Fuentes de Logs

### 1. **Firewall (Perimetral / Interno)** → SIEM (Splunk, Elastic, QRadar)
- **Objetivo**: Detectar accesos no autorizados, escaneo de puertos, tráfico malicioso.
- **Ejemplo**:
  - Dispositivo: Cisco ASA, Fortinet FortiGate, Palo Alto.
  - Log: Syslog vía UDP/TCP al colector del SIEM.
  - Resultado: Registros visibles en dashboards de red.

### 2. **EDR (Endpoint Detection & Response)** → SIEM
- **Objetivo**: Monitorear procesos sospechosos en endpoints.
- **Ejemplo**:
  - Herramienta: CrowdStrike Falcon, SentinelOne, Microsoft Defender for Endpoint.
  - Integración: API REST o forwarding nativo de eventos al SIEM.
  - Resultado: Eventos correlacionados con actividad de red o acceso a sistemas.

### 3. **Microsoft 365 / Azure AD** → SIEM
- **Objetivo**: Detección de accesos sospechosos, MFA fallido, logins inusuales.
- **Integración**:
  - Conectores de logs vía API o Azure Sentinel.
  - Logs como: `AuditLogs`, `SignInLogs`, `ExchangeLogs`.
  - Resultado: Alertas por login desde ubicaciones anómalas o sin MFA.

---

## 🧠 Enriquecimiento de Alertas

### 4. **VirusTotal / AbuseIPDB / GreyNoise** → SOAR o TheHive
- **Objetivo**: Verificar si una IP, hash o dominio es malicioso.
- **Integración**:
  - API REST usada por playbooks (SOAR) o automáticamente por Cortex en TheHive.
  - Resultado: Enriquecimiento automático de indicadores en los casos de alerta.

### 5. **MISP (Threat Intelligence Sharing)** → SIEM / SOAR / TheHive
- **Objetivo**: Incorporar IOCs actualizados a correlaciones y análisis.
- **Integración**:
  - API de MISP consume y exporta IOCs a:
    - Reglas de detección en SIEM.
    - Casos en TheHive.
    - Playbooks en SOAR.
  - Resultado: Las alertas se comparan automáticamente con IOCs activos.

---

## ⚙️ Automatización (SOAR)

### 6. **Splunk / Elastic / QRadar** → Cortex XSOAR / Phantom
- **Objetivo**: Automatizar respuesta ante detecciones.
- **Playbook Ejemplo**:
  - Entrada: Alerta por malware.
  - Flujo:
    1. Consulta hash en VirusTotal.
    2. Si es malicioso → Aísla host vía EDR.
    3. Genera ticket en ServiceNow.
  - Resultado: Respuesta automática sin intervención manual inicial.

### 7. **TheHive + Cortex + n8n**
- **Objetivo**: Orquestar análisis y gestión de casos de forma visual y low-code.
- **Integración**:
  - TheHive lanza análisis automáticos vía Cortex.
  - n8n ejecuta tareas como: enviar correos, actualizar tickets, crear gráficos.
  - Resultado: Automatización sin necesidad de plataformas comerciales.

---

## 📁 Repositorios y Sandboxing

### 8. **Cuckoo Sandbox** → TheHive / Cortex
- **Objetivo**: Analizar muestras sospechosas automáticamente.
- **Integración**:
  - Archivo adjunto en alerta → Enviado a Cuckoo.
  - Reporte de análisis se adjunta al caso en TheHive.
  - Resultado: Análisis automático del comportamiento del malware.

---

## 📄 Gestión y Trazabilidad

### 9. **SIEM / SOAR** → JIRA / ServiceNow
- **Objetivo**: Crear tickets automáticamente cuando se detecta una alerta crítica.
- **Integración**:
  - Webhook, API REST o plugin específico.
  - Incluye detalles como: usuario, IP, fecha, tipo de alerta, acciones tomadas.
  - Resultado: Centralización de seguimiento y cumplimiento normativo.

---

## 🌐 Web Filtering y Proxy

### 10. **Blue Coat / Zscaler / Squid Logs** → SIEM
- **Objetivo**: Detectar navegación a sitios maliciosos o categorías prohibidas.
- **Integración**:
  - Logs en formato syslog o CSV enviados periódicamente al SIEM.
  - Se correlaciona con IOCs o comportamiento del usuario.
  - Resultado: Alertas por navegación anómala.

---

## 📦 Detección en Nube y Aplicaciones

### 11. **AWS CloudTrail / GCP Logs / Azure Logs** → SIEM
- **Objetivo**: Auditar actividades de administración en entornos cloud.
- **Integración**:
  - CloudTrail envía logs a S3, Lambda los exporta al SIEM.
  - Alternativamente, vía DataForwarder (por ejemplo, en QRadar).
  - Resultado: Alertas por cambios de políticas, IAM o uso indebido.




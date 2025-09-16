
# Fuentes de Ingesta de Logs en SIEM

Un **SIEM** (Security Information and Event Management) es una herramienta clave en ciberseguridad que recolecta, analiza y correlaciona logs y eventos de diferentes fuentes para detectar amenazas, anomalías y cumplir con requisitos regulatorios.

Para entender cómo funciona un SIEM, es fundamental conocer las **fuentes de ingesta de logs**, es decir, de dónde provienen los datos que el SIEM procesa.

---

## ¿Qué es la ingesta de logs?

La **ingesta de logs** es el proceso mediante el cual un SIEM recibe y recopila registros (logs) generados por diferentes dispositivos, aplicaciones y servicios dentro de una organización.

---

## Principales fuentes de ingesta de logs

### 1. **Sistemas Operativos**

- **Windows Event Logs**  
  - Registros de eventos del sistema operativo Windows, como inicio de sesión, errores, cambios en políticas, y actividades de usuarios.  
  - Muy útil para monitorear accesos, privilegios y comportamiento anómalo.

- **Linux/Unix Syslog**  
  - Logs generados por el sistema Linux/Unix, como mensajes del kernel, autenticación, fallos y servicios en ejecución.  
  - Generalmente enviados vía protocolo syslog (UDP/TCP).

### 2. **Dispositivos de Red**

- **Firewalls**  
  - Registros de conexiones permitidas o bloqueadas, intentos de intrusión, tráfico anómalo, etc.

- **Routers y Switches**  
  - Información sobre el tráfico de red, cambios en configuraciones, errores y eventos importantes de la infraestructura.

- **IDS/IPS (Intrusion Detection/Prevention Systems)**  
  - Alertas sobre intentos de intrusión, ataques conocidos o comportamientos sospechosos.

### 3. **Sistemas de Autenticación**

- **Active Directory / LDAP**  
  - Eventos relacionados con autenticaciones, creación/eliminación de usuarios, cambios en permisos, etc.

- **VPNs y sistemas de acceso remoto**  
  - Logs de conexiones remotas, autenticación y uso de túneles seguros.

### 4. **Aplicaciones**

- **Servidores Web (Apache, Nginx, IIS)**  
  - Logs de acceso, errores, ataques web (SQLi, XSS), patrones de tráfico.

- **Bases de Datos**  
  - Consultas, accesos, cambios en datos sensibles.

- **Aplicaciones Empresariales**  
  - Logs específicos que reflejan uso, errores, eventos de seguridad o cumplimiento.

### 5. **Sistemas Cloud**

- **Plataformas Cloud (AWS, Azure, GCP)**  
  - Logs de auditoría, acceso a recursos, configuración, cambios y alertas de seguridad.

- **Contenedores y Orquestadores (Docker, Kubernetes)**  
  - Logs de despliegue, ejecución, errores y seguridad de contenedores.

### 6. **Herramientas de Seguridad**

- **Antivirus / Endpoint Detection and Response (EDR)**  
  - Alertas de malware, comportamiento sospechoso, análisis de archivos.

- **SOAR (Security Orchestration, Automation and Response)**  
  - Logs de automatización de respuestas, workflows, acciones tomadas.

### 7. **Otros Dispositivos**

- **Cámaras de Seguridad IP**  
  - Algunos SIEMs también pueden ingerir logs de dispositivos IoT para análisis de seguridad física.

- **Dispositivos industriales (ICS/SCADA)**  
  - Logs para proteger infraestructuras críticas.

---

## Métodos comunes para la ingesta de logs

- **Syslog**  
  - Protocolo estándar para enviar logs desde dispositivos y servidores hacia el SIEM.

- **Agentes de recolección**  
  - Software instalado en los sistemas para capturar y enviar logs de forma segura y fiable.

- **APIs y conectores específicos**  
  - Para servicios en la nube y aplicaciones que no usan syslog, el SIEM puede conectarse a través de APIs.

- **Integración con bases de datos y archivos**  
  - Lectura periódica de logs almacenados en archivos o bases de datos.

---

## Importancia de una buena ingesta de logs

- **Cobertura completa:** Cuantos más dispositivos y aplicaciones integrados, mejor visibilidad de la seguridad.
- **Calidad y normalización:** Los logs deben ser estructurados y normalizados para facilitar su análisis.
- **Tiempo real:** La ingesta rápida permite detección y respuesta a incidentes inmediata.
- **Seguridad en la transmisión:** Uso de protocolos seguros para evitar manipulación o pérdida de datos.

---

# Integración de Logs en SIEMs: Detalles y Datos Prácticos

La **integración de logs** en un SIEM es un paso fundamental para garantizar la visibilidad de la seguridad dentro de una organización. Este proceso implica configurar, recolectar y normalizar datos de diversas fuentes para su análisis y correlación.

---

## 1. **¿Qué implica la integración de logs?**

- **Recolectar** logs desde múltiples dispositivos y aplicaciones.
- **Transportar** los logs de forma segura y confiable al SIEM.
- **Normalizar** y estructurar los datos para análisis eficiente.
- **Correlacionar** eventos para detectar incidentes de seguridad.

---

## 2. **Fuentes comunes y métodos de integración**

| Fuente                      | Método de Integración                    | Protocolo / Herramienta               | Notas Prácticas                                      |
|----------------------------|----------------------------------------|-------------------------------------|-----------------------------------------------------|
| Sistemas Windows            | Windows Event Forwarding (WEF), Agentes | WMI, Winlogbeat, NXLog               | WEF permite enviar eventos a un servidor central.   |
| Linux / Unix                | Syslog, agentes                        | Syslog (UDP/TCP), Filebeat, NXLog   | Agentes pueden leer archivos `/var/log/`.            |
| Firewalls                  | Syslog, APIs                           | Syslog, APIs específicas             | Configurar niveles de logging para no saturar.       |
| Routers / Switches          | Syslog                               | Syslog (UDP/TCP)                     | Verificar compatibilidad con formatos.               |
| IDS/IPS                    | Syslog, APIs                          | Syslog, APIs específicas             | Integrar alertas críticas para detección rápida.     |
| Active Directory            | Agentes, APIs                        | Winlogbeat, LDAP Queries             | Extraer logs de eventos de autenticación.            |
| Servidores Web             | Lectura de logs, agentes              | Filebeat, NXLog                      | Manejar logs rotativos para no perder datos.         |
| Bases de Datos             | APIs, agentes                         | Conectores específicos               | Logs de auditoría pueden ser pesados, filtrar.       |
| Cloud Platforms            | APIs, agentes                        | AWS CloudTrail, Azure Monitor        | Configurar permisos mínimos necesarios.              |
| Endpoints (Antivirus/EDR) | Agentes, APIs                        | Agentes EDR, Syslog                  | Agentes ligeros para no impactar rendimiento.        |

---

## 3. **Herramientas y agentes populares para ingesta**

- **Filebeat / Winlogbeat (Elastic Stack)**  
  - Envían logs directamente a Elasticsearch o Logstash.  
  - Configurables para diferentes fuentes y formatos.

- **NXLog**  
  - Soporta Windows, Linux y otras plataformas.  
  - Permite recolección avanzada, filtrado y transformación.

- **Splunk Universal Forwarder**  
  - Envía datos a Splunk Enterprise.  
  - Optimizado para bajo impacto en los sistemas.

- **Syslog-ng / rsyslog**  
  - Daemon para recolección y reenvío de logs en Linux/Unix.  
  - Compatible con formatos personalizados.

---

## 4. **Protocolos y formatos comunes**

- **Syslog (RFC 3164 / RFC 5424)**  
  - Protocolo estándar para envío de logs.  
  - Puede ser UDP (menos seguro) o TCP/TLS (más seguro).

- **CEF (Common Event Format)**  
  - Formato estandarizado para eventos de seguridad.  
  - Facilita normalización en SIEM.

- **LEEF (Log Event Extended Format)**  
  - Similar a CEF, usado por IBM QRadar.

- **JSON / XML**  
  - Formatos estructurados para aplicaciones modernas y APIs.

---

## 5. **Prácticas recomendadas para integración**

- **Seguridad en la transmisión**  
  - Usar TLS para proteger los logs en tránsito.  
  - Evitar UDP si la pérdida de datos es crítica.

- **Filtrado y reducción**  
  - Configurar fuentes para enviar solo logs relevantes.  
  - Evitar saturar el SIEM con datos irrelevantes.

- **Normalización y parsing**  
  - Usar parsers para estructurar datos en campos útiles.  
  - Aprovechar reglas predefinidas o personalizadas.

- **Sincronización horaria**  
  - Asegurar que todos los dispositivos tengan NTP sincronizado.  
  - Importante para correlación temporal correcta.

- **Pruebas y validación**  
  - Validar que los logs llegan correctamente y contienen datos esperados.  
  - Monitorear errores en agentes y pérdidas de datos.

---

## 6. **Ejemplo básico de integración con Filebeat para Linux**

1. Instalar Filebeat en servidor Linux.
2. Configurar el archivo `filebeat.yml` para leer `/var/log/syslog`.
3. Configurar la salida hacia el SIEM (ej. Elasticsearch o Logstash).
4. Iniciar el servicio Filebeat.
5. Verificar en el SIEM que los logs llegan correctamente.

```yaml
filebeat.inputs:
- type: log
  enabled: true
  paths:
    - /var/log/syslog

output.elasticsearch:
  hosts: ["http://elasticsearch.local:9200"]
````


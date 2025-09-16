
# 📜 Ejemplos de Logs y 1ué fijarse en ellos

Los logs son la base para la investigación de alertas en un SOC. A continuación se muestran ejemplos de diferentes tipos de logs y los puntos clave que un analista debe revisar.

---

## 1️⃣ Logs de Firewall

**Ejemplo:**

2025-09-04 10:32:45 ACCEPT TCP 192.168.1.23:443 -> 203.0.113.45:514 REJECTED

**Qué mirar:**
- Dirección IP de origen y destino  
- Puerto y protocolo utilizados  
- Acciones permitidas o bloqueadas  
- Frecuencia de conexiones sospechosas  
- Patrones de acceso fuera de horario o desde países no habituales  

---

## 2️⃣ Logs de Endpoint / EDR

**Ejemplo:**

2025-09-04 11:15:22 ALERT Malware Detected: Trojan.Generic.AB123 on host PC-101

**Qué mirar:**
- Nombre del malware o alerta  
- Endpoint afectado  
- Usuario activo en el momento del evento  
- Hora de detección  
- Acciones automáticas realizadas (cuarentena, bloqueo, etc.)  

---

## 3️⃣ Logs de Sistema / Servidor

**Ejemplo (Windows Security Log):**

2025-09-04 12:05:01 EventID 4625: Failed login attempt for user Admin from 198.51.100.23

**Qué mirar:**
- Usuario afectado  
- Dirección IP de origen  
- Cantidad de intentos fallidos  
- Hora y frecuencia de los intentos  
- Posibles patrones de ataque (brute force)  

---

## 4️⃣ Logs de Aplicaciones Web

**Ejemplo (Apache Web Server):**

203.0.113.101 - - [04/Sep/2025:12:30:10 +0000] “POST /login.php HTTP/1.1” 200 512

**Qué mirar:**
- IP de cliente y patrón de acceso  
- URL accedida y método HTTP  
- Código de respuesta (200, 403, 404, 500)  
- Frecuencia de accesos a endpoints críticos  
- Posibles intentos de inyección o exploits  

---

## 5️⃣ Logs de Correo / Phishing

**Ejemplo:**

2025-09-04 13:05:12 SMTP ALERT: Email from unknown@phishingsite.com to user@example.com flagged as spam

**Qué mirar:**
- Remitente sospechoso o dominios maliciosos  
- Destinatario y cantidad de envíos  
- Tipo de amenaza detectada (spam, phishing, malware)  
- Adjuntos o links maliciosos  
- Seguimiento en herramientas de sandbox si aplica  

---

### 💡 Recomendaciones generales al analizar logs

- Priorizar **logs relacionados con alertas activas en SIEM o EDR**  
- Buscar **patrones y correlaciones** entre diferentes fuentes de logs  
- Documentar **horas, IPs, usuarios y endpoints** en el caso de investigación  
- Revisar **frecuencia y contexto**, no solo el evento aislado  
- Guardar **evidencia para escalamiento o reportes posteriores**  


⸻


# 📊 Tipos de Logs en un SOC

Esta tabla resume los principales tipos de logs que se encuentran en un SOC, los estándares que siguen y los puntos clave que un analista debe revisar.

| Tipo de log                 | Ejemplos de origen / herramienta                          | Estándar / Formato              | Qué mirar en el log                                                                 |
|------------------------------|-----------------------------------------------------------|---------------------------------|-----------------------------------------------------------------------------------|
| **Red / Firewall**           | Firewalls, routers, switches, IDS/IPS                     | Syslog (RFC 5424), CEF, LEEF   | IP origen/destino, puerto, protocolo, acción (permitido/bloqueado), patrones sospechosos |
| **Endpoint / EDR**           | CrowdStrike, SentinelOne, Microsoft Defender             | Sysmon, Syslog, CEF/LEEF       | Malware detectado, endpoint afectado, usuario, hora, acciones automáticas         |
| **Sistema / Servidor**       | Windows Event Log, Linux /var/log/syslog, DB logs         | Windows Event Log, Syslog RFC 5424 | EventID, usuario, IP origen, frecuencia, hora, criticidad del evento              |
| **Aplicaciones / Web**       | Apache, Nginx, ERP, CRM                                   | CLF, Combined Log Format, JSON  | IP cliente, URL, método HTTP, código de respuesta, patrón de ataque              |
| **Seguridad / Detección**    | SIEM, IDS/IPS, honeypots                                   | CEF, LEEF, Syslog               | Tipo de alerta, severidad, usuario/host afectado, IOC, correlaciones              |
| **Correo / Phishing**        | Exchange, SMTP, soluciones anti-spam                       | RFC 5322/2822 (headers), Syslog | Remitente sospechoso, destinatario, tipo de amenaza, adjuntos o links maliciosos  |
| **Autenticación / Directorio** | Active Directory, LDAP, RADIUS                             | Syslog, AD Event Log, RFC 5424  | Usuario, IP origen, tipo de login, éxito/fallo, patrones sospechosos              |
| **Contenedores / Microservicios** | Docker, Kubernetes, aplicaciones cloud                 | JSON, XML                        | Logs estructurados, errores, métricas, usuarios, endpoints, tiempos de ejecución  |

---

💡 **Recomendaciones generales:**
- Priorizar logs relacionados con alertas activas en **SIEM o EDR**.  
- Buscar **patrones y correlaciones** entre diferentes fuentes de logs.  
- Documentar **IPs, usuarios, endpoints y timestamps** en la investigación.  
- Revisar **frecuencia y contexto**, no solo eventos aislados.  
- Normalizar logs usando herramientas SIEM para análisis eficiente.
- 
# 📚 Formatos de Logs: Guía Completa

Existen varios **formatos de logs** dependiendo del sistema, la tecnología usada y el propósito del registro. Los logs pueden almacenarse en texto plano, estructuras estándar o formatos binarios.

---

## 🗂️ 1. Logs en Texto Plano (Plain Text)

Son los más comunes y sencillos de leer y procesar.

### 📄 Formato Tradicional (line-based)

- Cada línea representa un evento.
- Separación por espacios, tabuladores o delimitadores como `|`, `:` o `;`.

**Ejemplo (Apache access log):**

127.0.0.1 - - [16/Sep/2025:12:45:22 +0200] "GET /index.html HTTP/1.1" 200 1024


---

## 🧾 2. Formatos Estructurados (Recomendados)

### ✅ JSON (JavaScript Object Notation)

- Muy usado en aplicaciones modernas, microservicios y SIEMs.
- Fácil de leer, enviar por red, indexar y procesar.

```json
{
  "timestamp": "2025-09-16T12:45:22Z",
  "level": "INFO",
  "service": "auth-service",
  "user": "admin",
  "event": "login_success",
  "ip": "192.168.1.1"
}
```
### ✅ XML

Menos común hoy, pero todavía usado en entornos legacy.  
Verboso, pero estructurado.

```xml
<log>
  <timestamp>2025-09-16T12:45:22Z</timestamp>
  <level>ERROR</level>
  <message>Failed login</message>
  <user>admin</user>
</log>

```

## 📡 3. Formatos Estándar para Logs de Sistemas

### 🧱 Syslog (RFC 5424)

- Estándar para logs en sistemas Unix/Linux.
- Muy usado en servidores, dispositivos de red y seguridad.

**Ejemplo:**

<34>1 2025-09-16T12:45:22Z server1 appname 1234 ID47 [exampleSDID@32473 iut="3"] Login successful


---

### 💬 CEF (Common Event Format – ArcSight)

- Usado para logs de seguridad.
- Estructura semi-estructurada con delimitadores `|`.

**Ejemplo:**

CEF:0|Vendor|Product|Version|Signature ID|Name|Severity|key1=value1 key2=value2


---

### 🔐 LEEF (Log Event Extended Format – IBM QRadar)

- Similar a CEF, optimizado para QRadar SIEM.

**Ejemplo:**

LEEF:2.0|Vendor|Product|Version|EventID|key=value key2=value2


---

## 🧪 4. Binarios o Propietarios

Algunos sistemas guardan logs en formatos binarios o bases de datos internas.

| Sistema / Software     | Tipo de Log                         |
|-----------------------|-----------------------------------|
| Windows Event Logs     | Binario (.evtx)                   |
| MySQL / PostgreSQL     | Archivos propios o registros en tablas |
| Weblogic, SAP, Oracle  | Logs propietarios                 |

---

## 🔧 5. Otros Formatos Específicos

| Formato   | Usado en...                         |
|-----------|-----------------------------------|
| CSV       | Simple, tabular, exportable a Excel |
| YAML      | Algunos sistemas modernos / DevOps  |
| Protobuf  | Logs binarios compactos (telemetría, IoT) |

---

## 📌 ¿Qué Formato Deberías Usar?

| Necesidad                          | Formato Recomendado           |
|-----------------------------------|------------------------------|
| Fácil lectura manual              | Texto plano, CSV              |
| Integración con sistemas modernos | JSON, Syslog                 |
| Seguridad y cumplimiento (SIEM)   | CEF, LEEF, JSON estructurado |
| Alta eficiencia / bajo ancho de banda | Protobuf, Binario          |

---

## 🧩 Conclusión

No hay un único formato de logs. Depende del caso de uso.  
Hoy en día, lo más recomendable es:

- ✅ JSON para aplicaciones modernas  
- ✅ Syslog para sistemas y red  
- ✅ CEF / LEEF para seguridad y SIEM  
- ✅ Texto plano / CSV para entornos simples o legados  

⚠️ Lo más importante es que los logs sean **estructurados, consistentes, legibles y protegidos**.



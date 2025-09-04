
# 📜 Ejemplos de Logs y Qué Fijarse en Ellos

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

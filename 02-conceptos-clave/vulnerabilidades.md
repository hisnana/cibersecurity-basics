
# CVE (Common Vulnerabilities and Exposures)

---

## ¿Qué es CVE?

CVE es un sistema de identificación estándar para vulnerabilidades y exposiciones conocidas en software y hardware. Cada vulnerabilidad recibe un identificador único (CVE-ID) para facilitar su referencia y gestión.

---

## Conceptos clave

- **CVE-ID:** Código único que identifica una vulnerabilidad (ejemplo: CVE-2023-12345).  
- **Base de datos pública:** CVE es mantenido por MITRE y permite a organizaciones y proveedores compartir información de vulnerabilidades de manera estandarizada.  
- **Importancia:** Facilita la comunicación y coordinación para parches, análisis y mitigación.

---

## ¿Para qué sirve?

- Identificar rápidamente vulnerabilidades específicas.  
- Buscar información sobre el riesgo, exploits conocidos y soluciones.  
- Priorizar parches y medidas de seguridad basadas en CVE.

---

## Ejemplo

- **CVE-2017-0144:** Vulnerabilidad en SMB que permitió el ataque WannaCry ransomware.  
- Permite a los equipos de seguridad buscar detalles y aplicar parches recomendados.

---

## Recursos relacionados

- [Base de datos CVE oficial](https://cve.mitre.org/)  
- [NVD (National Vulnerability Database)](https://nvd.nist.gov/): Complementa CVE con información adicional como puntuación CVSS y referencias.

---

> ⚠️ *Mantenerse actualizado con CVEs relevantes es clave para proteger sistemas y responder a vulnerabilidades conocidas.*

# 🐞 Vulnerabilidades Conocidas

En este apartado se recogen algunas de las vulnerabilidades más relevantes en ciberseguridad, con su **CVE**, **criticidad** y **ejemplos de explotación o contexto**. Esta información ayuda a entender los riesgos y priorizar mitigación.

---

# Vulnerabilidades con Ejemplos de Explotación y Casos de Uso en Elastic SIEM (EQL/Lucene)

---

## 1️⃣ Cross-Site Scripting (XSS)
- **CVE Ejemplo:** CVE-2020-11022  
- **Criticidad:** Media - Alta (dependiendo del contexto y privilegios)  
- **Descripción:** Inserción de scripts maliciosos en páginas web, ejecutándose en el navegador de otros usuarios.  
- **Ejemplo:** Un atacante inyecta un `<script>` en un formulario de comentarios para robar cookies de sesión.  
- **Mitigación:** Validación y escape de inputs, Content Security Policy (CSP).

### Ejemplo de explotación
Un atacante envía un enlace malicioso a usuarios donde el script roba la cookie de sesión y la envía a un servidor externo, permitiendo secuestrar cuentas.

### Caso de uso Elastic SIEM

- **Descripción:** Detectar solicitudes HTTP que contienen payloads XSS típicos en parámetros.

#### Consulta Lucene:

```lucene
http.request.body:*<script>* OR http.request.body:*onerror=* OR http.request.body:*javascript:*
```
## 2️⃣ SQL Injection

- **CVE Ejemplo:** CVE-2019-1343  
- **Criticidad:** Alta  
- **Descripción:** Inserción de código SQL malicioso en consultas de bases de datos.  
- **Ejemplo:** `SELECT * FROM users WHERE username = 'admin' OR '1'='1';`  
- **Mitigación:** Uso de queries parametrizadas, ORM seguro, validación de inputs.

### Ejemplo de explotación  
Un atacante inyecta código SQL en un campo de búsqueda para obtener datos confidenciales.

### Caso de uso Elastic SIEM  
**Descripción:** Detectar patrones comunes de inyección SQL en parámetros o cuerpo de solicitudes.

**Consulta Lucene:**  
http.request.body:" OR 1=1" OR http.request.body:"UNION SELECT" OR http.request.body:'--


**Consulta EQL:**  
```eql
sequence by http.request.id
  [http where http.request.body.keyword : "* OR 1=1"]
  or
  [http where http.request.body.keyword : "*UNION SELECT*"]
  or
  [http where http.request.body.keyword : "*'--*"]
````
## 3️⃣ RCE (Remote Code Execution)

- **CVE Ejemplo:** CVE-2021-34527 (PrintNightmare)  
- **Criticidad:** Crítica  
- **Descripción:** Permite a un atacante ejecutar código arbitrario remotamente.  
- **Ejemplo:** Exploit que aprovecha un servicio vulnerable para ejecutar comandos con privilegios elevados.  
- **Mitigación:** Actualización de software, configuración segura, monitorización.

### Ejemplo de explotación  
Un atacante envía comandos maliciosos para ejecutar código arbitrario en un servidor.

### Caso de uso Elastic SIEM  
**Descripción:** Detectar ejecución de comandos sospechosos o uso anómalo de PowerShell.

**Consulta Lucene:**  
process.command_line:"Invoke-Expression" OR process.command_line:"powershell -EncodedCommand" OR process.command_line:Invoke-WebRequest


**Consulta EQL:**  
```eql
sequence by process.pid
  [process where process.command_line.keyword : "*Invoke-Expression*"]
  or
  [process where process.command_line.keyword : "*powershell -EncodedCommand*"]
  or
  [process where process.command_line.keyword : "*Invoke-WebRequest*"]
````
## 4️⃣ Desbordamiento de Buffer (Buffer Overflow)

- **CVE Ejemplo:** CVE-2018-8897  
- **Criticidad:** Alta  
- **Descripción:** Sobrescribir memoria adyacente, causando ejecución arbitraria o crash.  
- **Ejemplo:** Input excesivamente largo que provoca corrupción de memoria.  
- **Mitigación:** Validación de inputs, uso de lenguajes seguros, ASLR y DEP.

### Ejemplo de explotación  
Envió de un payload demasiado largo que provoca crash o ejecución arbitraria.

### Caso de uso Elastic SIEM  
**Descripción:** Detectar errores críticos en aplicaciones relacionados con buffer overflow.

**Consulta Lucene:**  
log.level:error AND message:buffer overflow

**Consulta EQL:**  
```eql
sequence by process.pid
  [log where log.level == "error" and log.message.keyword : "*buffer overflow*"]
````

## 5️⃣ Vulnerabilidades de deserialización insegura

- **CVE Ejemplo:** CVE-2017-12149  
- **Criticidad:** Alta  
- **Descripción:** Deserializar datos no confiables puede permitir ejecución de código.  
- **Ejemplo:** Aplicación Java deserializa objeto malicioso y ejecuta código arbitrario.  
- **Mitigación:** Evitar deserializar datos no confiables, validación estricta.

### Ejemplo de explotación  
Un objeto serializado malicioso ejecuta comandos al ser deserializado.

### Caso de uso Elastic SIEM  
**Descripción:** Detectar excepciones relacionadas con deserialización insegura.

**Consulta Lucene:**  
message:"InvalidClassException"


**Consulta EQL:**  
```eql
sequence by process.pid
  [log where log.message.keyword : "InvalidClassException"]
````
## 6️⃣ Cross-Site Request Forgery (CSRF)

- **CVE Ejemplo:** CVE-2020-11023  
- **Criticidad:** Media  
- **Descripción:** Un atacante induce a un usuario autenticado a ejecutar acciones no deseadas.  
- **Ejemplo:** Transferencia de fondos sin consentimiento mediante enlace malicioso.  
- **Mitigación:** Tokens CSRF, verificación de origen, SameSite cookies.

### Ejemplo de explotación  
Usuario autenticado accede a enlace malicioso que realiza acción no autorizada.

### Caso de uso Elastic SIEM  
**Descripción:** Detectar solicitudes POST sin token CSRF o sin headers referer/origin.

**Consulta Lucene:**  
http.request.method:POST AND NOT http.request.headers.referer:* AND NOT http.request.headers.origin:*


**Consulta EQL:**  
```eql
sequence by http.request.id
  [http where http.request.method == "POST" and
   not http.request.headers.referer exists and
   not http.request.headers.origin exists]
````
## 7️⃣ Vulnerabilidades en software crítico (Log4Shell)

- **CVE Ejemplo:** CVE-2021-44228 (Log4Shell)  
- **Criticidad:** Crítica  
- **Descripción:** Ejecución remota de código mediante vulnerabilidad en Log4j.  
- **Ejemplo:** JNDI lookup malicioso que ejecuta código en el servidor.  
- **Mitigación:** Actualización de Log4j, monitorización de logs.

### Ejemplo de explotación  
Inyección de cadena JNDI maliciosa desencadenando ejecución remota.

### Caso de uso Elastic SIEM  
**Descripción:** Detectar patrones JNDI maliciosos en logs de aplicaciones.

**Consulta Lucene:**  
message:${jndi:


**Consulta EQL:**  
```eql
sequence by process.pid
  [log where log.message.keyword : "*${jndi:*"]
````





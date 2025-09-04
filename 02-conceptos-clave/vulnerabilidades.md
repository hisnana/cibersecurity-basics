
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

## 1️⃣ Cross-Site Scripting (XSS)
- **CVE Ejemplo:** CVE-2020-11022  
- **Criticidad:** Media - Alta (dependiendo del contexto y privilegios)  
- **Descripción:** Inserción de scripts maliciosos en páginas web, ejecutándose en el navegador de otros usuarios.  
- **Ejemplo:** Un atacante inyecta un `<script>` en un formulario de comentarios para robar cookies de sesión.  
- **Mitigación:** Validación y escape de inputs, Content Security Policy (CSP).

---

## 2️⃣ SQL Injection
- **CVE Ejemplo:** CVE-2019-1343  
- **Criticidad:** Alta  
- **Descripción:** Inserción de código SQL malicioso en consultas de bases de datos, permitiendo acceso no autorizado o modificación de datos.  
- **Ejemplo:** `SELECT * FROM users WHERE username = 'admin' OR '1'='1';`  
- **Mitigación:** Uso de queries parametrizadas, ORM seguro, validación de inputs.

---

## 3️⃣ RCE (Remote Code Execution)
- **CVE Ejemplo:** CVE-2021-34527 (PrintNightmare)  
- **Criticidad:** Crítica  
- **Descripción:** Permite a un atacante ejecutar código arbitrario de forma remota en el sistema víctima.  
- **Ejemplo:** Exploit que aprovecha un servicio vulnerable para ejecutar comandos con privilegios elevados.  
- **Mitigación:** Actualización de software, configuración segura, monitorización de logs.

---

## 4️⃣ Desbordamiento de Buffer (Buffer Overflow)
- **CVE Ejemplo:** CVE-2018-8897  
- **Criticidad:** Alta  
- **Descripción:** Sobrescribir memoria adyacente en un programa, permitiendo ejecución de código arbitrario o crash de la aplicación.  
- **Ejemplo:** Un input excesivamente largo en un servicio vulnerable causa corrupción de memoria.  
- **Mitigación:** Validación de inputs, uso de lenguajes seguros, ASLR y DEP habilitados.

---

## 5️⃣ Vulnerabilidades de deserialización insegura
- **CVE Ejemplo:** CVE-2017-12149  
- **Criticidad:** Alta  
- **Descripción:** Al deserializar datos no confiables, un atacante puede ejecutar código o modificar objetos internos.  
- **Ejemplo:** Aplicación Java deserializa un objeto remoto malicioso y ejecuta código arbitrario.  
- **Mitigación:** Evitar deserializar datos no confiables, usar bibliotecas seguras, validación de tipos.

---

## 6️⃣ Cross-Site Request Forgery (CSRF)
- **CVE Ejemplo:** CVE-2020-11023  
- **Criticidad:** Media  
- **Descripción:** Un atacante engaña a un usuario autenticado para ejecutar acciones no deseadas en una aplicación web.  
- **Ejemplo:** Usuario autenticado en un banco recibe un enlace que transfiere fondos sin su consentimiento.  
- **Mitigación:** Tokens CSRF, verificación de origen, SameSite cookies.

---

## 7️⃣ Vulnerabilidades en software crítico
- **CVE Ejemplo:** CVE-2021-44228 (Log4Shell)  
- **Criticidad:** Crítica  
- **Descripción:** Ejecución remota de código en aplicaciones que usan la biblioteca Log4j.  
- **Ejemplo:** Un atacante envía un JNDI lookup malicioso que ejecuta código en el servidor.  
- **Mitigación:** Actualización de Log4j a versión segura, monitorización de logs y alertas.

---

### 🔹 Buenas prácticas para el apartado de vulnerabilidades

- Mantener un **listado actualizado** con los CVE más recientes y relevantes.  
- Incluir **criticidad** usando CVSS o clasificación interna.  
- Añadir **ejemplos claros de explotación** y mitigación.  
- Relacionar vulnerabilidades con **playbooks de respuesta**, escaneos y alertas SIEM.  

---



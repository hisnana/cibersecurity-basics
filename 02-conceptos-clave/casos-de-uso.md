
# 📂 Casos de Uso en un SOC

Los casos de uso (use cases) en un SOC muestran **cómo se aplican las herramientas, procedimientos y reglas de detección** para identificar y responder a incidentes reales.

---

## 1️⃣ Qué son los casos de uso
- Son **escenarios concretos de amenazas o eventos de seguridad** que un SOC busca detectar.  
- Permiten **definir reglas de correlación, alertas y playbooks** en SIEM y SOAR.  
- Ayudan a **medir la eficacia de la detección** y mejorar procedimientos.  

---

## 2️⃣ Qué incluir en cada caso de uso

1. **Nombre del caso de uso**  
   - Ej: "Intento de phishing dirigido", "Ransomware en endpoints", "Escaneo de red interno".  

2. **Descripción**  
   - Qué evento se detecta y por qué es relevante.  
   - Ej: "Se detecta envío masivo de correos sospechosos con enlaces a dominios no confiables".  

3. **Fuentes de datos / logs**  
   - SIEM, EDR, firewall, proxy, correo, logs de aplicaciones.  

4. **Indicadores y métricas**  
   - IOC/IOA relevantes: IPs, hashes, URLs, nombres de procesos.  
   - TTP según MITRE ATT&CK.  
   - Severidad / criticidad del incidente.  

5. **Reglas de correlación / triggers**  
   - Qué alerta genera el SIEM o qué acción dispara el SOAR.  

6. **Acciones de respuesta**  
   - Escalamiento, contención, bloqueo, notificación a usuario/cliente.  
   - Ejemplo: "Cuarentena de endpoint mediante EDR + creación de caso en TheHive".  

7. **Herramientas implicadas**  
   - SIEM, SOAR, EDR, Threat Intelligence, TheHive, Jira, etc.  

8. **Resultados esperados / objetivos**  
   - Qué se espera detectar, prevenir o mitigar.  
   - Métricas de efectividad: reducción de tiempo de respuesta, número de incidentes prevenidos.  

---

## 3️⃣ Ejemplos de casos de uso

- **Phishing interno detectado por correo**  
  - Logs: EDR + Email gateway + SIEM  
  - Acción: Notificación, cuarentena de emails, creación de caso en TheHive  

- **Ransomware en endpoints**  
  - Logs: EDR + SIEM + Firewall  
  - Acción: Aislamiento del endpoint, mitigación de red, reporte y escalamiento a Tier 2  

- **Escaneo de puertos interno sospechoso**  
  - Logs: Firewall + IDS  
  - Acción: Bloqueo IP, alerta a L2, documentación en sistema de gestión  

- **Acceso sospechoso de usuario privilegiado**  
  - Logs: Active Directory + SIEM  
  - Acción: Revisar autenticaciones, bloqueos temporales, notificación al SOC manager  

---

## 4️⃣ Buenas prácticas

- Documentar cada caso de uso de manera **estándar** para replicarlo y actualizarlo.  
- Relacionar casos de uso con **playbooks SOAR** para automatizar la respuesta.  
- Revisar y actualizar casos según **nuevas amenazas o cambios en infraestructura**.  
- Incluir **ejemplos de logs y alertas generadas** para referencia.  

---

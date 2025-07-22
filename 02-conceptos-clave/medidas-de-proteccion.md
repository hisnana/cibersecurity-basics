# 🛡️ Medidas de Protección en Ciberseguridad (SOC Tier 1)

Como analista Tier 1, es importante entender las principales medidas defensivas que protegen una organización. Estas defensas son la primera línea para detectar, prevenir o mitigar ataques.

---

## 1. **Firewall**

Controla el tráfico de red entrante y saliente según reglas definidas.

**Tipos:**
- Perimetral (en el borde de la red)
- Personal (en endpoints)
- Aplicación (WAF)

🛠️ *Ejemplo:* Bloquear el puerto 3389 (RDP) desde direcciones IP externas.

---

## 2. **Antivirus / Antimalware**

Detecta y elimina software malicioso en endpoints y servidores.

**Funciones:**
- Escaneo en tiempo real
- Cuarentena de archivos
- Detección por firmas y heurística

🛠️ *Ejemplo:* Detección de un troyano descargado desde un adjunto de correo.

---

## 3. **EDR (Endpoint Detection and Response)**

Monitoriza el comportamiento en endpoints y permite responder a incidentes.

**Funciones:**
- Aislamiento del equipo
- Análisis forense
- Contención del ataque

🛠️ *Ejemplo:* Microsoft Defender for Endpoint detecta ejecución de PowerShell malicioso.

---

## 4. **SIEM (Security Information and Event Management)**

Centraliza y correlaciona logs de sistemas para detectar incidentes en tiempo real.

**Funciones:**
- Alertas automáticas
- Detección de anomalías
- Reportes de cumplimiento

🛠️ *Ejemplo:* Alerta por múltiples fallos de inicio de sesión desde una IP sospechosa.

---

## 5. **Control de accesos**

Permite el acceso solo a usuarios autorizados mediante políticas de seguridad.

**Ejemplos:**
- Contraseñas seguras
- Autenticación multifactor (MFA)
- Políticas de mínimo privilegio

🛠️ *Ejemplo:* Un técnico no puede acceder a recursos del área financiera.

---

## 6. **Cifrado**

Protege los datos almacenados o transmitidos para que no puedan ser leídos sin autorización.

**Ámbitos:**
- En tránsito (TLS/HTTPS)
- En reposo (BitLocker, LUKS)

🛠️ *Ejemplo:* Correo cifrado para enviar documentos sensibles.

---

## 7. **Parcheo y actualizaciones**

Corregir vulnerabilidades aplicando actualizaciones de software.

🛠️ *Ejemplo:* Parchear sistemas afectados por vulnerabilidades como Log4Shell o BlueKeep.

---

## 8. **Segmentación de red**

Divide la red en zonas para limitar el movimiento lateral del atacante.

🛠️ *Ejemplo:* Separar la red de usuarios de la red de servidores críticos.

---

## 9. **Backups (copias de seguridad)**

Permiten recuperar datos ante un ataque, fallo técnico o error humano.

🛠️ *Ejemplo:* Restaurar archivos desde una copia de seguridad tras un ataque ransomware.

---

## 10. **Awareness y formación**

Capacitación del personal para identificar amenazas como phishing o ingeniería social.

🛠️ *Ejemplo:* Simulaciones de phishing para entrenar al personal no técnico.

---

> ✅ *Un SOC no solo reacciona a ataques: también valida que estas medidas estén activas y funcionando correctamente.*


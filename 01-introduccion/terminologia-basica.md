
# Terminología Básica en Ciberseguridad

Este documento recoge los términos más comunes que todo profesional de soporte (Tier 1) debe conocer al trabajar con sistemas seguros y detectar amenazas.

---

## 🔐 Autenticación
Proceso de verificar la identidad de un usuario o sistema. Ejemplo: ingresar con usuario y contraseña.

## 🧑‍💻 Autorización
Permite o deniega el acceso a recursos una vez que un usuario ha sido autenticado.

## 📂 Confidencialidad
Asegura que la información solo pueda ser accedida por personas autorizadas.

## ✍️ Integridad
Garantiza que la información no ha sido modificada o alterada sin autorización.

## ♻️ Disponibilidad
Asegura que los sistemas y datos estén accesibles cuando se necesiten.

---

## 🐛 Vulnerabilidad
Debilidad en un sistema que puede ser explotada para causar daño o comprometerlo.

## 🎯 Amenaza
Cualquier evento o entidad que tenga el potencial de explotar una vulnerabilidad.

## 🦠 Malware
Software malicioso. Incluye virus, troyanos, ransomware, spyware, etc.

## Definiciones y ejemplos de herramientas de protección de red

- **IDS (Intrusion Detection System):**  
  Sistema que **detecta** actividades sospechosas o maliciosas en la red, pero **no actúa automáticamente** para detenerlas.  
  **Ejemplos:**  
  - Snort  
  - Suricata  
  - Zeek (antes Bro)  
  - OSSEC (cuando se usa en modo detección)

- **IPS (Intrusion Prevention System):**  
  Sistema que detecta y **bloquea automáticamente** ataques o tráfico malicioso en tiempo real.  
  **Ejemplos:**  
  - Snort (en modo inline)  
  - Suricata (modo IPS)  
  - Cisco Firepower  
  - Palo Alto Networks Threat Prevention

- **Firewall:**  
  Dispositivo o software que **controla el tráfico de red** según reglas definidas, permitiendo o bloqueando conexiones según puertos, direcciones IP, protocolos, etc.  
  **Ejemplos:**  
  - iptables / nftables (Linux)  
  - Windows Defender Firewall  
  - pfSense  
  - Fortinet FortiGate  
  - Cisco ASA  


## 🧬 Hash
Valor único generado a partir de datos. Se usa para verificar integridad de archivos y contraseñas.

## 🔐 MFA (Multi-Factor Authentication)
Uso de dos o más métodos para autenticar a un usuario, como contraseña + código SMS.

## **Algoritmos de cifrado**

Operación o función matemática utilizada en combinación con una clave que se aplica a un texto en claro y permite obtener un texto cifrado (o descifrarlo).

## Definiciones y ejemplos de herramientas de seguridad

- **EDR (Endpoint Detection and Response):**  
  Solución que detecta, investiga y responde a amenazas en dispositivos finales (PCs, servidores).  
  **Ejemplos:**  
  - Microsoft Defender for Endpoint  
  - CrowdStrike Falcon  
  - SentinelOne  
  - Sophos Intercept X

- **XDR (Extended Detection and Response):**  
  Plataforma que unifica y correlaciona datos de múltiples fuentes (endpoints, red, nube, correo) para detectar amenazas avanzadas.  
  **Ejemplos:**  
  - Palo Alto Cortex XDR  
  - Trend Micro Vision One  
  - Microsoft Defender XDR  
  - Fortinet FortiXDR

- **SOAR (Security Orchestration, Automation and Response):**  
  Herramienta que automatiza tareas de seguridad (como respuestas a alertas) y orquesta flujos de trabajo entre distintos sistemas.  
  **Ejemplos:**  
  - Splunk SOAR  
  - IBM Security QRadar SOAR  
  - Palo Alto Cortex XSOAR  
  - Swimlane

- **SIEM (Security Information and Event Management):**  
  Sistema que centraliza y analiza logs y eventos de seguridad en tiempo real para detectar anomalías y amenazas.  
  **Ejemplos:**  
  - Splunk  
  - IBM QRadar  
  - Microsoft Sentinel  
  - Elastic SIEM  




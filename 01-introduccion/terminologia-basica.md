
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
 
  - -----

# 🥊 Red Team, Blue Team y Purple Team en Ciberseguridad

En ciberseguridad ofensiva y defensiva, existen equipos especializados que cumplen roles diferentes pero complementarios. Conocer su función ayuda a entender cómo se protege y se pone a prueba la seguridad de una organización.

---

## 🔴 Red Team (Equipo Rojo)

**Objetivo:** Simular ataques reales para probar la seguridad de los sistemas desde una perspectiva ofensiva.

**Funciones principales:**
- Realizar pruebas de penetración (pentesting).
- Emular ataques de actores reales (APT, ransomware, insiders).
- Evaluar la efectividad de la defensa sin previo aviso.

**Ejemplos de actividades:**
- Explotar vulnerabilidades.
- Realizar phishing dirigido (spear phishing).
- Elevar privilegios y moverse lateralmente por la red.
- Extraer datos (exfiltración).

**Herramientas comunes:**
- Metasploit, Cobalt Strike, BloodHound, Empire, Nmap.

---

## 🔵 Blue Team (Equipo Azul)

**Objetivo:** Defender la infraestructura de TI, detectar y responder a los ataques.

**Funciones principales:**
- Monitorear sistemas con SIEM, EDR y firewalls.
- Analizar alertas y responder a incidentes (IR).
- Fortalecer la seguridad: parches, políticas, segmentación.
- Investigar amenazas y realizar threat hunting.

**Ejemplos de actividades:**
- Analizar logs de alertas sospechosas.
- Contener una infección detectada por el EDR.
- Bloquear una IP en el firewall tras detectar C2.
- Realizar análisis forense básico.

**Herramientas comunes:**
- Splunk, Microsoft Sentinel, CrowdStrike, Velociraptor, YARA, Suricata.

---

## 🟣 Purple Team (Equipo Morado)

**Objetivo:** Colaborar entre Red y Blue Team para mejorar continuamente la detección y la respuesta.

**Funciones principales:**
- Coordinar ejercicios entre ofensiva y defensiva.
- Analizar qué técnicas del Red Team fueron detectadas (y cuáles no).
- Mejorar reglas de detección y casos de uso.
- Fomentar el aprendizaje compartido.

**Ejemplos de actividades:**
- Simular un ataque (Red) y ajustar detecciones en el SIEM (Blue).
- Automatizar la respuesta con SOAR basado en lo aprendido.
- Documentar mejoras técnicas y procesos.

**Herramientas comunes:**
- MITRE ATT&CK Framework  
- Atomic Red Team (simulación de TTPs)  
- Caldera (emulación de adversarios)  
- Sigma (detecciones compartibles)

---

## 🧠 Resumen comparativo

| Equipo      | Enfoque    | Objetivo principal                     | Rol típico en una organización             |
|-------------|------------|----------------------------------------|--------------------------------------------|
| Red Team    | Ofensivo   | Simular ataques reales                 | Testeo de seguridad (pentesting avanzado)  |
| Blue Team   | Defensivo  | Detectar, proteger y responder         | SOC, IR, gestión de alertas                |
| Purple Team | Colaborativo | Mejorar detección y respuesta conjunta | Coordinación de Red + Blue (optimización) |

---

> 🎯 *Un SOC Tier 1 forma parte del Blue Team. Comprender cómo actúan los otros equipos te ayuda a saber qué buscar y cómo responder mejor ante ataques simulados o reales.*


# ¿Qué es un incidente de ciberseguridad?

Un **incidente de ciberseguridad** es cualquier evento o serie de eventos que comprometen la confidencialidad, integridad o disponibilidad de los sistemas, redes o datos de una organización.

Puede incluir ataques como accesos no autorizados, malware, robo de información, interrupción de servicios o cualquier actividad que afecte negativamente la seguridad informática.

---

**Ejemplo:**  
- Un intento exitoso de acceso no autorizado a un servidor.  
- La propagación de un ransomware que cifra datos críticos.  
- La detección de tráfico anómalo que indica una posible intrusión.

---

> Un incidente debe ser identificado, analizado y gestionado rápidamente para minimizar el impacto y restaurar la seguridad.


# Definiciones Clave en Seguridad Informática

---

## Hacker

Persona experta en sistemas informáticos que explora, analiza o modifica sistemas para entender su funcionamiento o encontrar vulnerabilidades. Puede tener intenciones benignas o maliciosas.

---

## Pentester (Tester de penetración)

Profesional que realiza pruebas controladas y autorizadas para identificar vulnerabilidades en sistemas o aplicaciones, con el fin de mejorar la seguridad.

---

## Hacktivista

Hacker que utiliza sus habilidades para promover causas políticas o sociales, generalmente realizando ataques que buscan visibilizar un mensaje o protesta.

---

## Caja Blanca (White Box)

Pruebas de seguridad donde el pentester tiene acceso completo a la información interna del sistema (código fuente, arquitectura, credenciales).

---

## Caja Gris (Gray Box)

Pruebas donde el pentester tiene acceso parcial a información interna, combinando técnicas de caja blanca y caja negra.

---

## Caja Negra (Black Box)

Pruebas en las que el pentester no tiene información previa sobre el sistema objetivo y actúa como un atacante externo real, sin acceso interno.

---

> Estos términos ayudan a definir roles y metodologías en la evaluación y protección de sistemas.


# Metodologías y Estándares en Ciberseguridad

---

## OWASP (Open Web Application Security Project)

**Descripción:**  
Proyecto comunitario que proporciona recursos, herramientas y buenas prácticas para mejorar la seguridad de las aplicaciones web.

**Conceptos clave:**  
- Listado OWASP Top 10: Las 10 vulnerabilidades más críticas en aplicaciones web (ej. inyección SQL, cross-site scripting).  
- Guías para desarrollo seguro y pruebas de seguridad.

**Uso:**  
Fundamental para desarrolladores, testers y equipos de seguridad al evaluar o diseñar aplicaciones web seguras.

---

## ISO 27000 (Familia de normas ISO/IEC 27000)

**Descripción:**  
Conjunto de normas internacionales para gestionar la seguridad de la información en las organizaciones.

**Conceptos clave:**  
- ISO/IEC 27001: Estándar para sistemas de gestión de seguridad de la información (SGSI).  
- ISO/IEC 27002: Código de buenas prácticas para controles de seguridad.  
- Enfoque basado en riesgos para identificar, evaluar y tratar riesgos de seguridad.

**Uso:**  
Adoptada por empresas para certificar su gestión de seguridad y cumplir con regulaciones.

---

## Otras Metodologías y Marcos Relevantes

### NIST Cybersecurity Framework

- Marco flexible para mejorar la gestión de riesgos en ciberseguridad.  
- Cinco funciones principales: Identificar, Proteger, Detectar, Responder, Recuperar.

### MITRE ATT&CK

- Base de conocimientos de tácticas, técnicas y procedimientos (TTPs) usados por adversarios.  
- Utilizado para modelar ataques y mejorar detección y respuesta.

### CIS Controls (Center for Internet Security)

- Lista priorizada de controles para mejorar la ciberseguridad en organizaciones.  
- Enfocado en acciones prácticas y efectivas.

---

## Resumen rápido

| Metodología / Estándar | Enfoque                   | Uso principal                              |
|-----------------------|--------------------------|-------------------------------------------|
| OWASP                 | Seguridad en aplicaciones web | Identificación y mitigación de vulnerabilidades web |
| ISO 27000             | Gestión de seguridad de la información | Implementación de SGSI y cumplimiento normativo |
| NIST CSF              | Gestión de riesgos       | Marco para mejorar postura de ciberseguridad |
| MITRE ATT&CK          | Inteligencia de amenazas | Modelado y detección de técnicas de ataque |
| CIS Controls          | Buenas prácticas         | Priorizar controles de seguridad efectivos |

---

> 📌 *Conocer y aplicar estas metodologías ayuda a construir defensas sólidas y gestionar la seguridad de forma organizada y efectiva.*

# ¿Qué es un Log?

---

## Definición

Un **log** (registro) es un archivo o conjunto de datos que registra eventos, acciones o mensajes generados por sistemas, aplicaciones o dispositivos de red. Los logs son esenciales para monitorear, auditar y diagnosticar el funcionamiento y la seguridad de un entorno informático.

---

## Conceptos clave

- **Fuente:** Sistema operativo, aplicaciones, firewalls, routers, antivirus, etc.  
- **Contenido típico:** Fecha y hora, usuario, tipo de evento, resultado, dirección IP, etc.  
- **Uso principal:** Detección de incidentes, análisis forense, resolución de problemas y cumplimiento normativo.

---

## Ejemplos de logs comunes

| Tipo de Log           | Descripción                            | Ejemplo                                   |
|-----------------------|--------------------------------------|-------------------------------------------|
| Logs de Sistema       | Eventos del sistema operativo          | Inicio o cierre de sesión, errores del sistema |
| Logs de Seguridad     | Eventos relacionados con seguridad     | Intentos de login fallidos, accesos denegados |
| Logs de Aplicaciones  | Registros generados por aplicaciones    | Transacciones, errores en la aplicación   |
| Logs de Firewall      | Registro de tráfico de red filtrado     | Bloqueo de IP sospechosa                   |
| Logs de Antivirus     | Eventos de detección y acción antimalware | Detección de malware, cuarentena de archivos |

---

# Definiciones Clave

---

## PCI DSS (Payment Card Industry Data Security Standard)

Estándar de seguridad que establece requisitos para proteger la información de tarjetas de pago y prevenir fraudes. Aplica a todas las entidades que procesan, almacenan o transmiten datos de tarjetas.

---

## Ofuscar

Técnica que consiste en modificar código o datos para hacerlo difícil de entender o analizar, con el fin de proteger propiedad intelectual o dificultar el análisis por parte de atacantes.

---

## P2P (Peer-to-Peer)

Modelo de red donde los participantes (nodos) se comunican directamente entre sí, compartiendo recursos o información sin necesidad de un servidor central.

---

## SLA (Service Level Agreement)

Acuerdo formal entre un proveedor de servicios y un cliente que define niveles de servicio, responsabilidades y métricas para asegurar la calidad y disponibilidad del servicio.


# 0 Day (Zero Day)

---

## Definición

Un **0 day** es una vulnerabilidad de seguridad en software o hardware que es desconocida para los desarrolladores o el público en general, y por lo tanto, no existe un parche o solución disponible en el momento de su descubrimiento.

Los atacantes pueden aprovechar estas vulnerabilidades para realizar ataques antes de que se haya tomado alguna medida de mitigación.

---

## Características clave

- Vulnerabilidad desconocida hasta su explotación o divulgación.  
- Alta peligrosidad por la falta de defensa previa.  
- Puede ser vendida en mercados clandestinos o usada en ataques dirigidos.

---

## Ejemplo

- Un exploit que aprovecha una falla en un sistema operativo antes de que el fabricante publique un parche.

---

> ⚠️ *La gestión rápida y la actualización constante son esenciales para protegerse contra ataques 0 day.*





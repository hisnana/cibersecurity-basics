# Resumen de Ataques Comunes (SOC Tier 1)

Como analista Tier 1, es fundamental conocer los ataques más comunes que pueden aparecer en alertas de herramientas como SIEM, EDR o firewalls. Aquí se explican de forma clara, con ejemplos reales.

---

## 1. Phishing

Engaño mediante correos, mensajes o sitios falsos para robar credenciales o distribuir malware.

**Ejemplo:**  
- Un correo con asunto “Actualiza tu cuenta de Microsoft” que redirige a una página falsa con URL sospechosa.

🛠️ *Claves para detectar:* dominios falsos, urgencia en el mensaje, errores ortográficos, archivos `.html` o `.exe` como adjuntos.

---

## 2. Ransomware

Malware que cifra los archivos de un sistema y pide un rescate (generalmente en criptomonedas) para desbloquearlos.

**Ejemplo:**  
- LockBit, WannaCry, Conti: se propagan por red y cifran carpetas compartidas.

🛠️ *Indicadores comunes:* múltiples procesos de cifrado, extensiones extrañas en archivos, nota de rescate (`README.txt`), tráfico sospechoso a direcciones TOR.

---

## 3. Malware común

Infecciones de software malicioso como virus, troyanos, keyloggers o spyware.

**Ejemplo:**  
- Un usuario ejecuta un `.exe` descargado por error y se instala un troyano tipo Remcos para control remoto.

🛠️ *Alertas típicas:* ejecución de binarios inusuales, cambios en claves de registro, conexiones salientes persistentes.

---

## 4. Ataques de fuerza bruta

Intentos repetidos de adivinar contraseñas en servicios como RDP, SSH o aplicaciones web.

**Ejemplo:**  
- Decenas de intentos de inicio de sesión fallidos desde una misma IP en pocos minutos.

🛠️ *Herramientas de ataque comunes:* Hydra, Medusa, herramientas de scripts automatizados.

---

## 5. Denegación de Servicio (DoS/DDoS)

Ataque que busca saturar un servicio o servidor mediante peticiones masivas, dejándolo fuera de línea.

**Ejemplo:**  
- Miles de peticiones HTTP/s o conexiones simultáneas desde IPs distintas (botnet).

🛠️ *Detección:* spikes de tráfico, saturación de ancho de banda, logs de aplicaciones web inactivos o con errores 503.

---

## 6. Exploits y vulnerabilidades

Ataques que aprovechan fallos en software para ejecutar código o elevar privilegios.

**Ejemplo:**  
- CVE-2021-44228 (Log4Shell): permite ejecución remota de código en servidores con versiones vulnerables de Log4j.

🛠️ *Indicadores:* conexiones externas justo después de carga de datos, aparición de shells reversas o procesos no esperados.

---

## 7. Movimiento lateral

El atacante se desplaza por la red desde un sistema comprometido para acceder a otros más valiosos.

**Ejemplo:**  
- Uso de `PsExec` o `RDP` para saltar de una máquina infectada a otras dentro del dominio.

🛠️ *Señales típicas:* conexiones internas inusuales, uso de herramientas administrativas, accesos remotos no autorizados.

---

## 8. Ingeniería social

Manipulación psicológica para que usuarios entreguen información o realicen acciones inseguras.

**Ejemplo:**  
- Una llamada telefónica falsa que solicita reiniciar sesión y entregar el código MFA.

🛠️ *Claves:* comportamiento sospechoso de usuarios, entrega de credenciales o acceso no justificado, registros de sesiones anómalas.

---

## 9. Botnets

Redes de dispositivos infectados que actúan coordinadamente bajo control de un atacante.

**Ejemplo:**  
- Botnet Mirai infectaba routers y dispositivos IoT para lanzar ataques DDoS masivos.

🛠️ *Detección:* tráfico saliente hacia direcciones C2 (Command & Control), patrones automatizados, conexiones a puertos no estándar.

---

## Consejos para Tier 1

- Identifica patrones repetitivos en los logs.
- Verifica reputación de IPs, hashes y dominios sospechosos.
- Documenta y escala eventos con impacto real o confirmados.
- Usa herramientas como VirusTotal, AbuseIPDB, Any.run para apoyar tu análisis.

---

> 🎯 *Tu misión como Tier 1 no es investigar en profundidad, sino filtrar alertas reales, priorizar las importantes y escalarlas con contexto.*

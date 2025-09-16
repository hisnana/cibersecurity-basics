
# 📚 Recursos Útiles para Prepararte como Analista SOC Tier 1

A continuación, se presentan enlaces prácticos y confiables para que puedas formarte y practicar habilidades clave en ciberseguridad defensiva.

---

## 🎓 Formación Teórica y Certificaciones Gratuitas

- [Cisco CyberOps Associate (Introductorio)](https://www.netacad.com/courses/cybersecurity/cybersecurity-essentials)
- [IBM Cybersecurity Analyst Professional Certificate (Coursera)](https://www.coursera.org/professional-certificates/ibm-cybersecurity-analyst)
- [Google Cybersecurity Certificate](https://www.coursera.org/professional-certificates/google-cybersecurity)
- [Cybrary SOC Analyst Career Path](https://www.cybrary.it/career-path/soc-analyst/)
- [TryHackMe - SOC Level 1 Learning Path](https://tryhackme.com/path/outline/soclevel1)

---

## 🛠️ Laboratorios y Práctica Técnica

- [TryHackMe - Blue Team Labs](https://tryhackme.com/room/blueteamtools)
- [Blue Team Labs Online (BTLO)](https://blueteamlabs.online/)
- [RangeForce - Cyber Skills Platform](https://www.rangeforce.com/)
- [CyberDefenders - Blue Team Challenges](https://cyberdefenders.org/)
- [Splunk Fundamentals 1 (Free)](https://www.splunk.com/en_us/training/free-courses/splunk-fundamentals-1.html)

---

## 🧠 Conocimiento Técnico Fundamental

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Elastic Security (SIEM)](https://www.elastic.co/security)
- [Splunk Use Case Library](https://lantern.splunk.com/)
- [Sigma Rules (Detecciones genéricas para SIEMs)](https://github.com/SigmaHQ/sigma)
- [ThreatHunting Guide (Microsoft)](https://docs.microsoft.com/en-us/azure/sentinel/threat-hunting)

---

## 🧪 Repositorios de Datos y Logs de Prueba

- [Security Onion (Distribución para Blue Team)](https://securityonionsolutions.com/)
- [SOC Prime - Sigma Rule Repository](https://socprime.com/)
- [Log Generator para SIEMs - DeTT&CT](https://github.com/OTRF/DeTT&CT)

---

## 🛡️ Simulación y Detección

- [Atomic Red Team (Simulación de TTPs)](https://github.com/redcanaryco/atomic-red-team)
- [Invoke-AtomicRedTeam (PowerShell)](https://github.com/redcanaryco/invoke-atomicredteam)
- [Caldera by MITRE (Adversary Emulation)](https://github.com/mitre/caldera)

---

## 📖 Lectura Complementaria y Blogs

- [Malware Traffic Analysis (Logs de red y PCAPs)](https://www.malware-traffic-analysis.net/)
- [DFIR Report (Análisis reales de incidentes)](https://thedfirreport.com/)
- [Hunting Handbook by SANS](https://www.sans.org/white-papers/39590/)
- [Infosec Writeups (Blue Team Category)](https://infosecwriteups.com/)

---

## 📺 YouTube y Canales Educativos

- [John Hammond (Ciberseguridad Técnica)](https://www.youtube.com/c/JohnHammond010)
- [BlueTeamVillage (Talks y talleres)](https://www.youtube.com/c/BlueTeamVillage)
- [Security Onion YouTube Channel](https://www.youtube.com/c/SecurityOnionSolutions)

---

## 📢 Comunidades y Recursos Continuos

- [Reddit - r/BlueTeamSec](https://www.reddit.com/r/BlueTeamSec/)
- [Discord - TryHackMe Blue Team](https://discord.gg/tryhackme)
- [Twitter / X - Siguientes cuentas: @mttaggart, @chrissanders88, @cyb3rops]

---
# 🧪 Webs para Practicar Lenguajes de SIEMs

Este listado incluye plataformas donde puedes practicar las consultas que se usan comúnmente en SIEMs como **Microsoft Sentinel, Splunk, Elastic**, etc.

---

## 📘 SPL (Splunk Processing Language)

- 🔗 [Splunk Search Tutorial](https://docs.splunk.com/Documentation/Splunk/latest/SearchTutorial/WelcometotheSearchTutorial)
  - Curso oficial interactivo para aprender SPL paso a paso.
  
- 🔗 [Splunk Fundamentals 1 (Gratis)](https://www.splunk.com/en_us/training/free-courses/splunk-fundamentals-1.html)
  - Curso con ejercicios prácticos y entorno incluido.

- 🔗 [Splunk Sandbox en CyberDefenders](https://cyberdefenders.org/labs/)
  - Laboratorios con entorno real para ejecutar SPL queries.

- 🔗 [Lantern - Splunk Use Case Explorer](https://lantern.splunk.com/)
  - Biblioteca de casos de uso con consultas SPL listas para usar.

---

## 📗 KQL (Kusto Query Language – Microsoft Sentinel)

- 🔗 [KQL Tutorial by Microsoft Learn](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/)
  - Documentación oficial + playground interactivo.

- 🔗 [KQL Learn & Test](https://kusto.blob.core.windows.net/kustodocs/index.html)
  - Editor interactivo para aprender y probar KQL directamente.

- 🔗 [Microsoft Sentinel GitHub Queries](https://github.com/Azure/Azure-Sentinel)
  - Repositorio de queries reales de Sentinel (en KQL).

- 🔗 [HackTheBox - Blue Team Labs (con KQL)](https://academy.hackthebox.com/)
  - Laboratorios con consultas defensivas, incluido KQL.

---

## 📙 EQL (Elastic Query Language) / Lucene (Elastic SIEM)

- 🔗 [Elastic Security Documentation](https://www.elastic.co/guide/en/security/current/index.html)
  - Guía oficial con ejemplos de EQL y Lucene.

- 🔗 [Elastic EQL Playground](https://eqlplayground.io/)
  - *Simulador* para practicar EQL (requiere JSON de eventos).

- 🔗 [Sigma HQ - Query Samples](https://github.com/SigmaHQ/sigma)
  - Reglas Sigma con traducción a EQL, Lucene y otros lenguajes SIEM.

- 🔗 [TryHackMe - Blue Team Labs: Elastic SIEM](https://tryhackme.com/room/introtoelasticsiem)
  - Laboratorio práctico para usar EQL/Lucene en detecciones reales.

---

## 📓 Sigma Query Language (YML → SIEM)

- 🔗 [Sigma Rule Editor (Online Converter)](https://uncoder.io/)
  - Herramienta para convertir Sigma → SPL, KQL, EQL, etc.

- 🔗 [SigmaHQ - Main Repo](https://github.com/SigmaHQ/sigma)
  - Biblioteca de detecciones agnósticas, puedes practicar adaptándolas a tu SIEM.

---

## 🧠 Otras Plataformas Generales

- 🔗 [Blue Team Labs Online (BTLO)](https://blueteamlabs.online/)
  - Incluye escenarios prácticos con diferentes SIEMs y consultas.

- 🔗 [Security Onion](https://securityonionsolutions.com/)
  - Distribución defensiva con Elastic stack lista para practicar.

- 🔗 [CyberDefenders](https://cyberdefenders.org/)
  - Algunos retos requieren redactar queries (KQL/SPL).

---

> 💡 **Consejo:** Aprende primero SPL o KQL dependiendo del SIEM que uses. Luego explora EQL si trabajas con Elastic. Complementa todo con Sigma para convertir reglas entre plataformas.


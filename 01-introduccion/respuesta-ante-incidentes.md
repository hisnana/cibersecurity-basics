# 🛡️ Terminología Básica de Respuesta ante Incidentes (SOC / IR)

Esta guía resume los términos más importantes para la **respuesta ante incidentes de seguridad**, útil para analistas SOC y documentación de procedimientos.

---

## 1️⃣ Conceptos Generales
- **Incidente de seguridad**: Evento que amenaza la confidencialidad, integridad o disponibilidad de sistemas, datos o servicios.  
- **Falso positivo**: Alerta que parece un incidente pero no representa riesgo real.  
- **IOC (Indicator of Compromise / Indicador de compromiso)**: Evidencia de que un sistema ha sido comprometido (IPs, hashes de malware, URLs maliciosas).  
- **IOA (Indicator of Attack / Indicador de ataque)**: Evidencia de acciones que pueden derivar en un incidente (scripts sospechosos, cambios en configuración).  
- **TTP (Tactics, Techniques, Procedures)**: Descripción de cómo un atacante opera, según frameworks como MITRE ATT&CK.  

---

## 2️⃣ Niveles y Roles en SOC
- **Tier 1 / L1**: Analista inicial que monitorea alertas, realiza triage y clasifica incidentes.  
- **Tier 2 / L2**: Analista especializado que investiga alertas complejas y coordina escalamiento.  
- **Tier 3 / L3**: Equipo de expertos en respuesta a incidentes, threat hunting y análisis forense.  

---

## 3️⃣ Fases de la Respuesta a Incidentes
1. **Preparación**: Definir políticas, procedimientos, herramientas y entrenamiento.  
2. **Identificación**: Detectar y confirmar que un evento es un incidente.  
3. **Contención**: Limitar el impacto del incidente (temporal o permanente).  
4. **Erradicación**: Eliminar la amenaza del sistema afectado (malware, cuentas comprometidas, etc.).  
5. **Recuperación**: Restaurar sistemas y servicios a funcionamiento normal.  
6. **Lecciones aprendidas**: Documentar el incidente y ajustar procesos para prevenir futuros problemas.  

---

## 4️⃣ Herramientas y Técnicas Comunes
- **SIEM (Security Information and Event Management)**: Consolida y correlaciona logs y alertas.  
- **EDR (Endpoint Detection & Response)**: Monitoriza y protege endpoints en tiempo real.  
- **SOAR (Security Orchestration, Automation and Response)**: Automatiza procesos de respuesta y coordinación entre herramientas.  
- **TheHive / Jira / ServiceNow**: Gestión de incidentes y casos.  
- **Threat Intelligence / MISP**: Información sobre amenazas y ataques conocidos.  

---

## 5️⃣ Otros Términos Importantes
- **Escalamiento**: Transferir un incidente a un nivel superior o equipo especializado.  
- **Mitigación**: Acciones para reducir el impacto del incidente.  
- **Playbook**: Guía paso a paso de acciones a seguir ante un tipo específico de incidente.  
- **CVE (Common Vulnerabilities and Exposures)**: Base de datos de vulnerabilidades conocidas.  
- **Sandboxing**: Ejecución de archivos sospechosos en entorno seguro para análisis.  

---

## 6️⃣ CD en Ciberseguridad

**CD** significa **Continuous Delivery / Continuous Deployment** y se refiere a prácticas de **automatización del despliegue de software**.  
En ciberseguridad se aplica de la siguiente forma:

- **Continuous Delivery**: Automatiza la entrega de cambios de software a entornos de prueba y producción de forma segura y repetible.  
- **Continuous Deployment**: Lleva los cambios automáticamente a producción tras pasar todas las pruebas de seguridad y funcionalidad.  
- **Relación con ciber**:  
  - Integrar **escaneo de vulnerabilidades** en pipelines CI/CD.  
  - Automatizar **pruebas de seguridad** (SAST, DAST, container scanning).  
  - Reducir riesgo de errores humanos y vulnerabilidades en despliegues.  
  - Permite aplicar **DevSecOps**, integrando seguridad desde el desarrollo hasta la producción.  

**Herramientas comunes en CD/SecOps:** Jenkins, GitLab CI/CD, GitHub Actions, SonarQube, Trivy, Checkmarx, Aqua Security.

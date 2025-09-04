# Escalamiento de Alertas en SOC

Este procedimiento describe cómo un analista SOC de nivel 1 debe **escalar una alerta** cuando, tras la investigación inicial, se determina que no puede resolverse de manera autónoma o requiere intervención de un equipo especializado (Tier 2, incident response, gestión de vulnerabilidades, etc.).

Incluye criterios de escalamiento, pasos concretos, herramientas y registros que se deben documentar.

---

## 📝 Criterios para escalar
- Incidentes de **alta criticidad** o con impacto potencial importante.  
- Alertas que **no pueden resolverse con información disponible**.  
- Incidentes que requieren **acción fuera del alcance de Tier 1** (p. ej. cambios en firewall, contención de endpoint).  
- **Patrones nuevos** o sospechas de APT/ataque dirigido.  

---

## 🔄 Pasos para el escalamiento

1. **Validar alerta**: confirmar que no es un falso positivo.  
2. **Recopilar evidencia**:  
   - Logs relevantes  
   - Capturas de red o endpoint  
   - IOC detectados  
   - Screenshots si es necesario  
3. **Documentar en el sistema de gestión** (TheHive, Jira, ServiceNow):  
   - Descripción de la alerta  
   - Evidencia recopilada  
   - Acciones realizadas  
   - Nivel de criticidad y contexto  
4. **Notificar al equipo escalado**:  
   - Asignar al analista de Tier 2 correspondiente  
   - Adjuntar toda la información y evidencia  
   - Incluir información de contacto para seguimiento  
5. **Seguimiento del caso**:  
   - Confirmar que el equipo escalado ha recibido y entendido la alerta  
   - Actualizar el ticket si se necesita información adicional  

---

## 🛠️ Herramientas recomendadas
- **TheHive**: creación y seguimiento de casos.  
- **Jira / ServiceNow**: seguimiento interno y registro de incidencias.  
- **SIEM / EDR**: exportar logs y evidencias.  
- **Threat Intelligence (MISP, VirusTotal)**: para añadir contexto adicional.  

---

## 💡 Notas y buenas prácticas
- Nunca escalar sin evidencia suficiente: documentar todo lo que se ha revisado.  
- Mantener comunicación clara con el equipo escalado.  
- Actualizar el ticket o caso con todas las acciones y hallazgos.  
- Revisar y aprender de cada escalamiento para mejorar reglas de detección y procedimientos internos.  

---

## 🖼️ Diagrama de flujo 



```mermaid
flowchart TD
    Alerta[Recibe alerta] --> Validar[Validar si es falso positivo]
    Validar -->|Sí| Cerrar[Falso positivo / cierre]
    Validar -->|No| Recopilar[Recopilar evidencia]
    Recopilar --> Documentar[Documentar en TheHive / Jira]
    Documentar --> Notificar[Notificar al equipo Tier 2 / área afectada]
    Notificar --> Seguimiento[Confirmar recepción y seguimiento]
    Seguimiento --> Cierre[Actualizar caso y cerrar]

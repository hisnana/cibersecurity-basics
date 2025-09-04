
# 📝 Generación y Gestión de Reportes en SOC

Este procedimiento describe cómo un analista SOC debe **generar, revisar y entregar reportes** de alertas e incidentes.  
Incluye los tipos de reportes, contenido recomendado, herramientas y buenas prácticas para mantener trazabilidad y calidad en la gestión de la información.

---

## 📂 Tipos de reportes

- **Reportes de alertas diarias**  
  - Resumen de todas las alertas revisadas en el día.  
  - Indicadores: número de alertas, criticidad, falsos positivos.  

- **Reportes de incidentes**  
  - Descripción completa de incidentes escalados o mitigados.  
  - Evidencias recopiladas, medidas aplicadas, responsables.  

- **Reportes de tendencias y métricas**  
  - Análisis semanal/mensual: patrones de ataques, falsos positivos frecuentes, tiempos de respuesta.  
  - Base para optimizar reglas de detección y procedimientos internos.  

---

## 📄 Contenido recomendado para cada reporte

- **Identificación del incidente / alerta**  
  - ID del ticket / caso en TheHive o Jira  
  - Fecha y hora de detección  
  - Fuente de la alerta (SIEM, EDR, logs)  

- **Descripción del evento**  
  - Qué ocurrió, cómo se detectó, y contexto del incidente  

- **Análisis realizado**  
  - Evidencia recopilada  
  - Evaluación de impacto  
  - Determinación de criticidad  

- **Acciones realizadas**  
  - Escalamiento (si aplica)  
  - Medidas de mitigación o contención  
  - Notificaciones enviadas  

- **Resultados y cierre**  
  - Estado final del caso (resuelto, falso positivo, pendiente)  
  - Recomendaciones para evitar incidentes similares  

- **Referencias / Evidencias**  
  - Logs, capturas, IOC, capturas de pantalla  

---

## 🛠️ Herramientas recomendadas

- **TheHive** → creación de tickets y casos  
- **Jira / ServiceNow** → seguimiento y documentación  
- **Excel / Google Sheets / Power BI** → métricas y reportes de tendencias  
- **SIEM / EDR dashboards** → extracción de información y evidencia  
- **Threat Intelligence** → añadir contexto de IOC o campañas conocidas  

---

## 💡 Buenas prácticas

- Generar reportes de manera **consistente y diaria** para mantener trazabilidad.  
- Incluir **evidencia mínima necesaria**: no dejar vacíos en los reportes.  
- Revisar reportes antes de enviarlos a áreas externas o clientes.  
- Mantener los reportes archivados y accesibles para auditorías o revisiones internas.  
- Normalizar formatos y nomenclaturas para facilitar lectura y análisis.  

---

## 🖼️ Diagrama de flujo sugerido

```mermaid
flowchart TD
    Alerta[Recepción de alerta / incidente] --> Validar[Validar y confirmar relevancia]
    Validar -->|No relevante| Cerrar[Falso positivo / cierre]
    Validar -->|Relevante| Analizar[Analizar y recopilar evidencia]
    Analizar --> Documentar[Documentar en TheHive / Jira]
    Documentar --> Generar[Generar reporte diario / incidente]
    Generar --> Revisar[Revisar y aprobar]
    Revisar --> Entregar[Entregar a áreas internas o clientes]
    Entregar --> Archivo[Archivar y mantener registro]
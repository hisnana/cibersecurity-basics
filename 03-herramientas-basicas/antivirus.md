# 🛡️ Herramientas de Antivirus / Endpoint Protection

Los antivirus y soluciones EDR son fundamentales para la **detección y respuesta temprana** de malware, ataques dirigidos y amenazas persistentes en endpoints.

---

## 🔹 Funciones principales
- Detección y bloqueo de malware (virus, troyanos, ransomware, spyware).  
- Monitoreo en tiempo real de actividad sospechosa en endpoints.  
- Cuarentena automática de archivos o procesos maliciosos.  
- Integración con SIEM y SOAR para automatizar alertas y respuestas.  
- Generación de logs de eventos de seguridad para análisis posterior.  

---

## 🔹 Herramientas recomendadas

| Herramienta                  | Tipo             | Comentarios / Integración SOC                       |
|-------------------------------|----------------|----------------------------------------------------|
| **CrowdStrike Falcon**        | EDR / Cloud     | Protección avanzada de endpoints, detección de TTP, integración con SIEM y SOAR |
| **SentinelOne**               | EDR / Cloud     | Detección autónoma de malware, respuesta automática, visibilidad completa del endpoint |
| **Microsoft Defender for Endpoint** | EDR / Antivirus | Integración nativa con Windows, detección en tiempo real, reporting en Microsoft 365 |
| **Carbon Black (VMware)**     | EDR             | Análisis de comportamiento y respuesta, threat hunting |
| **Sophos Intercept X**        | Antivirus / EDR | Prevención de exploits, ransomware y malware avanzado |
| **ClamAV**                    | Antivirus Open Source | Detección básica de malware en servidores Linux/Windows, útil en pipelines CI/CD |

---

## 🔹 Buenas prácticas de uso
- Mantener la **base de firmas y motores actualizados**.  
- Configurar **alertas automáticas hacia SIEM / SOAR**.  
- Revisar periódicamente **logs de detección y cuarentena**.  
- Combinar con **Threat Intelligence** para enriquecer IOC/IOA.  
- Integrar en **playbooks de respuesta** para agilizar contención y mitigación.  

---

💡 **Tip:** Los EDR modernos no solo actúan como antivirus; permiten correlacionar eventos, ejecutar scripts de contención y alimentar plataformas SOAR para automatizar la respuesta.

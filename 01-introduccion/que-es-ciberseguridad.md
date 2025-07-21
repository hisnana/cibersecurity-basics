
# ¿Qué es la Ciberseguridad?

La **ciberseguridad** es el conjunto de prácticas, tecnologías y procesos diseñados para proteger sistemas, redes y datos digitales contra accesos no autorizados, ataques, daños o robos.

---

## ¿Por qué es importante la ciberseguridad?

En un mundo cada vez más conectado, la información digital es uno de los activos más valiosos. Protegerla evita:

- **Robo de información sensible** (datos personales, financieros, empresariales).
- **Interrupciones en servicios y operaciones**.
- **Fraudes y pérdidas económicas**.
- **Daños a la reputación de empresas y usuarios**.

---

## Áreas principales de la ciberseguridad

- **Seguridad de redes:** Protección de las conexiones y comunicaciones.
- **Seguridad de sistemas:** Defensa de los equipos y servidores.
- **Seguridad de aplicaciones:** Garantizar que el software funcione sin vulnerabilidades.
- **Gestión de identidad y accesos:** Controlar quién puede acceder a qué.
- **Respuesta a incidentes:** Actuar rápidamente ante ataques o fallos.

---

## Rol de las personas en la ciberseguridad

La mayoría de los incidentes ocurren por errores humanos. Por eso, la **conciencia y formación** de usuarios y equipos de soporte es clave para mantener un entorno seguro.
**El mayor vector de ataque en las empresas es los usuarios, los ataques de phishing(envio de emails que roban datos) es el mayor vector de entrada a una empresa.**


# Fundamentos de la Ciberseguridad: CIA, Autenticación y Autorización

## 🔺 El Triángulo CIA

El modelo **CIA** es la base fundamental de la ciberseguridad. Representa tres principios que toda estrategia de protección debe garantizar:

| Pilar              | Descripción                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Confidencialidad** | Garantiza que solo las personas autorizadas puedan acceder a la información. Se logra con cifrado, autenticación, control de accesos, etc. |
| **Integridad**       | Asegura que los datos no han sido alterados de forma no autorizada. Se logra con hashes, firmas digitales, controles de cambios. |
| **Disponibilidad**   | Garantiza que los sistemas y datos estén accesibles cuando se necesiten. Se protege con backups, redundancia, protección contra ataques como DDoS. |

---

## 🔐 Autenticación y Autorización

Aunque **autenticación** y **autorización** no forman parte directa del triángulo CIA, son esenciales para **garantizar la confidencialidad** y el control de acceso:

| Concepto          | Descripción                                                             |
|-------------------|-------------------------------------------------------------------------|
| **Autenticación** | Verifica la identidad del usuario o sistema. Ejemplo: login con contraseña o MFA. |
| **Autorización**  | Determina qué recursos o acciones están permitidos a ese usuario autenticado. Ejemplo: acceso de solo lectura o escritura. |

---

## 📌 Relación entre conceptos

| Concepto         | Relacionado con...   | Ejemplo práctico                                |
|------------------|----------------------|--------------------------------------------------|
| Autenticación    | Confidencialidad     | El usuario se identifica con su contraseña       |
| Autorización     | Confidencialidad     | El sistema permite o deniega acceso a un recurso |
| Confidencialidad | Pilar del CIA        | Archivos cifrados y acceso restringido           |
| Integridad       | Pilar del CIA        | Comparación de hashes para verificar archivos    |
| Disponibilidad   | Pilar del CIA        | Servidores operativos y redundantes              |


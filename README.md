# 🤖 Proyecto_IA

## HelpDeskBot – Asistente Automatizado de Soporte Interno


---

##  Descripción General

**HelpDeskBot** es un bot conversacional diseñado para gestionar solicitudes internas de soporte de manera rápida, organizada y eficiente.

Permite registrar:

*  Incidentes técnicos
*  Solicitudes administrativas
*  Consultas generales

Todo esto mediante **flujos conversacionales guiados**, automatización básica y una experiencia clara para el usuario.

> El bot no toma decisiones autónomas ni utiliza aprendizaje automático.
> Su función principal es **organizar, registrar y presentar información** de forma estructurada.

---

##  Tecnologías Utilizadas

*  **Telegram** → Canal de comunicación principal
*  **n8n Community Edition** → Motor de automatización y lógica
*  **Google Sheets** → Base de datos ligera / persistencia
*  **Ngrok** → Exposición local para pruebas webhook

---

##  Funcionamiento General

HelpDeskBot guía al usuario mediante **opciones numéricas simples**, menús claros y mensajes humanizados.

###  Mensaje de Bienvenida

```text
Hola, soy HelpDeskBot 👋

Estoy aquí para ayudarte con solicitudes de soporte
de forma rápida y ordenada.

Por favor escribe el número de la opción que quieras usar.

Menú principal:
0. Ayuda
1. Crear solicitud
2. Consultar estado de solicitud
3. Mis solicitudes
4. Reportes
5. Configuración
```

---

##  Modelo de Datos (Google Sheets)

Documento principal:

```text
HelpDeskBot_DB
```

###  Hoja: SOLICITUDES

| Campo          | Descripción                    |
| -------------- | ------------------------------ |
| id_ticket      | ID único del ticket            |
| tipo           | Tipo de solicitud              |
| prioridad      | Alta / Media / Baja            |
| descripcion    | Detalle del caso               |
| estado         | Abierto / En proceso / Cerrado |
| creado_por     | Usuario creador                |
| fecha_creacion | Fecha de registro              |

---

###  Hoja: USUARIOS

| Campo         | Descripción    |
| ------------- | -------------- |
| telegram_user | ID Telegram    |
| nombre        | Nombre usuario |
| rol           | Cargo / Perfil |
| activo        | Sí / No        |

---

###  Hoja: LOGS

| Campo         | Descripción      |
| ------------- | ---------------- |
| timestamp     | Fecha y hora     |
| telegram_user | Usuario          |
| pantalla      | Menú visitado    |
| opcion        | Opción elegida   |
| resultado     | Acción ejecutada |

---

##  Flujo Conversacional

##  Crear Solicitud

```text
Vamos a crear una solicitud.

Selecciona el tipo:

1. Soporte técnico
2. Solicitud administrativa
3. Consulta general
9. Cancelar
```

### Wizard Guiado

1. Tipo de solicitud
2. Prioridad
3. Descripción
4. Confirmación
5. Registro automático
6. Mensaje de éxito

---

##  Automatizaciones Implementadas

 Registro automático del ticket
 Cambio de estado automático
 Notificación básica por Telegram o correo
 Registro de acciones en LOGS
 Consulta de tickets existentes
 Historial del usuario

---

##  Validaciones

El sistema valida:

* Campos obligatorios
* Prioridad válida
* Usuario activo
* Confirmación antes de guardar
* Cancelación segura de procesos

---

##  Beneficios del Proyecto

* Reduce tiempos de atención
* Centraliza solicitudes internas
* Mejora trazabilidad
* Automatiza tareas repetitivas
* Facilita seguimiento de tickets
* Escalable a futuras mejoras con IA real

---

##  Estado del Proyecto

 En desarrollo / pruebas internas

---

##  Vista del Flujo en n8n

> Automatización principal desarrollada visualmente en n8n

![Flujo Principal](img/captura-n8n.png)

---

##  Autor

Desarrollado como proyecto académico / automatización interna usando herramientas no-code + lógica conversacional.

---

##  Futuras Mejoras

* Panel web administrativo
* Métricas avanzadas
* Integración con correo corporativo
* IA para clasificación automática
* Base de conocimientos interna
* Dashboard en tiempo real

---

##  Licencia

Uso educativo / demostrativo.

# Chatbot de To-Do: Sistema de Organización Personal en Telegram con Firebase

## Descripción del Proyecto
Este es un chatbot de **To-Do** diseñado para ayudar a los usuarios a gestionar tareas de manera eficiente a través de **Telegram** y utilizando **Firebase** como base de datos para el almacenamiento en la nube. El bot permite a los usuarios crear, eliminar y listar tareas, establecer recordatorios, y organizar las tareas según prioridades. Es una herramienta ideal para mejorar la productividad y organización personal mediante una interfaz de mensajería accesible.

## 1. **Resumen del Proyecto**
El **Chatbot de To-Do** es una herramienta interactiva ejecutada en Telegram que ayuda a los usuarios a gestionar tareas y recordatorios de manera eficiente. El chatbot permite agregar, eliminar y listar tareas pendientes, establecer recordatorios, y categorizarlas por prioridades. **Firebase** se usará como backend para almacenar y sincronizar tareas de manera eficiente.

## 2. **Objetivos**
- **Gestión de tareas**: Permitir al usuario crear, eliminar y actualizar tareas a través de comandos en Telegram.
- **Categorías y prioridades**: Clasificar las tareas por categorías (trabajo, estudio, hogar) y niveles de prioridad (alta, media, baja).
- **Recordatorios automáticos**: Enviar notificaciones en Telegram para recordar las fechas límite o el vencimiento de tareas.
- **Lista de tareas filtrada**: Ofrecer al usuario una vista filtrada de las tareas según prioridad o vencimiento.
- **Seguimiento de progreso**: Mostrar al usuario el progreso de las tareas completadas mediante actualizaciones en el chat.

## 3. **Características Principales**

### 3.1 **Agregar tareas**
- **Función**: Permitir a los usuarios agregar nuevas tareas con una descripción, fecha límite y prioridad.
- **Formato de Comando**: 
  - `/agregar [Descripción] para [Fecha] con prioridad [alta/media/baja]`
- **Ejemplo**: `/agregar "Terminar reporte" para "15 de marzo" con prioridad alta`.

### 3.2 **Eliminar tareas**
- **Función**: Eliminar una tarea de la lista del usuario.
- **Formato de Comando**: 
  - `/eliminar [Número/Descripción]`
- **Ejemplo**: `/eliminar 1` o `/eliminar "Terminar reporte"`.

### 3.3 **Listar tareas**
- **Función**: Mostrar una lista de todas las tareas con la opción de filtrar por fecha de vencimiento o prioridad.
- **Formato de Comando**: 
  - `/listar [Filtro]`
- **Filtros posibles**: 
  - Sin filtro (muestra todas las tareas).
  - Por prioridad (`alta`, `media`, `baja`).
  - Por fecha de vencimiento (`hoy`, `esta semana`, `este mes`).
- **Ejemplo**: `/listar` o `/listar prioridad alta`.

### 3.4 **Recordatorios**
- **Función**: Enviar recordatorios automáticos antes de las fechas límite.
- **Comportamiento**: El chatbot recordará al usuario una tarea 1 día antes y el mismo día del vencimiento.

### 3.5 **Actualizar tareas**
- **Función**: Permitir modificar la descripción, fecha o prioridad de una tarea existente.
- **Formato de Comando**: 
  - `/actualizar [Número/Descripción] con [Nueva descripción/Nueva fecha/Nueva prioridad]`.
- **Ejemplo**: `/actualizar 1 con nueva fecha 16 de marzo`.

## 4. **Arquitectura Técnica**

### 4.1 **Tecnologías**
- **Lenguaje de programación**: Python.
- **Plataforma de chat**: Telegram.
- **Framework**: `python-telegram-bot` para la interacción con Telegram.
- **Base de datos**: Firebase Realtime Database o Firestore para el almacenamiento de tareas y datos del usuario.

### 4.2 **Integración con Firebase**
Se utilizará **Firebase** como base de datos para almacenar:
- **ID de usuario**: Cada usuario de Telegram tendrá un ID único.
- **Tareas**: Se almacenarán las tareas de cada usuario con descripción, fecha de vencimiento, y prioridad.
- **Estados**: El estado de cada tarea (completada o pendiente).
- **Historial**: Registros de creación y modificación de tareas.

### 4.3 **Persistencia de Datos**
Firebase permitirá la sincronización en tiempo real de las tareas, asegurando que los usuarios puedan acceder a sus tareas desde cualquier dispositivo. Los datos clave a almacenar incluyen:
- Descripción de la tarea.
- Fecha de vencimiento.
- Prioridad de la tarea.
- Estado (completada o no completada).

## 5. **Consideraciones Futuras**
- **Integración con Google Calendar**: Sincronizar tareas con eventos de Google Calendar.
- **Multiusuario**: Mejorar el soporte para múltiples usuarios simultáneos, asegurando que las tareas se almacenen y gestionen de forma aislada entre usuarios.
- **Tareas recurrentes**: Agregar soporte para tareas que se repitan a diario, semanalmente o mensualmente.

## 6. **Despliegue**
El chatbot será alojado en un servidor y estará disponible a través de la API de Telegram. Se usará **Firebase** para el almacenamiento de datos, con el proyecto desplegado usando `Docker` para facilitar la configuración. 

### Pasos de Despliegue:
1. Configurar el proyecto en Firebase y obtener las credenciales necesarias.
2. Integrar el SDK de Firebase con el código del bot en Python.
3. Configurar el despliegue automático mediante Docker.

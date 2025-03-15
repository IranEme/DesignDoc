# CHATBOT TO-DO SYSTEM DESIGN DOC  
**Link**: N/A

**Author(s)**: Juan Iran López Mercado

**Status**: Draft

**Ultima actualización**: 2025-03-15

## Contenido
- [Objetivo](#objetivo)
- [Goals](#goals)
- [Non-Goals](#non-goals)
- [Background](#background)
- [Overview](#overview)
- [Detailed Design](#detailed-design)
  - [Solucion 1](#solucion-1)
    - [Frontend](#frontend-1)
    - [Backend](#backend-1)
  - [Solucion 2](#solucion-2)
    - [Frontend](#frontend-2)
    - [Backend](#backend-2)
- [Consideraciones](#consideraciones)
- [Métricas](#métricas)
- [Links](#links)

## Objetivo
**¿Qué y por qué estamos haciendo esto?**

Este proyecto busca crear un chatbot en Telegram para organizar tareas (to-do) mediante una interfaz simple y accesible. El objetivo es automatizar la gestión de tareas y recordar al usuario sus actividades, mejorando la productividad y organización diaria. Firebase se utilizará como la base de datos para almacenar y gestionar las tareas de manera eficiente.

## Goals
- Crear un chatbot funcional en Telegram que ayude al usuario a gestionar tareas.
- Implementar una interfaz sencilla y amigable para interactuar con el chatbot.
- Integrar funcionalidades de recordatorio de tareas.
- Utilizar Firebase como base de datos para almacenar y recuperar las tareas.

## Non-Goals
- Desarrollar una aplicación móvil o web completa para la gestión de tareas.
- Implementar sistemas de inteligencia artificial avanzados para predicción de tareas.
- Integrar con plataformas de terceros como Google Calendar o Trello.

## Background
Este proyecto se enmarca dentro de la necesidad de automatizar y optimizar la gestión de tareas personales. Muchas personas tienen dificultades para organizar sus actividades diarias, y un chatbot simple puede proporcionar una solución eficaz. El chatbot operará en Telegram, y utilizará Firebase como backend para almacenar las tareas del usuario y proporcionar una sincronización en tiempo real.

## Overview
El chatbot será capaz de recibir comandos desde Telegram y gestionar tareas como añadir, eliminar, o listar tareas pendientes. Las tareas se almacenarán en Firebase, y el chatbot notificará al usuario acerca de sus actividades programadas.

## Detailed Design
La arquitectura del sistema se dividirá en dos componentes principales: Frontend y Backend.

### Solucion 1
#### Frontend
El frontend consistirá en un bot que se implementará en Telegram. Utilizaremos la [API de Telegram](https://core.telegram.org/bots/api) para recibir comandos y responder de forma interactiva. El bot interactuará con el usuario mediante mensajes de texto simples.

#### Backend
El backend se gestionará en Firebase, utilizando Firebase Realtime Database o Firestore para almacenar y recuperar las tareas. Firebase proporcionará una sincronización en tiempo real entre el servidor y los usuarios, y gestionará el almacenamiento de datos de manera escalable.

### Solucion 2
#### Frontend
Se desarrollará una interfaz sencilla de texto donde los usuarios puedan escribir comandos como "Añadir tarea", "Listar tareas", y "Eliminar tarea". El chatbot responderá con las tareas actuales o la confirmación de la acción ejecutada.

#### Backend
El backend se implementará utilizando Firebase para almacenar tareas. Se utilizarán las funcionalidades de Firebase Authentication para autenticar a los usuarios y Firebase Realtime Database o Firestore para gestionar las tareas. El sistema permitirá la manipulación de tareas y la programación de recordatorios.

## Consideraciones
- **Preocupaciones**: Se debe considerar el manejo de errores si el chatbot recibe comandos incorrectos o si no se pueden agregar tareas.
- **Tech Debt**: Usar Firebase puede implicar una dependencia externa que podría generar deuda técnica si el sistema escala mucho. Se debe monitorear el uso de las funciones en tiempo real.
- **Trade-offs**: La simplicidad del diseño con Firebase puede limitar algunas funcionalidades avanzadas que se podrían agregar en el futuro, como la integración con otros servicios o la personalización de recordatorios.

## Métricas
- **Tasa de éxito de comandos**: ¿Cuántos comandos el chatbot maneja correctamente?
- **Tiempo de respuesta**: ¿Cuánto tiempo tarda el chatbot en responder a las consultas del usuario?
- **Satisfacción del usuario**: Se evaluará la experiencia del usuario mediante retroalimentación directa o encuestas.
- **Uso de la base de datos**: Medir cuántas tareas se crean, actualizan y eliminan, para determinar la eficiencia del sistema con Firebase.

## Links
- [Enlace al repositorio del proyecto](https://github.com/IranEme/DesignDoc/)
- [Documentación de la API de Telegram](https://core.telegram.org/bots/api)
- [Documentación de Firebase](https://firebase.google.com/docs)

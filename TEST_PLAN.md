# 📋 Test Plan: Restful-Booker API

## 1. Introducción
Este documento define los requisitos funcionales y de seguridad para la API Restful-Booker.

## 2. Requisitos Funcionales (El "Qué" se debe probar)

### REQ-01: Autenticación
- El sistema debe permitir la autenticación de usuarios administradores.
- **Entrada:** `username`, `password`.
- **Salida:** Token de sesión válido.

### REQ-02: Gestión de Reservas (CRUD)
- El sistema debe permitir la creación, consulta, actualización y eliminación de reservas.
- **Validación:** Cada reserva debe tener un ID único y asociado a datos válidos (nombre, apellido, precio, fechas).

### REQ-03: Seguridad y Negativa
- La API debe denegar el acceso a funciones protegidas (como Borrar/Actualizar) si no se provee un Token válido.
- **Código esperado:** 403 Forbidden.

## 3. Criterios de Aceptación
- Todas las pruebas deben devolver un código HTTP 200/201 para flujos exitosos.
- Los tiempos de respuesta (Latency) deben ser inferiores a 1000ms.
- El formato de respuesta debe ser JSON estricto.

## 4. Entorno de Pruebas
- **Base URL:** `https://restful-booker.herokuapp.com`

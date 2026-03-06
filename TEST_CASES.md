# 🧪 Casos de Prueba (Test Cases)

## TC-01: Autenticación (Auth)
* **Objetivo:** Validar que el usuario 'admin' obtenga un token válido.
* **Pasos:**
    1. Enviar POST a `https://restful-booker.herokuapp.com/auth`
    2. En el Body (JSON) poner: {"username": "admin", "password": "password123"}
* **Resultado Esperado:** Código 200 OK y una respuesta que contenga un campo "token".

## TC-02: Crear Reserva (Booking)
* **Objetivo:** Validar que se pueda crear una reserva nueva.
* **Pasos:**
    1. Enviar POST a `https://restful-booker.herokuapp.com/booking`
    2. En el Body (JSON) poner: 
       {
         "firstname" : "Jim",
         "lastname" : "Brown",
         "totalprice" : 111,
         "depositpaid" : true,
         "bookingdates" : { "checkin" : "2026-01-01", "checkout" : "2026-01-02" }
       }
* **Resultado Esperado:** Código 200 OK y un "bookingid" generado.
* 
* ## TC-03: Consultar Reserva (GET)
* **Objetivo:** Verificar que se puede obtener la información de una reserva específica.
* **Pasos:** 1. Enviar GET a `https://restful-booker.herokuapp.com/booking/{id}` (usa el id que obtuviste en el TC-02).
* **Resultado Esperado:** Código 200 OK y que los datos coincidan con los ingresados.

## TC-04: Borrar Reserva (DELETE - Caso de Seguridad)
* **Objetivo:** Validar que no se pueda borrar sin token.
* **Pasos:**
    1. Enviar DELETE a `https://restful-booker.herokuapp.com/booking/{id}` sin enviar el Token.
* **Resultado Esperado:** Código 403 Forbidden.

## TC-05: Validación de Campos Vacíos (Negative Testing)
* **Objetivo:** Validar que la API maneje errores si falta el nombre.
* **Pasos:**
    1. Enviar POST a `/booking` enviando el JSON vacío `{}`.
* **Resultado Esperado:** Código 400 Bad Request o 500 (según el manejo de errores de la API).

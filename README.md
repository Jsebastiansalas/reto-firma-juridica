# Firma Jurídica - Base de Datos

## Interpretación del problema
El sistema sirve para gestionar los asuntos legales que maneja una firma jurídica para sus clientes. Resuelve la desorganización y permite llevar los casos de manera más fácil y ordenada.

## Identificación de entidades y atributos

**Cliente**
- DNI (PK)
- nombre
- dirección
- fecha de nacimiento

**Asuntos Legales**
- numero_expediente (PK)
- fecha de inicio
- fecha de finalización
- estado del caso (en proceso, cerrado, suspendido)

**Procuradores**
- DNI (PK)
- nombre
- apellidos
- numero de colegiado
- numero de casos ganados

## Justificación de relaciones y cardinalidades

- **Cliente - Asunto (1:N):** Un cliente puede tener muchos asuntos, pero un asunto no puede pertenecer a muchos clientes.
- **Procurador - Asunto (N:M):** Un procurador puede llevar muchos asuntos y un asunto puede tener muchos procuradores.

## Transformación al modelo relacional
Las 3 entidades se convirtieron en 3 tablas y sus atributos en columnas. Para la relación 1:N se agregó la clave foránea DNI_cliente dentro de la tabla Asuntos Legales.

## Decisiones tomadas
Se creó una tabla intermedia llamada **asunto_procurador** para resolver la relación N:M entre Procuradores y Asuntos. Esta tabla contiene las claves foráneas de ambas tablas y su clave primaria es compuesta por DNI_procurador y numero_expediente.
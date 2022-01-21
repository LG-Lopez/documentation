---
title: QoS
date: 2022-01-19T15:55:46-05:00
description: >
  Atributos del SLD (Definición del nivel de servicio) del servicio.
---
## Operaciones

### confirmarEstadoTransferenciaRecibida

#### Controles de seguridad a nivel de mensaje
|Identificación y autenticación|Autorización|Confidencialidad|Integridad|Auditabilidad|
|-|:-:|:-:|:-:|:-:|
|Por medio del ChannelAdapter de MQ y a traves del usuario de conexión y certificado digital|Por medio del Registry a nivel de servicio|Por SSL entre el cliente y MQ|SSL|Auditabilidad por medio de logs del gestor de colas|
|

#### Desempeño y disponibilidad
| Nombre de la operación|Transacciones soportadas por segundo|Tiempo de respuesta máximo en segundos|Tiempo de respuesta promedio en segundos|Horario disponible|
|-|-|-|-|-|
|confirmarEstadoTransferenciaRecibida|10|30|2|7 días desde las 5:00 - 22:00|
|
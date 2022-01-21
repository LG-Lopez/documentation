---
title: Hoja de Datos
date: 2022-01-19T15:55:46-05:00
description: >
  A short lead description about this content page. It can be **bold** or _italic_ and can be split over multiple paragraphs.
---
## WebSphere MB - activo/activo

### Proyecto: SWIFT GPI

PMO31494

Analista: Yuliana Giraldo Morales

| Ambiente | DESARROLLO | CERTIFICACIÓN | PRODUCCIÓN |
|-|:-:|:-:|:-:|
| F5 HTTPS | https://esbdev.bancolombia.corp:3310/ESB/SOAP/Default | https://esbqa.bancolombia.corp:3310/ESB/SOAP/Default | https://esbpro.bancolombia.corp:3310/ESB/SOAP/Default |
| Máquina | Nodo 1 -> pbmdebdmeb02 (10.8.87.145)  |Nodo 2 -> pbmdebdmeb03 (10.8.87.146) | Nodo 1 -> pbmdebqmeb03 (10.8.73.184) Nodo 2 -> pbmdebqmeb04 (10.8.73.185) | pbmdebpmeb07 [Bus] [10.8.16.193]  pbmdebpmeb08 [Bus] [10.8.16.194]   pbmdebpamq01 [Bus] [10.8.16.238]  pbmdebpamq02 [Bus] [10.8.16.239] |
| DNS y puerto para establecer conexión | DCOLQMGRBUS01 (1422) DCOLQMGRBUS02 (1423) | CCOLQMGRBUS01 (1422) CCOLQMGRBUS02 (1423) | PCOLQMGRBUS01 (1422)  PCOLQMGRBUS02 (1423) PCOLQMGRBUS03 (1424) PCOLQMGRBUS04 (1425) |
| Bróker, gestor de colas y puerto |DCOLBUS01   - DCOLQMGRBUS01  (1422)  DCOLBUS02   - DCOLQMGRBUS02  (1423) | CCOLBUS01   - CCOLQMGRBUS01  (1422) CCOLBUS02   - CCOLQMGRBUS01  (1422) |PCOLBUS01 - PCOLQMGRBUS01 (1422) PCOLBUS02 - PCOLQMGRBUS02 (1423) PCOLBUS03 - PCOLQMGRBUS03 (1424) PCOLBUS04 - PCOLQMGRBUS04 (1425)|
| |

|COLAS|
|-|

|Tipo | Nombre y descripción | Profundidad (cantidad máxima de mensajes) | Tamaño máximo del mensaje (por defecto 4MB) | Persistencia (marque) | Cluster (marque) | Tipo enlace (seleccione) | Cluster Workload (marque) |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Local | INT_GESTIONTRANSINTERNACIONALESV2_INT.QL.REQ (Cola de entrada del servicio) | 5000 | 4MB |  | X | Sin fijar | Local | 
| Local | INT_GESTIONTRANSINTERNACIONALESV2_INT.QL.CBK (Cola de Salida del servicio) | 5000 | 4MB |  | X | Sin fijar | Local | 
| Local | INT_IASWIFTGPI_V2_INT.QL.REQ (Cola de entrada IA REST SwiftGPI V2) | 5000 | 4MB |  | X | Sin fijar | Local | 

|FLUJOS|
|-|

| Área funcional dueña del servicio (CDE) | Nombre del artefacto de despliegue | Nombre del flujo | Colas relacionadas | Volumen transaccional (mensajes x min) | Tiempo respuesta esperado (ms) | Tipo de componente | Web Service (marque) | Cantidad de instancias adicionales (hilos) | Nombre de los grupos de ejecución | Listeners (http) (https) |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| CDE | AW0290_GestionTransferenciasInternacionalesV2_DFDL.bar | com.bancolombia.ca.iast.GestionTransferenciasInternacionales | INT_GESTIONTRANSINTERNACIONAL_IC_IAST_INT.QL.REQ INT_GESTIONTRANSINTERNACIONAL_IC_IAST_INT.QL.CBK | 1000 | 5000 | Consumer DFDL | | 0 | SWIFTGPI_01 | | 
| CDE | AW0290_GestionTransferenciasInternacionV2_IIB10.bar | Producto.MonedaExtranjera.ComercioExterior.GestionTransferenciasInternacionales.GestionTransferenciasInternacionalesRequest_SM | INT_GESTIONTRANSINTERNACIONALESV2_INT.QL.REQ INT_GESTIONTRANSINTERNACIONALESV2_INT.QL.CBK | 1000 | 5000 | Service Mediator | | 0 | SWIFTGPI_01 | |
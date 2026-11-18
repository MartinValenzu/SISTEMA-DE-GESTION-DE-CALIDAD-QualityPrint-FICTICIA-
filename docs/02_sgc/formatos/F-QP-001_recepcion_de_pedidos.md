# F-QP-001 — Formato de recepción de pedidos

| Campo de control documental | Información |
|---|---|
| Código | F-QP-001 |
| Versión | 1.0 |
| Fecha | 18/11/2026 |
| Estado | **Formato aprobado para el proyecto académico** |
| Actividad | 2.8.5 — Formato de recepción de pedidos |
| Responsable | Comercial y diseño |
| Procedimiento asociado | [PR-QP-001 — Recepción de pedidos](../procedimientos/PR-QP-001_recepcion_de_pedidos.md) |

**Uso:** completar un formato por pedido, conservar cada revisión y adjuntar las evidencias de aceptación. Los espacios vacíos no representan pedidos reales. Para el portafolio se utilizarán únicamente datos ficticios.

## 1. Identificación del pedido

| Campo | Dato |
|---|---|
| ID de pedido | |
| Versión de requisitos | |
| Fecha y hora de solicitud | |
| Canal de recepción | |
| ID o nombre del cliente | |
| Contacto del cliente (ficticio en demostraciones) | |
| Responsable comercial | |
| Fecha solicitada de entrega | |
| Fecha acordada de entrega | |
| Modalidad (recolección / envío) | |
| Destino o punto de entrega | |
| Condiciones especiales | |

## 2. Detalle de prendas

Una fila por combinación de producto, tejido, color, talla y conjunto de estampados. Si una prenda lleva varios estampados, registrar su cantidad una sola vez y asociar todos sus diseños en la sección 3.

| N.º línea | Producto | Tejido | Color | Talla | Cantidad (unidades) | ID(s) de diseño |
|---|---|---|---|---|---:|---|
| | | | | | | |
| | | | | | | |
| | | | | | | |

**Cantidad total del pedido:** __________ unidades.

## 3. Especificaciones del diseño

Una fila por estampado, incluyendo los adicionales de una misma prenda. Vincular cada diseño a la línea correspondiente.

| ID de diseño | Línea(s) de pedido | Versión del arte | Referencia del archivo | Posición y orientación | Ancho (cm) | Alto (cm) | Tolerancia dimensional (cm) | Referencia de posición y tolerancia (cm / grados si aplica) | Referencia de color / acabado |
|---|---|---|---|---|---:|---:|---|---|---|
| | | | | | | | | | |
| | | | | | | | | | |

## 4. Revisión de requisitos y factibilidad

Marcar un resultado por criterio: **C** (cumple), **NC** (no cumple), **P** (pendiente de comprobar), **NA** (no aplica, justificado).

| Criterio | Resultado | Evidencia u observación | Responsable |
|---|---|---|---|
| Datos del cliente y contacto completos | | | |
| Producto, tejido, talla, color y cantidades confirmados | | | |
| Cantidad total coincide con la suma del detalle | | | |
| Posición, dimensiones y tolerancias definidas | | | |
| Compatibilidad técnica de prendas e insumos revisada | | | |
| Disponibilidad de prendas e insumos confirmada | | | |
| Capacidad de equipo y personal disponible para la fecha propuesta | | | |
| Condiciones especiales y modalidad de entrega revisadas | | | |

| Campo | Dato |
|---|---|
| Fecha de revisión | |
| Responsable de revisión | |
| Resultado global (viable / pendiente / no viable) | |
| Motivo, condición pendiente o rechazo | |

## 5. Confirmación comercial

| Campo | Dato |
|---|---|
| Estado (pendiente / confirmado / rechazado / cancelado) | |
| Versión de requisitos aceptada | |
| Fecha de aceptación del cliente | |
| Evidencia de aceptación (referencia o canal) | |
| Fecha de entrega acordada inicialmente | |
| Fecha de entrega acordada vigente | |
| Responsable de confirmación | |

## 6. Aprobación del diseño

Registrar cada versión aprobada o solicitada para modificación. Si existen varios diseños, registrar una fila por cada decisión.

| ID de diseño | Versión | Resultado (pendiente / aprobado / ajustes) | Fecha | Evidencia de aceptación | Responsable |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |

La confirmación comercial no sustituye la aprobación del arte.

## 7. Autorización de transferencia a producción

| Control | Resultado (sí / no) |
|---|---|
| Pedido confirmado y viable | |
| Todos los diseños vigentes aprobados | |
| Disponibilidad de insumos confirmada | |
| Especificaciones y cantidades completas | |

| Campo | Dato |
|---|---|
| Decisión (autorizado / bloqueado) | |
| Fecha y responsable de autorización | |
| Motivo del bloqueo | |

La autorización permite transferir el pedido a Producción; la comprobación física de materiales corresponde a F-QP-002 antes de crear el lote.

## 8. Historial de cambios y cancelaciones

No sobrescribir la versión anterior ni perder la primera fecha de entrega acordada.

| Versión nueva | Fecha | Campo modificado | Valor anterior | Valor nuevo | Motivo | Aceptación y evidencia | Responsable |
|---|---|---|---|---|---|---|---|
| | | | | | | | |
| | | | | | | | |

## 9. Reglas de validación para el futuro software

| Campo o condición | Regla |
|---|---|
| ID de pedido | Único, obligatorio e inmutable. |
| Versión | Entero positivo; incrementar al modificar requisitos confirmados. |
| Cantidad | Entero mayor que cero por línea; total calculado sumando las líneas. |
| Dimensiones | Valores mayores que cero al aprobar el diseño. |
| Tolerancias | Valor no negativo y unidad definida; no asumir un valor universal. |
| Fecha acordada | Obligatoria para confirmar el pedido; conservar la inicial y las revisiones aceptadas. |
| Estado comercial | Confirmado solo cuando los requisitos estén revisados, la factibilidad sea viable y exista aceptación. |
| Diseño | Cada versión debe asociarse a su aprobación; una nueva versión requiere nueva revisión y aceptación. |
| Transferencia | Bloquear si cualquiera de los cuatro controles de la sección 7 es negativo o falta por comprobar. |
| Historial | Mantener cambios, responsables, fechas y evidencias; no borrar el pedido al cancelarlo. |

## 10. Control de versiones del formato

| Versión | Fecha | Cambio | Estado |
|---|---|---|---|
| 0.1 | 18/11/2026 | Plantilla inicial de recepción, requisitos, factibilidad, aprobaciones y cambios | En revisión |
| 1.0 | 18/11/2026 | Aprobación del formato F-QP-001 por el usuario | Aprobado |

- [x] **2.8.5.** Formato de recepción de pedidos aprobado para el proyecto académico.

**Siguiente entregable:** [F-QP-002 — Formato de inspección de materiales](F-QP-002_inspeccion_de_materiales.md) (2.8.6), publicado para revisión.

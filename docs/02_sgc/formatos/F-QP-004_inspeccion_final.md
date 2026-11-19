# F-QP-004 — Formato de inspección final y liberación de prendas

| Campo documental | Información |
|---|---|
| Código | F-QP-004 |
| Versión | 0.1 |
| Fecha | 19/11/2026 |
| Actividad | 2.8.8 — Formato de inspección final |
| Estado | **Plantilla en revisión** |
| Empresa | QualityPrint (ficticia) |
| Proceso | PO-03 — Control de calidad |
| Responsable | Control de calidad |
| Procedimiento | [PR-QP-003 — Inspección de calidad](../procedimientos/PR-QP-003_inspeccion_de_calidad.md) |

**Uso:** un registro por inspección de lote. Inspeccionar individualmente el 100 % de las prendas acabadas presentadas y conservar resultados de reinspecciones. Plantilla vacía para el proyecto académico; utilizar exclusivamente datos ficticios.

## 1. Definiciones

| Término | Definición |
|---|---|
| Unidad inspeccionada | Prenda identificada sobre la que se inicia una comprobación de calidad final registrada. |
| Conforme | Unidad que cumple todos los criterios aplicables, incluidas las pruebas adicionales exigidas. |
| Retenida | Unidad apartada con incumplimiento o comprobación pendiente, sin autorización de entrega. |
| Rechazada | Unidad que Calidad determina, mediante decisión registrada, que no puede entregarse como conforme. |
| Defecto | Incumplimiento observado o medido de un criterio de aceptación. |
| Reinspección | Nueva inspección individual de la misma unidad después de una corrección autorizada. |
| Liberada | Unidad conforme cuya entrega ha sido autorizada por Calidad y registrada. |

Una unidad conforme no queda automáticamente liberada para despacho.

## 2. Identificación de la inspección

| Campo | Dato |
|---|---|
| ID único de inspección | |
| Tipo (inicial / reinspección) | |
| ID de inspección anterior, si aplica | |
| ID de pedido y versión de requisitos F-QP-001 | |
| ID de lote y registro F-QP-003 | |
| ID y versión de cada diseño aprobado | |
| Línea(s) de pedido / producto, tejido, color y talla | |
| Fecha y hora de inicio | |
| Fecha y hora de cierre | |
| Responsable de Calidad | |
| Cantidad de prendas presentadas | |
| Referencia de criterios y tolerancias vigentes | |

## 3. Recepción del lote y condiciones de inspección

Usar C (cumple), NC (no cumple), P (pendiente) y NA (no aplica, justificar).

| Verificación | Resultado | Evidencia / observación |
|---|---|---|
| Pedido, lote, identificadores individuales y registros de producción coinciden | | |
| Cantidad recibida concuerda con las unidades aptas entregadas en F-QP-003 o con un retrabajo autorizado | | |
| Arte vigente aprobado, dimensiones, posición y tolerancias disponibles | | |
| Referencia visual y condiciones de evaluación de color definidas | | |
| Área limpia, iluminación y medios de medición adecuados | | |
| Pruebas adicionales exigidas identificadas y método definido, si aplica | | |

Si falta una condición crítica, registrar el motivo y retener las unidades afectadas; no emitir liberación.

## 4. Catálogo de criterios de inspección

Se conservan los códigos de PR-QP-003. No asignar tolerancias numéricas universales: utilizar las documentadas en el pedido o en la instrucción validada.

| Código de defecto | Verificación | Criterio de aceptación |
|---|---|---|
| DEF-01 | Producto, tejido, color y talla | Coinciden con la línea del pedido. |
| DEF-02 | Diseño, contenido y orientación | Coinciden con el arte aprobado. |
| DEF-03 | Ancho y alto del estampado | Dentro de los límites aprobados en cm. |
| DEF-04 | Posición y alineación | Dentro de las tolerancias respecto a las referencias de la prenda. |
| DEF-05 | Integridad de impresión | Sin partes ausentes del diseño. |
| DEF-06 | Manchas y bandas | Sin alteraciones visibles no previstas en el arte. |
| DEF-07 | Adhesión inicial visible | Sin bordes levantados, desprendimientos ni áreas visiblemente desadheridas. |
| DEF-08 | Estado textil | Sin cortes, perforaciones, quemaduras o marcas no previstas. |
| DEF-09 | Acabado | Sin residuos o deformaciones contrarios a la especificación. |
| DEF-10 | Color del estampado | Conforme a la referencia visual aprobada en las condiciones definidas. |

## 5. Registro individual de inspección

Una fila por unidad y revisión. Registrar C, NC, P o NA por criterio; justificar NA y documentar P. Si la prenda tiene varios estampados, comprobarlos todos y detallar los resultados en 5.2. La unidad recibe NC en el criterio si cualquiera de sus estampados lo incumple; P si no hay incumplimiento observado pero falta comprobar alguno.

### 5.1. Resultado por unidad

| ID de unidad | N.º revisión | Línea / talla | DEF-01 | DEF-02 | DEF-03 | DEF-04 | DEF-05 | DEF-06 | DEF-07 | DEF-08 | DEF-09 | DEF-10 | Estado (conforme / retenida / rechazada) |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | | | | | |
| | | | | | | | | | | | | | |

### 5.2. Mediciones y evidencias por unidad y estampado

Registrar, por separado, ancho, alto, posición y alineación que correspondan al diseño. Indicar valor nominal, tolerancia, unidad y valor observado; no inventar límites. Registrar evidencias y justificaciones de NA/P o defectos.

| ID unidad / revisión | ID diseño / versión | Criterio | Valor o referencia aprobada | Tolerancia y unidad | Valor observado / referencia de evidencia | Resultado | Observación |
|---|---|---|---|---|---|---|---|
| | | | | | | | |
| | | | | | | | |

Si todos los criterios aplicables son C y las pruebas adicionales requeridas resultan conformes, la unidad puede declararse conforme. Un NC o P obliga a retenerla mientras no exista disposición; el rechazo necesita una decisión documentada.

## 6. Pruebas adicionales, cuando se exijan

| Campo | Dato |
|---|---|
| Prueba requerida (lavado, adherencia u otra) | |
| Requisito que exige la prueba / referencia | |
| Método, condiciones y criterio de aceptación previamente definidos | |
| Unidad(es) o muestra identificada | |
| Fecha, responsable y evidencia | |
| Resultado (C / NC / P / NA justificado) | |

Repetir por prueba exigida. Sin resultados conformes de las pruebas obligatorias no se libera el lote afectado. La inspección visual de adherencia no demuestra resistencia al lavado.

## 7. Defectos y tratamiento

Registrar un hallazgo por incumplimiento identificado. Una unidad puede presentar varios defectos sin que eso incremente el conteo de prendas defectuosas.

| ID de hallazgo / evento | ID unidad / revisión | ID diseño (si aplica) | Código DEF | Descripción y evidencia | Acción de contención / ubicación | ID de NC F-QP-005 (cuando se genere) |
|---|---|---|---|---|---|---|
| | | | | | | |
| | | | | | | |

### Reinspección

| ID unidad original | ID hallazgo / NC | Retrabajo autorizado y referencia | ID nueva inspección / revisión | Fecha y responsable | Resultado y estado |
|---|---|---|---|---|---|
| | | | | | |

La reinspección debe evaluar todos los criterios aplicables. Conservar el resultado inicial; no reemplazarlo ni eliminar sus defectos.

## 8. Conciliación de cantidades

Contar unidades físicas distintas según su último estado en el registro, sin duplicar reinspecciones.

| Concepto | Cantidad (unidades) |
|---|---:|
| A. Unidades distintas presentadas | |
| B. Unidades distintas inspeccionadas | |
| C. Unidades presentadas aún sin iniciar inspección | |
| D. Unidades conformes | |
| E. Unidades retenidas después de iniciar inspección | |
| F. Unidades rechazadas | |
| G. Unidades distintas con al menos un defecto detectado en inspección final | |
| H. Unidades conformes autorizadas para entrega (parte de D) | |

**Validaciones:** A = B + C; B = D + E + F; G ≤ B; H ≤ D. Todas las cantidades son enteros no negativos. G conserva los defectos detectados en el historial de evaluación, aunque una reinspección posterior sea favorable. C permanece no liberada; si una unidad aún no inspeccionada se retiene, registrar la condición por separado sin sumarla a E.

Los descartes de producción y las unidades no presentadas se controlan en F-QP-003 y no se incluyen como inspeccionadas. En los totales del pedido o del período se deduplican unidades por identificador.

## 9. Liberación y conciliación del pedido

Comparar los resultados acumulados de los lotes del mismo pedido con las cantidades vigentes por línea. No sumar dos veces una prenda ya liberada.

| Línea / producto / talla | Cantidad acordada | Unidades distintas conformes acumuladas | Cantidad previamente liberada | Nueva cantidad autorizada | Diferencia pendiente |
|---|---:|---:|---:|---:|---:|
| | | | | | |

| Decisión | Dato |
|---|---|
| Estado (liberación completa / parcial autorizada / bloqueada) | |
| ID(s) de unidades autorizadas | |
| Cantidad nueva autorizada | |
| Pedido sin requisitos pendientes (sí/no) | |
| Evidencia de autorización expresa del cliente si es parcial | |
| Motivo de bloqueo / condición pendiente | |
| Fecha y hora de autorización | |
| Responsable de Calidad que autoriza | |
| Responsable de Logística que recibe | |

Liberar el pedido completo solo si las cantidades conformes por línea coinciden con lo acordado y no hay requisitos pendientes. Una entrega parcial requiere autorización expresa o modificación del pedido registrada por Comercial. No liberar unidades retenidas, rechazadas, pendientes de evaluación o con pruebas obligatorias pendientes.

## 10. Reglas de validación para el futuro software

| Campo o decisión | Validación |
|---|---|
| Vínculos | ID de inspección único; pedido, lote y unidad identificables. |
| Criterios | Resultado individual C/NC/P/NA; NA requiere justificación. |
| Mediciones | Conservar especificación, unidad, tolerancia y observación. |
| Defectos | Usar código DEF y evidencia; varios defectos pueden asociarse a la misma unidad. |
| Reinspección | Mismo ID de unidad, nueva revisión y referencia al resultado anterior. |
| Estados | No declarar conforme si hay NC/P o prueba obligatoria pendiente; no eliminar historial. |
| Conteos | Calcular A, B, C, D, E, F, G y H según secciones 8 y 9; impedir duplicados. |
| Liberación | Solo por Calidad, con unidades específicas conformes y condiciones del pedido verificadas. |

**Indicadores:** IND-01 usa unidades distintas con defecto detectado / unidades distintas inspeccionadas; IND-03 usa pedidos finalizados con inspección registrada / pedidos finalizados; IND-04 usa eventos detectados con registro de NC / eventos detectados. Multiplicar por 100; si no hay denominador, mostrar N/D. Conservar los IDs para deduplicar en el período de consulta.

Estas reglas son propuestas para el diseño del software; todavía no están implementadas.

## 11. Control de versiones

| Versión | Fecha | Cambio | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Plantilla inicial de inspección individual, defectos, reinspección, cantidades y liberación | En revisión |

- [ ] **2.8.8.** Formato de inspección final publicado; pendiente de aprobación.

**Siguiente entregable:** F-QP-005 — Registro de no conformidades (2.8.9).

[Volver al listado maestro](../LM-QP-001_listado_maestro_de_documentos.md).

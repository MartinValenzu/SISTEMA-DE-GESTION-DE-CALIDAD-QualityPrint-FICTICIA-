# F-QP-002 — Formato de inspección y liberación de materiales DTF

| Campo | Valor |
|---|---|
| Código documental | F-QP-002 |
| Versión | 0.1 |
| Fecha | 18/11/2026 |
| Actividad del ROADMAP | **2.8.6. Formato de inspección de materiales** |
| Estado | **Borrador para revisión; no aprobado** |
| Empresa | QualityPrint (ficticia) |
| Proceso | PO-02 — Preparación de la producción DTF |
| Responsable de verificación | Operador DTF |
| Apoyo y tratamiento de desviaciones | Administración/logística y Control de calidad |
| Procedimiento asociado | [PR-QP-002 — Producción DTF](../procedimientos/PR-QP-002_produccion_dtf.md) |

> **Uso académico:** esta es una plantilla vacía. No contiene inspecciones realizadas ni demuestra controles ejecutados. Para pruebas y portafolio deben usarse exclusivamente identificadores y datos ficticios. La compatibilidad, las condiciones de almacenamiento y los criterios técnicos se determinan a partir de las fichas reales del fabricante/proveedor y de la combinación de insumos y equipo seleccionada; no se inventan valores de temperatura, tiempo, presión ni tolerancias.

## 1. Objetivo y regla de uso

Registrar **antes de iniciar la impresión de un lote** la identidad, cantidad, condición y compatibilidad de las prendas y consumibles DTF. Dejar constancia de la decisión de **aceptación, retención o rechazo** para impedir utilizar material sin verificar o no conforme.

**Una inspección de recepción del proveedor y una verificación previa a producción pueden usar este mismo formato, pero cada una necesita su propio ID de inspección y tipo de control.** Una revisión realizada días antes no reemplaza el examen visual del material antes de utilizarlo.

## 2. Definiciones puntuales

| Concepto | Definición operativa |
|---|---|
| Material inspeccionado | Prenda o consumible DTF identificado por referencia y, cuando exista, lote del proveedor. |
| Lote de insumo | Código asignado por el proveedor para identificar una partida del mismo material. |
| Conforme (C) | Se comprueba el criterio indicado en la ficha o especificación aprobada. |
| No conforme (NC) | El material incumple al menos un criterio aplicable. |
| Pendiente (P) | Falta evidencia para confirmar un criterio; el material no queda liberado. |
| No aplica (NA) | El criterio no corresponde a ese material y se registra la justificación. |
| Retenido | Material identificado y apartado temporalmente, prohibido para producción. |
| Liberado | Material autorizado para uso después de cumplir los criterios aplicables. |

**NC** es el resultado de una comprobación y no siempre implica que ya se haya creado un registro formal F-QP-005. Si existe incumplimiento confirmado debe informarse a Calidad y registrarse según PR-QP-004.

## 3. Identificación de la inspección

| Campo obligatorio | Dato por diligenciar |
|---|---|
| ID único de inspección de materiales | |
| Tipo: recepción de proveedor / previo a producción | |
| Fecha y hora | |
| ID del pedido | |
| ID del lote de producción (si ya fue asignado) | |
| Responsable que inspecciona | |
| Área de revisión | |
| Referencia de orden / entrega del proveedor, si corresponde | |
| Referencia de especificaciones técnicas vigentes | |

Si todavía no existe lote de producción, conservar el **ID de pedido** y registrar el **ID de lote** al asignarlo. El formato no autoriza por sí mismo iniciar una producción sin arte aprobado.

## 4. Insumos inspeccionados y trazabilidad

Registrar **una fila por referencia y lote de proveedor**. Si dos partidas del mismo insumo tienen lotes distintos, usar dos filas.

| ID línea | Tipo de material | Referencia / descripción exacta | Proveedor | Lote de proveedor | Cantidad requerida | Cantidad verificada | Unidad (u., m, kg, etc.) | Vencimiento (si aplica) | Ubicación / observación |
|---|---|---|---|---|---:|---:|---|---|---|
| | Prenda textil | | | | | | | | |
| | Film PET DTF | | | | | | | | |
| | Tinta DTF | | | | | | | | |
| | Polvo adhesivo DTF | | | | | | | | |
| | Otro insumo | | | | | | | | |

**Regla de cantidad:** valores numéricos mayores que cero para insumos requeridos; identificar unidad y fuente de la cantidad solicitada. Si una cantidad verificada es insuficiente, marcar **P** o **NC** según la condición y **no liberar para la cantidad planificada**.

## 5. Lista de inspección por tipo de material

### 5.1. Prendas textiles

| Verificación | Resultado C / NC / P / NA | Hallazgo / evidencia |
|---|---|---|
| Tipo de prenda coincide con el pedido | | |
| Composición/tejido identificado y compatible con el proceso aprobado | | |
| Color y tallas coinciden con las líneas del pedido | | |
| Cantidad por talla coincide con la necesidad del lote | | |
| Sin manchas, roturas, humedad anormal ni defectos visibles antes del estampado | | |
| Área prevista de estampado permite las dimensiones del diseño aprobado | | |

### 5.2. Film PET DTF

| Verificación | Resultado C / NC / P / NA | Hallazgo / evidencia |
|---|---|---|
| Referencia del film compatible con tinta, polvo y modo de transferencia | | |
| Cara de impresión y método de despegue identificados por ficha técnica | | |
| Film sin roturas, dobleces, contaminación ni daños visibles | | |
| Condiciones de almacenamiento conformes con instrucciones del proveedor | | |
| Cantidad disponible para el trabajo | | |

### 5.3. Tintas DTF

| Verificación | Resultado C / NC / P / NA | Hallazgo / evidencia |
|---|---|---|
| Referencia y tipo adecuados para la impresora / cabezal y flujo RIP | | |
| Envase y etiqueta legibles, sin fugas ni deterioro observable | | |
| Fecha/lote identificables y vigencia conforme a fabricante, si aplica | | |
| Condiciones de almacenamiento y manejo confirmadas con ficha técnica | | |
| Disponibilidad de colores y blanco requeridos para el arte | | |

### 5.4. Polvo adhesivo DTF

| Verificación | Resultado C / NC / P / NA | Hallazgo / evidencia |
|---|---|---|
| Referencia de polvo compatible con el film, tinta y tejido previstos | | |
| Envase identificado, sin contaminación ni humedad anormal visible | | |
| Lote / condiciones de conservación comprobados | | |
| Ficha de datos de seguridad (SDS) e instrucciones disponibles | | |
| Controles de manipulación, extracción/ventilación y protección requeridos definidos | | |

**Condición de seguridad:** si no están definidos los controles exigidos por la SDS y la evaluación del puesto, **no autorizar la manipulación del polvo**. Este formato no sustituye una evaluación profesional de seguridad.

### 5.5. Insumos o accesorios adicionales

| Insumo / referencia | Criterio aplicado | Resultado C / NC / P / NA | Evidencia / observación |
|---|---|---|---|
| | | | |
| | | | |

## 6. Referencias técnicas y compatibilidad

| Campo | Referencia o resultado |
|---|---|
| Ficha técnica de prenda o tejido | |
| Ficha técnica de film y tipo de despegue | |
| Ficha técnica de tinta | |
| Ficha técnica/SDS del adhesivo | |
| Referencia del procedimiento o receta técnica validada para esa combinación | |
| Marca/modelo de impresora y prensa relacionados (solo identificación) | |
| Resultado global de compatibilidad (confirmada / pendiente / no compatible) | |
| Evidencia de consulta técnica, cuando se requiera | |

**No copiar parámetros de otras marcas o equipos.** Los ajustes de impresión, curado y transferencia se registrarán en **F-QP-003**, una vez aprobados con base en el equipo y los materiales concretos.

## 7. Hallazgos, retención y tratamiento

Si existe resultado **NC** o **P**, identificar la **línea de insumo afectada**, la cantidad y su ubicación; impedir su utilización hasta nueva decisión documentada.

| ID de hallazgo | Línea(s) afectada(s) | Criterio incumplido / pendiente | Cantidad afectada y unidad | Acción inmediata (identificar, separar, suspender) | ID de NC F-QP-005 si aplica | Responsable y fecha |
|---|---|---|---|---|---|---|
| | | | | | | |
| | | | | | | |

**Regla:** no convertir el estado **P** en **C** sin registrar la evidencia faltante. Una reinspección exige fecha, responsable y resultado nuevos.

## 8. Decisión final de inspección

| Control de salida | Respuesta |
|---|---|
| ¿Todos los criterios aplicables tienen resultado C o NA justificado? | |
| ¿Las cantidades requeridas están disponibles y conciliadas? | |
| ¿Se confirmó la compatibilidad técnica? | |
| ¿Los materiales con NC/P están retenidos e identificados? | |
| ¿Las condiciones de seguridad de manipulación están verificadas para el puesto? | |

| Decisión | Dato |
|---|---|
| **Estado global: LIBERADO / RETENIDO / RECHAZADO** | |
| ID(s) de línea(s) liberada(s), si hay liberación parcial | |
| Cantidad liberada por línea (y unidad) | |
| Justificación y acciones pendientes | |
| Responsable de inspección | |
| Fecha y hora de la decisión | |
| Responsable que autoriza una liberación excepcional documentada (si aplica) | |
| ID y fecha de reinspección (si aplica) | |

**Liberación parcial:** solo se autoriza el uso de **líneas o cantidades explícitamente liberadas**; los materiales retenidos permanecen separados. Una liberación excepcional no puede omitir un requisito de seguridad o compatibilidad.

## 9. Reglas de validación para el futuro software

| Campo o decisión | Regla de negocio verificable |
|---|---|
| Identificación | Cada inspección tiene ID único; se vincula a pedido y, cuando exista, lote de producción. |
| Tipos de material | Valores normalizados: prenda, film, tinta, adhesivo u otro. |
| Cantidades | Números positivos, misma unidad para comparar requerido y verificado. |
| Trazabilidad | Registrar referencia y lote de proveedor cuando exista; nunca inventarlo si falta. |
| Estado por criterio | Solo C, NC, P o NA; NA exige justificación. |
| Estado por material | No liberar una línea con NC o P sin nueva inspección satisfactoria. |
| Liberación global | Solo cuando todas las líneas necesarias cumplen criterios y hay disponibilidad suficiente; excepciones parciales requieren cantidades liberadas explícitas. |
| Hallazgos | Vincular una detección a la línea afectada y, ante NC confirmada, al registro de no conformidad cuando se genere. |
| Seguridad | Si faltan verificaciones obligatorias de seguridad para el manejo previsto, la decisión queda retenida. |
| Auditoría | Guardar cambios de estado, fecha, responsable y evidencia; no sobrescribir historial. |

Estas son **reglas propuestas para las etapas 3 y 4**, no características ya implementadas en la aplicación.

## 10. Revisión del formato y control de cambios

- [ ] **2.8.6.** Formato de inspección de materiales redactado y publicado; pendiente de aprobación.

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 18/11/2026 | Plantilla de materiales, criterios específicos, retención y liberación | En revisión |

**Próximo entregable tras aprobar F-QP-002:** **2.8.7 — F-QP-003, Registro de producción DTF**.

[Volver al listado maestro](../LM-QP-001_listado_maestro_de_documentos.md).

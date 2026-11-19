# F-QP-003 — Registro de producción DTF

| Campo documental | Información |
|---|---|
| Código | F-QP-003 |
| Versión | 1.0 |
| Fecha | 19/11/2026 |
| Actividad | 2.8.7 — Registro de producción DTF |
| Estado | **Formato aprobado para el proyecto académico** |
| Empresa | QualityPrint (ficticia) |
| Proceso | PO-02 — Producción DTF |
| Responsable | Operador DTF |
| Verificación | Control de calidad |
| Procedimiento | [PR-QP-002 — Producción DTF](../procedimientos/PR-QP-002_produccion_dtf.md) |

**Uso:** diligenciar un registro por lote de producción y conservar cada cambio. Esta plantilla vacía no acredita producción ejecutada. Utilizar únicamente datos ficticios en el portafolio.

## 1. Definiciones

| Término | Definición |
|---|---|
| Lote de producción | Conjunto de prendas de un pedido con el mismo diseño aprobado, tejido y configuración técnica, identificado mediante un código único. |
| Primera pieza | Primera prenda estampada de una configuración que Calidad verifica antes de autorizar las restantes. |
| Parámetro validado | Valor o rango aprobado para una combinación concreta de equipo, tejido e insumos. |
| Prenda procesada | Unidad que entró en una operación de estampado del lote. |
| Pendiente | Unidad asignada al lote que aún no ha sido procesada. |
| Apta para inspección | Unidad acabada sin desviación pendiente que pasa a inspección final; aún no está liberada para despacho. |
| Retenida | Unidad identificada y separada por una desviación pendiente de decisión. |
| Descartada | Unidad definitivamente excluida del lote mediante decisión documentada. |
| Retrabajo | Nueva operación autorizada sobre una unidad ya procesada para cumplir su requisito original. |

## 2. Identificación del lote

| Campo | Dato |
|---|---|
| ID único de lote | |
| ID del pedido F-QP-001 | |
| Versión vigente de requisitos | |
| Línea(s) del pedido | |
| ID y versión de cada diseño aprobado | |
| Referencia de aprobación del cliente | |
| Producto / tejido / color / talla | |
| Cantidad inicial asignada (unidades) | |
| Fecha y hora de inicio | |
| Fecha y hora de cierre | |
| Operador responsable | |
| Impresora DTF (ID y modelo) | |
| Equipo de curado (ID y modelo) | |
| Prensa térmica (ID y modelo) | |
| Referencia de configuración técnica aprobada | |
| Estado del lote (preparado / en producción / detenido / cerrado) | |

Si cambia el diseño, tejido o la configuración técnica validada, cerrar o detener el lote anterior y abrir otro lote vinculado al mismo pedido. Si cambia un insumo o equipo sin modificar la configuración técnica validada, detener, verificar la compatibilidad, documentar el cambio y exigir una nueva primera pieza antes de continuar. Conservar los tramos anteriores.

## 3. Verificación previa al inicio

Registrar C (cumple), NC (no cumple) o P (pendiente). Todos los controles son obligatorios.

| Control | Resultado | Evidencia / referencia |
|---|---|---|
| Pedido confirmado y todos los diseños de la línea aprobados | | |
| Dimensiones, posición, orientación y tolerancias definidas | | |
| Inspección previa de materiales F-QP-002 liberada para las cantidades requeridas | | |
| Equipos verificados según manuales y condiciones de operación segura | | |
| Instrucción técnica validada disponible para la combinación | | |
| Controles de manipulación, extracción y protección definidos y verificados | | |

| Campo | Dato |
|---|---|
| Decisión de inicio (autorizado / bloqueado) | |
| Fecha, hora y responsable | |
| Motivo si se bloquea | |

**Regla:** no imprimir la primera pieza ni iniciar producción si algún control tiene resultado NC o P. La autorización de inicio no autoriza producir el resto del lote hasta aceptar la primera pieza.

## 4. Materiales utilizados

Vincular cada línea a la inspección de materiales y conservar el lote del proveedor cuando exista. No sumar cantidades con unidades distintas.

| ID línea F-QP-002 | Material / referencia | Lote de proveedor | Cantidad liberada para el lote | Consumo real | Unidad (u., m, ml, g, etc.) | Observación |
|---|---|---|---:|---:|---|---|
| | Prendas | | | | | |
| | Film | | | | | |
| | Tinta | | | | | |
| | Adhesivo | | | | | |
| | Otro | | | | | |

**ID(s) de inspección F-QP-002:** __________.

Si se sustituye material, registrar la nueva línea, inspección y configuración antes de utilizarlo. El consumo real no debe exceder la cantidad liberada vinculada al lote sin autorización adicional documentada.

## 5. Parámetros técnicos del proceso

Repetir esta tabla por configuración identificada. Completar únicamente con valores tomados de una instrucción validada y del equipo real; no usar valores universales.

**ID de configuración:** __________. **Referencia y revisión de instrucción técnica:** __________.

| Operación | Parámetro | Unidad / escala | Valor o rango autorizado | Valor configurado / observado | Resultado C / NC / P / NA |
|---|---|---|---|---|---|
| Impresión | Archivo RIP, modo/perfil y configuración aplicable | Referencia | | | |
| Impresión | Verificación previa de impresión según manual | Resultado | | | |
| Adhesivo | Método de aplicación y retiro de exceso | Referencia | | | |
| Curado | Temperatura | °C | | | |
| Curado | Tiempo | s | | | |
| Transferencia | Temperatura | °C | | | |
| Transferencia | Tiempo | s | | | |
| Transferencia | Presión | Unidad o escala de prensa | | | |
| Despegue | Condición y espera, si se exige | Tipo / s | | | |
| Acabado | Prensado final, si aplica | °C / s / escala | | | |

| Campo | Dato |
|---|---|
| Fecha y hora de verificación | |
| Responsable | |
| Evidencia / referencia de medición o lectura | |
| Justificación de criterios NA | |

Si un parámetro se aparta de su rango autorizado, detener y retener lo afectado desde la última verificación conforme. Registrar la incidencia, corregir y obtener nueva aceptación de primera pieza antes de continuar.

## 6. Control y aceptación de primera pieza

Registrar una fila por intento; conservar los intentos no aceptados. Si la pieza contiene varios estampados, comprobarlos todos.

| ID de intento | ID de prenda | ID configuración | Fecha/hora | Diseño y orientación | Dimensiones | Posición | Integridad visual | Adherencia inicial visible | Resultado (aceptada / retenida) | Responsable Calidad |
|---|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | | |
| | | | | | | | | | | |

Marcar C o NC en cada criterio y registrar las medidas observadas, especificaciones y tolerancias aplicables en el siguiente detalle.

| ID intento / diseño | Criterio o dimensión | Especificación y tolerancia | Valor observado / evidencia | Resultado |
|---|---|---|---|---|
| | | | | |
| | | | | |

**Autorización de continuación:** únicamente si todos los criterios aplicables de la primera pieza vigente cumplen. Repetir ante un cambio de configuración, insumo, equipo o corrección que modifique los parámetros, según PR-QP-002. No confundir esta aceptación con la liberación final.

## 7. Seguimiento de producción

Registrar una fila por tramo de producción bajo una configuración aceptada. Identificar las unidades procesadas; conservar los eventos aunque después exista retrabajo.

| Tramo | Configuración / intento aceptado | Fecha/hora inicio-fin | IDs de unidades o rango inequívoco | Nuevas unidades procesadas | Control visual film/prenda | Desviación / ID de incidencia | Operador |
|---|---|---|---|---:|---|---|---|
| | | | | | | | |
| | | | | | | | |

Registrar las unidades de primera pieza en la sección 6 y en el estado individual de la sección 9.2; incluirlas una sola vez en el total procesado. Los tramos de esta sección registran las unidades restantes. No contar como nueva unidad una prenda retrabajada. El seguimiento debe permitir conocer qué unidades fueron procesadas antes y después de un cambio.

## 8. Incidencias y retrabajos

| ID incidencia | Fecha/hora | Tramo, unidad(es) o film afectado | Etapa / desviación | Cantidad y unidad | Acción de contención | ID NC (F-QP-005, si aplica) | Decisión Calidad / resultado |
|---|---|---|---|---|---|---|---|
| | | | | | | | |
| | | | | | | | |

| ID unidad | Motivo y autorización de retrabajo | Fecha / responsable | Resultado de la verificación | Estado resultante |
|---|---|---|---|---|
| | | | | |

Los retrabajos no eliminan las incidencias iniciales. Si se descarta una prenda y se utiliza otra como reposición, registrar ambas con IDs diferentes.

## 9. Conciliación y cierre del lote

### 9.1. Cantidades de prendas

Contar cada unidad física una sola vez según su estado al cierre.

| Concepto | Cantidad (unidades) |
|---|---:|
| A. Unidades inicialmente asignadas | |
| B. Reposiciones u otras incorporaciones autorizadas | |
| C. Unidades retiradas antes de procesar, documentadas | |
| D. Total asignado neto (A + B − C) | |
| E. Unidades procesadas distintas (incluye primera pieza procesada) | |
| F. Aptas para inspección final | |
| G. Retenidas | |
| H. Descartadas después de procesar | |
| I. Pendientes de procesar | |

**Validaciones obligatorias:**

- D = E + I.
- E = F + G + H.
- Todas las cantidades son enteros no negativos.
- El número de operaciones de retrabajo no se suma a E.
- Las retiradas antes de procesar (C) no se cuentan como descartes de producción (H); registrar motivo, ID y destino.
- Las pérdidas de film o consumibles se registran en su propia unidad de medida, no como prendas descartadas.

### 9.2. Movimientos y estado al cierre

| ID de unidad o rango | Estado final (apta / retenida / descartada / pendiente / retirada antes de procesar) | Cantidad | Referencia de evidencia o disposición |
|---|---|---:|---|
| | | | |
| | | | |

### 9.3. Transferencia a Control de calidad

| Campo | Dato |
|---|---|
| Cantidad entregada a inspección final (F) | |
| ID(s) de unidades entregadas | |
| Cantidad retenida y ubicación | |
| Cantidad descartada y decisión asociada | |
| Pendientes y motivo | |
| Fecha/hora de entrega | |
| Operador que entrega | |
| Responsable de Calidad que recibe | |
| Referencia de inspección final F-QP-004 (cuando se registre) | |
| Observaciones / incidencias pendientes | |

No cerrar el registro con cantidades incoherentes. Un lote puede cerrarse parcialmente con pendientes o retenidas solo si se documentan las cantidades, sus motivos y su seguimiento; no se considera el pedido completo ni autorizado para despacho.

## 10. Reglas para el futuro software

| Campo o acción | Validación |
|---|---|
| ID lote | Único e inmutable; asociado a un pedido y sus líneas aprobadas. |
| Materiales | Vincular a líneas liberadas de F-QP-002 y cantidades suficientes. |
| Inicio | Bloquear si falta cualquier control obligatorio de la sección 3. |
| Parámetros | Registrar configuración, origen del valor autorizado, unidad y valor observado. |
| Primera pieza | Bloquear producción restante sin aceptación vigente de Calidad. |
| Cambio técnico | Invalidar la autorización anterior; exigir nueva primera pieza y abrir otro lote si cambia la configuración validada. |
| Unidades | ID único por prenda, sin duplicar el conteo de retrabajos o reinspecciones. |
| Cierre | Verificar ambas conciliaciones y conservar el estado individual de las unidades. |
| Transferencia | Solo unidades aptas pasan a inspección final; nunca a despacho directo. |
| Auditoría | Conservar usuario, fecha, hora, cambios, decisiones y evidencias. |

Reglas propuestas para las etapas de requisitos y diseño; todavía no son funcionalidades implementadas.

## 11. Control de versiones

| Versión | Fecha | Cambio | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Plantilla inicial de materiales, parámetros, primera pieza, incidencias y conciliación del lote | En revisión |
| 1.0 | 19/11/2026 | Aprobación del usuario | Aprobado |

- [x] **2.8.7.** Registro de producción DTF aprobado para el proyecto académico.

**Siguiente entregable:** [F-QP-004 — Formato de inspección final](F-QP-004_inspeccion_final.md) (2.8.8).

[Volver al listado maestro](../LM-QP-001_listado_maestro_de_documentos.md).

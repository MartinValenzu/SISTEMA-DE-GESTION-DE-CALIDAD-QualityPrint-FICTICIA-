# DOC-QP-011 — Requisitos funcionales del software

| Campo | Información |
|---|---|
| Código | DOC-QP-011 |
| Apartado | 3.2 — Requisitos funcionales |
| Versión | 1.0 |
| Fecha | 19/11/2026 |
| Estado | **Aprobado para el proyecto académico** |
| Proyecto | QualityPrint-SGC (empresa ficticia) |
| Elaboración | Responsable del proyecto |
| Revisión propuesta | Gerencia y Control de calidad |
| Aprobación del portafolio | Aprobado por el usuario del proyecto |

## 1. Objetivo y alcance

Especificar las operaciones que deberá realizar la aplicación web del SGC, los datos que deberá registrar y las condiciones verificables que determinarán si cada operación funciona correctamente.

**Requisito funcional (RF):** comportamiento observable que el sistema debe ejecutar ante una solicitud o evento. **Criterio de aceptación:** condición concreta cuyo cumplimiento permite verificar ese comportamiento mediante una prueba.

El MVP comprende los once apartados del roadmap 3.2. No incluye facturación, pagos, contabilidad, control directo de maquinaria, gestión avanzada de inventario ni aplicación móvil nativa. Cada RF tiene código único y estable; no implica que ya se haya programado.

**Fuentes:** [DOC-QP-010 — Roles y permisos](DOC-QP-010_usuarios_roles_y_permisos.md), [DOC-QP-004 — Indicadores](../02_sgc/DOC-QP-004_direccionamiento_estrategico.md), [procedimientos y formatos aprobados de la etapa 2](../02_sgc/README.md).

## 2. Reglas comunes

- Toda operación protegida requiere sesión activa y autorización de acuerdo con DOC-QP-010, incluyendo la separación de funciones y el alcance de datos.
- Los identificadores de registros son únicos e inmutables. Los vínculos obligatorios deben apuntar a registros existentes.
- Validar campos, estados, cantidades y permisos en el servidor. Si la validación falla, informar el motivo sin guardar una modificación parcial.
- Los registros cerrados, aprobados o referenciados no se eliminan ni se sobrescriben. Los cambios permitidos conservan actor, fecha, valor anterior, nuevo valor, motivo y evidencia cuando aplique.
- Toda consulta permite localizar los registros por identificador y los filtros definidos en su requisito. Usar exclusivamente datos ficticios para pruebas y demostraciones.
- Las autorizaciones se registran por persona, no solo por rol. Las expresiones «deberá» designan condiciones futuras, no funciones implementadas.

## 3.2.1. Gestión de usuarios

**Fuente:** DOC-QP-010, PER-01 a PER-08.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-01 | Registrar cuentas individuales con identificador, nombre, usuario único, estado y roles autorizados. | ADMIN | Una cuenta válida se guarda; un nombre de usuario duplicado se rechaza. No se admite una cuenta compartida. |
| RF-02 | Iniciar y cerrar sesión, verificando credenciales y estado activo. | Todos | Credenciales válidas de una cuenta activa permiten acceso a su menú; inválidas o cuenta inactiva lo deniegan. Tras cerrar sesión no se accede a rutas protegidas. |
| RF-03 | Consultar, actualizar y desactivar cuentas; restablecer credenciales sin revelar las anteriores. | ADMIN | Una cuenta desactivada pierde acceso, pero sus registros históricos conservan su autor. El restablecimiento invalida la credencial anterior. |
| RF-04 | Registrar autorización de roles por GERENCIA y aplicar los cambios por ADMIN. | GERENCIA / ADMIN | Una asignación sin autorización o que eleve los privilegios del propio usuario se rechaza; una autorizada queda registrada con el autorizador, el ejecutor y la fecha. |
| RF-05 | Aplicar permisos, alcance de consulta y restricciones de separación de funciones en cada operación. | Sistema | Un ADMIN sin CALIDAD no modifica inspecciones; un usuario con PRODUCCION y CALIDAD no libera su propio lote. Un intento denegado no altera datos. |

## 3.2.2. Gestión de clientes

**Fuente:** PR-QP-001 / F-QP-001.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-06 | Crear clientes con ID, nombre o razón social, medio de contacto y estado. | COMERCIAL | Se registra un cliente identificado con al menos un contacto; no se graba un ID repetido ni un cliente sin nombre. |
| RF-07 | Consultar clientes por ID, nombre y estado, actualizar datos de contacto y desactivar registros conservando sus pedidos. | COMERCIAL; consulta GERENCIA/CALIDAD según necesidad | Una modificación no cambia el ID. Un cliente inactivo no puede vincularse a pedidos nuevos, pero sus pedidos anteriores permanecen accesibles a los roles autorizados. |

## 3.2.3. Registro y consulta de pedidos

**Fuente:** PR-QP-001 / F-QP-001; despacho conforme PR-QP-003 / F-QP-004.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-08 | Registrar pedido vinculado a cliente activo, fechas de solicitud y entrega, modalidad, líneas de producto, talla, color, tejido y cantidad. | COMERCIAL | Al registrar dos líneas de 3 y 5 unidades, el total calculado es 8; una cantidad cero, negativa o fraccionaria se rechaza. |
| RF-09 | Registrar diseños por línea, versiones, referencia de arte, posición, orientación, dimensiones, tolerancias y aprobación del cliente. | COMERCIAL | Una versión nueva queda pendiente de aprobación y conserva la anterior. No se aprueba si faltan especificaciones o evidencia del cliente. |
| RF-10 | Revisar factibilidad, disponibilidad, capacidad y aceptación; confirmar, rechazar o cancelar el pedido con motivo. | COMERCIAL | Una confirmación sin fecha acordada, requisitos completos, factibilidad viable o aceptación se bloquea. Cancelar conserva el registro; no permite nuevos lotes. |
| RF-11 | Autorizar transferencia a producción únicamente con pedido confirmado, todos sus diseños vigentes aprobados y requisitos e insumos disponibles. | COMERCIAL | Con un diseño pendiente o disponibilidad sin confirmar, no se autoriza la transferencia. La autorización no sustituye la inspección física de materiales. |
| RF-12 | Versionar cambios de requisitos y fechas acordadas con aceptación del cliente; conservar historial y comunicar el cambio a producción y calidad mediante consulta del estado vigente. | COMERCIAL | Una modificación aceptada incrementa la versión, mantiene fecha inicial y evidencia; los lotes afectados no continúan con especificaciones obsoletas hasta reevaluación. |
| RF-13 | Consultar pedidos por ID, cliente, fecha, estado comercial y avance operativo, mostrando lotes, inspecciones, liberaciones y entregas relacionadas. | Roles autorizados según DOC-QP-010 | El detalle de un pedido presenta sus registros vinculados y no muestra información ajena al alcance del usuario. |
| RF-14 | Registrar despacho y entrega física por línea y unidades autorizadas, fecha, modalidad y evidencia; impedir duplicar unidades entregadas. | LOGISTICA | Un despacho de unidades retenidas se rechaza. Una entrega parcial exige autorización expresa del cliente; una entrega completa requiere cantidades acordadas y requisitos satisfechos. |

**Estados comerciales:** pendiente, confirmado, rechazado, cancelado. El avance operativo se obtiene de las autorizaciones y registros vinculados; no debe confundirse con el estado comercial.

**Pedido entregado/finalizado:** pedido confirmado cuyas cantidades acordadas vigentes se entregaron completamente con evidencia. No se cuenta como finalizado por estar cancelado, rechazado o parcialmente entregado. La fecha de entrega completa es la del último despacho recibido y confirmado.

## 3.2.4. Gestión de productos y prendas

**Fuente:** F-QP-001 y F-QP-002.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-15 | Administrar catálogo de productos y variantes con ID, descripción, tipo de prenda, tejido, talla, color y estado. | COMERCIAL | No se crea una variante duplicada del mismo producto, tejido, talla y color; una variante inactiva no se selecciona en pedidos nuevos. |
| RF-16 | Registrar recepción básica de insumos y prendas con referencia, proveedor, lote cuando exista, cantidad, unidad y vencimiento si aplica. | LOGISTICA | Se guarda una recepción identificable con cantidad positiva y unidad; no se admite una cantidad negativa ni se confunde recepción con liberación de calidad. |
| RF-17 | Conservar la especificación de producto y variante aceptada en el pedido, aunque el catálogo cambie posteriormente. | Sistema | Modificar la descripción de una variante no altera las especificaciones históricas de los pedidos confirmados. |

No se contempla contabilidad de existencias, valoración ni compras automatizadas. Se registran las entradas necesarias para trazabilidad de producción.

## 3.2.5. Registro de producción DTF

**Fuente:** PR-QP-002 / F-QP-002 / F-QP-003.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-18 | Registrar inspección de materiales vinculada al pedido, referencias, lotes, cantidades y criterios C/NC/P/NA con evidencia y justificación cuando aplique. | PRODUCCION / CALIDAD | Un criterio NC o pendiente bloquea la liberación del material afectado; no se libera por registrar la inspección. Solo CALIDAD autoriza uso conforme. |
| RF-19 | Crear lote con ID, pedido transferido, líneas, diseños aprobados, insumos, equipos, cantidades y operador. | PRODUCCION | Un lote sin pedido autorizado, materiales liberados suficientes o especificaciones vigentes no puede iniciar producción. |
| RF-20 | Registrar parámetros aplicados por operación y valores/rangos de referencia de la instrucción técnica validada para la combinación. | PRODUCCION | Una desviación respecto al rango aprobado queda registrada, obliga a contener lo afectado y bloquea la continuación hasta decisión de CALIDAD. No se asignan valores DTF universales. |
| RF-21 | Registrar primera pieza, aceptación de CALIDAD y cambios de diseño, tejido, insumo, equipo o configuración que exijan repetirla. | PRODUCCION registra; CALIDAD autoriza | Sin aceptación de primera pieza no se registra producción de las unidades restantes. Un cambio que invalide la aceptación obliga a nueva verificación. |
| RF-22 | Identificar cada prenda física, registrar autocontroles, incidencias, retrabajos autorizados y estado del lote. | PRODUCCION | Un retrabajo conserva el ID original y el historial; una unidad no puede contarse dos veces como procesada. |
| RF-23 | Cerrar lote y conciliar cantidades: procesadas = aptas para inspección + retenidas + descartadas; registrar pendientes y entregar a Calidad. | PRODUCCION | Si se registran 10 procesadas y 7 aptas, 2 retenidas y 1 descartada, la conciliación es válida; si las cantidades no coinciden, no se cierra. El cierre no libera prendas. |

Estados del lote: preparado, en producción, detenido y cerrado. Los cambios de estado requieren los controles documentados en F-QP-003. No se ordena operar maquinaria desde el software.

## 3.2.6. Registro de inspecciones

**Fuente:** PR-QP-003 / F-QP-004.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-24 | Registrar inspección final con ID, pedido, lote, unidades individuales e identificación del criterio vigente. | CALIDAD | Solo se vinculan unidades del lote correcto, entregadas a inspección o autorizadas para reinspección; no se admite una revisión duplicada de la misma unidad. |
| RF-25 | Evaluar cada unidad y cada estampado aplicable con criterios DEF-01 a DEF-10, resultados C/NC/P/NA, mediciones, tolerancias, evidencia y pruebas adicionales cuando sean obligatorias. | CALIDAD | Una unidad con un criterio NC o pendiente no se declara conforme. Una NA exige justificación y una prueba obligatoria pendiente bloquea liberación. |
| RF-26 | Registrar reinspección después de retrabajo autorizado, conservando la identificación, revisión anterior y defectos. | CALIDAD | Una reinspección conforme no elimina el defecto inicial ni crea otra unidad física; existe una nueva revisión rastreable. |
| RF-27 | Conciliar cantidades presentadas, inspeccionadas, pendientes, conformes, retenidas, rechazadas, defectuosas y liberadas. | Sistema / CALIDAD | Valida A=B+C, B=D+E+F, G≤B y H≤D según F-QP-004; las cantidades son enteros no negativos y se deduplican IDs. |
| RF-28 | Autorizar liberación completa o parcial de unidades conformes por línea; registrar actor, fecha, IDs y cantidades. | CALIDAD | No se libera una prenda pendiente, retenida o rechazada; no libera quien produjo el lote. Una liberación parcial requiere autorización expresa del cliente y no duplica IDs ya liberados. |

## 3.2.7. Registro de defectos

**Fuente:** catálogo de PR-QP-003 / F-QP-004.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-29 | Registrar hallazgo con ID, código DEF, unidad, revisión, diseño cuando aplique, criterio incumplido, descripción y evidencia. | CALIDAD para inspección final | Al registrar DEF-03 y DEF-06 en una misma prenda, quedan dos hallazgos y una unidad defectuosa. Los códigos utilizados corresponden al catálogo aprobado. |
| RF-30 | Registrar eventos de detección independientes de NC desde inspecciones, producción, materiales o reclamaciones, con fuente, responsable y fecha. | Roles operativos y GERENCIA conforme DOC-QP-010 | Un evento tiene identidad propia antes de crear la NC; varios defectos del mismo evento pueden vincularse sin duplicarlo. CALIDAD puede confirmar el incumplimiento en el evento de origen sin crear todavía F-QP-005. Un reporte no confirmado no se cuenta como NC confirmada. |
| RF-31 | Consultar defectos por código, pedido, lote, unidad y período; mostrar evento de origen, contención, reincidencia y vínculo a NC. | CALIDAD / GERENCIA; otros según alcance | El registro de un defecto permite consultar el historial inicial y la reinspección, aunque el defecto haya sido corregido. |

## 3.2.8. Gestión de no conformidades

**Fuente:** PR-QP-004 / F-QP-005.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-32 | Registrar NC a partir de un evento confirmado, asignar ID único y vincular evento independiente, requisito, alcance, evidencia, prioridad y responsable. | CALIDAD | No se registra otra NC para el mismo evento confirmado; varios eventos independientes mantienen sus IDs. La prioridad aplica el criterio más alto correspondiente. |
| RF-33 | Registrar contención, notificaciones y disposición por elemento o grupo, cantidad, responsable, plazo y evidencia de ejecución. | CALIDAD autoriza; roles asignados ejecutan | Un elemento retenido no se usa ni despacha; las cantidades de disposición cubren el alcance sin duplicados y se distinguen las pendientes. |
| RF-34 | Verificar tratamiento, decidir de forma justificada si exige AC y vincular F-QP-006 cuando corresponda. | CALIDAD | En NC crítica, repetitiva o sistemática se exige AC vinculada. Una corrección no verificada impide el cierre. |
| RF-35 | Gestionar estados Abierta, En tratamiento, Pendiente de verificación, Cerrada y reapertura con historial; consultar por prioridad, estado, fecha y responsable. | CALIDAD; consulta autorizada | No se cierra una NC con tratamiento pendiente o AC obligatoria sin eficacia verificada. La reapertura conserva fecha y resultado del cierre anterior. |

## 3.2.9. Registro de acciones correctivas

**Fuente:** PR-QP-004 / F-QP-006.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-36 | Crear AC con ID único, motivo, NC vinculadas, hipótesis, evidencias y causas confirmadas. | CALIDAD | Una AC sin NC existente no se guarda; varias NC pueden vincularse a una AC de causa común sin fusionar sus eventos. |
| RF-37 | Registrar acciones por causa, responsables, fechas límite, recursos, evidencia esperada y criterios de eficacia previos a ejecutar. | CALIDAD planifica; GERENCIA aprueba recursos/responsables | No se pasa a ejecución si falta causa confirmada, plan aprobado o criterio medible con período/cantidad mínima y meta. |
| RF-38 | Registrar avances, acciones ejecutadas, retrasos y evidencia; conservar cambios de plazo autorizados. | Responsable asignado / CALIDAD | Una nueva fecha no elimina el plazo original; una acción sin evidencia no se considera ejecutada y verificada. |
| RF-39 | Registrar evaluación de eficacia contra criterios aprobados, con resultado medido y evidencia; gestionar cierre y reapertura. | CALIDAD independiente de la ejecución | Si falta una oportunidad mínima, queda Pendiente. Si un criterio falla, queda No eficaz y retorna al análisis. Solo todos los criterios cumplidos permiten cierre; no cierra automáticamente las NC vinculadas. |

Estados de AC: Abierta, En ejecución, Pendiente de eficacia, En revisión de causa y Cerrada.

## 3.2.10. Consulta de indicadores

**Fuente:** DOC-QP-004, IND-01 a IND-05. Las metas son propuestas del caso académico.

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-40 | Calcular IND-01: unidades distintas con defecto de inspección final / unidades distintas inspeccionadas × 100. | GERENCIA / CALIDAD; otros según alcance | Con 100 unidades inspeccionadas y 4 distintas defectuosas, mostrar 4 %. Dos defectos en una unidad cuentan una vez; una reinspección favorable no borra el defecto original. |
| RF-41 | Calcular IND-02: pedidos entregados completamente en o antes de la fecha acordada válida / pedidos entregados completamente × 100. | GERENCIA / CALIDAD; COMERCIAL/LOGISTICA según alcance | Con 20 pedidos entregados y 19 puntuales, mostrar 95 %. Una modificación posterior al vencimiento no convierte un retraso en puntual. |
| RF-42 | Calcular IND-03: pedidos finalizados con inspección final registrada / pedidos finalizados × 100. | GERENCIA / CALIDAD | En una prueba aislada del cálculo con 10 registros de pedidos finalizados y 9 con inspección final registrada, mostrar 90 %; el flujo normal debe impedir finalizar pedidos sin liberación. una inspección no equivale automáticamente a conformidad. |
| RF-43 | Calcular IND-04: eventos distintos de NC confirmada detectados con registro vinculado / total de eventos distintos de NC confirmada detectados × 100. | GERENCIA / CALIDAD | Si 5 eventos confirmados fueron detectados y 4 tienen F-QP-005, mostrar 80 %. El denominador incluye el evento pendiente de registro. Cerrar una NC no elimina el evento. |
| RF-44 | Registrar un plan básico de mantenimiento preventivo con ID de actividad, equipo, fecha programada, responsable, ejecución y evidencia; calcular IND-05 a partir de dichos registros. | GERENCIA autoriza programación; PRODUCCION registra ejecución; GERENCIA/CALIDAD consultan | Con 4 actividades programadas en el período y 3 ejecutadas a tiempo, mostrar 75 %. Si no hay actividades programadas, mostrar N/D. No se incluye un módulo avanzado de mantenimiento. |
| RF-45 | Filtrar indicadores por mes y mostrar meta, numerador, denominador, valor y estado de cumplimiento; consultar registros de origen autorizados. | Roles según alcance DOC-QP-010 | Con denominador cero, mostrar N/D sin asignar cumplimiento. Un filtro modifica resultados calculados, no cifras fijas. |

### Reglas de cálculo

| Indicador | Fecha de inclusión y regla | Meta |
|---|---|---|
| IND-01 | Unidades cuya primera inspección final se inició en el mes seleccionado; contar defectos confirmados de esas unidades detectados hasta el cierre del mes, sin descontar correcciones. Cada ID cuenta una vez en su cohorte. | ≤ 5 % |
| IND-02 | Pedidos cuya entrega completa ocurrió en el mes seleccionado; comparar fecha de entrega completa con la última fecha acordada aceptada antes o en la fecha límite anterior y antes de la entrega. Las extensiones posteriores al vencimiento se conservan, pero no cambian la evaluación de puntualidad ya incumplida. | ≥ 95 % |
| IND-03 | Pedidos finalizados en el mes seleccionado; contar aquellos con inspección final registrada vinculada al pedido y efectuada antes o al finalizar. | 100 % |
| IND-04 | Eventos confirmados con fecha de detección en el mes; evaluar existencia de NC vinculada al cierre del mes. Un evento no confirmado no entra; su confirmación posterior debe conservar fecha original y permitir revisión histórica identificable. | 100 % |
| IND-05 | Actividades de mantenimiento cuya fecha programada original corresponde al mes; contar ejecuciones con evidencia hasta la fecha programada. Las reprogramaciones conservan el plazo original para medir puntualidad. | 100 % |

El período corresponde al mes calendario en la zona horaria del proyecto (Colombia). Los resultados históricos se calculan con corte al final del período; una corrección legítima de datos debe quedar auditada. Mostrar porcentajes con hasta dos decimales, comparar la meta con el valor sin redondear y mostrar N/D ante denominador cero. No incluir registros de ensayo ajenos al período o conjunto de datos seleccionado.

RF-44 propone los permisos mínimos adicionales de programación y ejecución de mantenimiento para dar soporte a IND-05; no altera las autorizaciones de liberación o de cierre de calidad. La propuesta queda sujeta a revisión junto con este documento.

## 3.2.11. Dashboard o panel principal

| ID | Requisito funcional | Rol autorizado | Criterio de aceptación |
|---|---|---|---|
| RF-46 | Mostrar panel inicial según el rol con navegación hacia sus módulos autorizados. | Todos con sesión activa | ADMIN ve gestión de cuentas y seguridad; PRODUCCION ve lotes asignados; CALIDAD ve inspecciones y NC; GERENCIA ve resumen general; COMERCIAL y LOGISTICA ven sus operaciones. No aparecen acciones ajenas al rol. |
| RF-47 | Mostrar indicadores, cantidades de pedidos por situación operativa, lotes en proceso, unidades retenidas, NC abiertas y AC pendientes/vencidas según alcance. | Roles empresariales autorizados | Al registrar o cambiar un evento válido, la tarjeta correspondiente refleja el dato almacenado al actualizar la consulta. Un campo sin datos se muestra como cero en conteos y N/D en porcentajes sin denominador. |
| RF-48 | Permitir filtrar por período y consultar el detalle del dato agregado, respetando permisos y fuentes. | Roles autorizados | Un filtro mensual actualiza gráficos, tarjetas y detalle con la misma población; un enlace a un registro fuera de alcance queda denegado. |

## 4. Trazabilidad y validación

Los requisitos se usarán como referencia en el diseño del modelo de datos, casos de uso y pruebas. Los formatos F-QP-001 a F-QP-006 son la fuente de campos y validaciones operativas; no se sustituirán por registros de texto sin estructura.

| Apartado del roadmap | Identificadores | Evidencia de origen |
|---|---|---|
| 3.2.1 | RF-01–05 | DOC-QP-010 |
| 3.2.2 | RF-06–07 | PR-QP-001 / F-QP-001 |
| 3.2.3 | RF-08–14 | F-QP-001 / F-QP-004 |
| 3.2.4 | RF-15–17 | F-QP-001 / F-QP-002 |
| 3.2.5 | RF-18–23 | F-QP-002 / F-QP-003 |
| 3.2.6 | RF-24–28 | F-QP-004 |
| 3.2.7 | RF-29–31 | F-QP-004 / F-QP-005 |
| 3.2.8 | RF-32–35 | F-QP-005 |
| 3.2.9 | RF-36–39 | F-QP-006 |
| 3.2.10 | RF-40–45 | DOC-QP-004 |
| 3.2.11 | RF-46–48 | DOC-QP-010 / DOC-QP-004 |

**Total:** 48 requisitos funcionales propuestos, cada uno con criterio de aceptación. Su prioridad de implementación se formalizará en 3.4.5. Estas pruebas son condiciones futuras, no resultados ejecutados.

## 5. Estado y control de cambios

- [x] 3.2.1. Gestión de usuarios.
- [x] 3.2.2. Gestión de clientes.
- [x] 3.2.3. Registro y consulta de pedidos.
- [x] 3.2.4. Gestión de productos y prendas.
- [x] 3.2.5. Registro de producción DTF.
- [x] 3.2.6. Registro de inspecciones.
- [x] 3.2.7. Registro de defectos.
- [x] 3.2.8. Gestión de no conformidades.
- [x] 3.2.9. Registro de acciones correctivas.
- [x] 3.2.10. Consulta de indicadores.
- [x] 3.2.11. Dashboard o panel principal.

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | 48 requisitos funcionales, criterios de aceptación y trazabilidad con el SGC | En revisión |
| 1.0 | 19/11/2026 | Aprobación del usuario | Aprobado |

**Siguiente apartado:** [DOC-QP-012 — Requisitos no funcionales](DOC-QP-012_requisitos_no_funcionales.md) (3.3).

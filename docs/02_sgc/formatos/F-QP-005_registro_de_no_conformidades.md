# F-QP-005 — Registro de no conformidades

| Campo documental | Información |
|---|---|
| Código | F-QP-005 |
| Versión | 1.0 |
| Fecha | 19/11/2026 |
| Actividad | 2.8.9 — Registro de no conformidades |
| Estado | **Formato aprobado para el proyecto académico** |
| Empresa | QualityPrint (ficticia) |
| Proceso | PO-03 — Control de calidad |
| Responsable | Control de calidad |
| Procedimiento | [PR-QP-004 — Gestión de no conformidades](../procedimientos/PR-QP-004_gestion_de_no_conformidades.md) |

## 1. Objetivo

Registrar cada incumplimiento confirmado desde su detección hasta su cierre, identificando el requisito incumplido, el alcance afectado, la disposición aplicada y la evidencia de verificación.

## 2. Definiciones operativas

| Término | Definición |
|---|---|
| No conformidad (NC) | Incumplimiento demostrado de un requisito aplicable al producto, material, proceso o servicio. |
| Evento de detección | Hallazgo identificado en una fuente independiente, que permite rastrear cuándo y dónde se detectó el incumplimiento. |
| Contención | Medida inmediata que impide utilizar, procesar o entregar elementos afectados. |
| Disposición | Decisión sobre el tratamiento del elemento afectado: corrección documental, retrabajo, reposición, devolución o descarte. |
| Corrección | Acción que elimina el incumplimiento detectado en el caso concreto. |
| Acción correctiva (AC) | Acción dirigida a eliminar la causa de una NC para impedir su repetición. |
| Verificación | Comprobación documentada de que el tratamiento se ejecutó y cumple el requisito aplicable. |

## 3. Instrucciones de diligenciamiento

- Un registro por evento de NC confirmado. Asignar ID único; conservar el ID original de detección.
- Registrar los hallazgos procedentes de F-QP-002, F-QP-003, F-QP-004 u otra fuente identificada, incluso después de la entrega.
- Describir el requisito concreto y el resultado observado, aportando evidencia. No utilizar únicamente expresiones como «producto malo» o «error de producción».
- Si un evento incluye varios defectos en una misma unidad, conservar los defectos por separado y contar la unidad una sola vez en el alcance.
- Utilizar «No aplica» con justificación cuando un campo no corresponda al caso; no confundirlo con un dato pendiente.

## 4. Formato para diligenciar

### 4.1. Identificación y detección

| Campo | Dato |
|---|---|
| ID de NC único | |
| Fecha y hora de detección | |
| Fecha y hora de registro | |
| Detector / cargo | |
| Fuente de detección, ID de evento y referencia al registro original | |
| Proceso donde ocurrió | |
| Pedido, lote o material (según aplique) | |
| Requisito incumplido (documento, criterio, versión o especificación del pedido) | |
| Descripción objetiva del incumplimiento (esperado frente a observado) | |
| Evidencia inicial (archivo, fotografía, medición o referencia) | |
| Detectado después de entrega (Sí/No) | |
| Responsable del seguimiento | |
| Fecha límite de tratamiento | |
| Estado actual | Abierta |

### 4.2. Alcance de la no conformidad

| ID de unidad, lote, línea o elemento afectado | Código DEF (si aplica) | Hallazgo / evidencia | Cantidad afectada | Unidad de medida |
|---|---|---|---:|---|
| | | | | |

| Medida de alcance | Valor |
|---|---|
| Total afectado sin duplicados (por unidad de medida) | |
| Elementos adicionales evaluados y resultado | |
| Justificación si no aplica cuantificación | |

Si el evento afecta unidades de distinta naturaleza (por ejemplo, prendas y material), registrar totales separados. Los defectos adicionales de una misma prenda no incrementan el número de prendas afectadas.

### 4.3. Prioridad y contención

| Prioridad | Criterio de asignación | Respuesta inmediata |
|---|---|---|
| Crítica | Riesgo para personas, operación insegura o entrega sin liberación. | Detener la actividad afectada, contener y notificar inmediatamente a Gerencia y Calidad. |
| Mayor | Incumplimiento de requisito del cliente, varias unidades afectadas, pérdida de trazabilidad o repetición. | Bloquear lo afectado, notificar a Calidad antes de continuar y evaluar la causa. |
| Menor | Caso aislado sin impacto en seguridad, trazabilidad ni requisitos del cliente. | Registrar, contener cuando aplique y corregir antes de cerrar. |

Seleccionar la prioridad más alta aplicable.

| Campo | Dato |
|---|---|
| Prioridad asignada (Crítica/Mayor/Menor) | |
| Criterio y justificación | |
| Medida de contención aplicada | |
| Fecha y hora / responsable | |
| Ubicación e identificación de elementos bloqueados | |
| Personas notificadas, fecha, hora y evidencia | |
| Si ocurrió después de entrega: aviso a Comercial/Gerencia y acuerdo con el cliente | |

La comunicación posterior a la entrega no sustituye el historial original del pedido ni su registro de entrega.

### 4.4. Disposición y ejecución

| Elementos afectados (ID o grupo sin traslape) | Cantidad y unidad | Disposición autorizada | Responsable / plazo | Fecha y resultado de ejecución | Evidencia |
|---|---|---|---|---|---|
| | | | | | |

Disposiciones permitidas: corrección documental, retrabajo, reposición, devolución o descarte. Registrar autorización y fecha de decisión:

| Campo | Dato |
|---|---|
| Responsable de Calidad que autoriza la disposición | |
| Fecha de autorización | |
| Justificación de la decisión | |

No liberar ni entregar unidades que continúen incumpliendo requisitos. En una reposición, identificar la unidad nueva y el destino de la original. En una corrección documental, conservar el valor anterior, el cambio, la fecha y el responsable. Los totales de disposición deben cubrir el alcance afectado, sin duplicar unidades; si quedan pendientes, identificarlas expresamente.

### 4.5. Verificación del tratamiento

| Elemento o grupo | Criterio comprobado / método | Resultado (Conforme/No conforme/No aplica justificado) | Referencia de reinspección o evidencia | Verificador / fecha |
|---|---|---|---|---|
| | | | | |

Para retrabajos y reposiciones de prendas, registrar la reinspección en F-QP-004 antes de autorizar la liberación. Para devoluciones o descartes, verificar la ejecución y la segregación o baja correspondiente. Para correcciones documentales, verificar el registro corregido y su historial. Si persiste el incumplimiento, mantener bloqueado el elemento y retornar a tratamiento.

### 4.6. Decisión sobre acción correctiva

| Campo | Dato |
|---|---|
| ¿Se requiere AC? (Sí/No) | |
| Justificación de la decisión | |
| ID de AC vinculada (F-QP-006, cuando corresponda) | |
| Estado y referencia de evidencia de eficacia de la AC | |
| Responsable de la evaluación / fecha | |

Es obligatoria una AC en casos críticos, repetitivos o sistemáticos. En los demás casos, justificar si se requiere o no. Diferentes eventos con causa común pueden quedar vinculados a una misma AC sin perder sus IDs de NC.

### 4.7. Cierre

Lista de comprobación del responsable de calidad:

- [ ] Requisito, evento de origen y evidencia identificados.
- [ ] Alcance cuantificado o no aplicación justificada.
- [ ] Contención y disposición ejecutadas, con evidencia.
- [ ] Verificación satisfactoria; elementos sin conformidad no liberados.
- [ ] Decisión de AC justificada; si es obligatoria, eficacia verificada y documentada.
- [ ] Comunicación y tratamiento posterior a entrega documentados, cuando apliquen.

| Campo | Dato |
|---|---|
| Resultado del cierre | |
| Responsable que autoriza el cierre | |
| Fecha y hora de cierre | |
| Evidencia final / referencias | |

## 5. Estados y trazabilidad

| Estado | Condición |
|---|---|
| Abierta | NC registrada; tratamiento por iniciar. |
| En tratamiento | Contención o disposición en ejecución, o incumplimiento pendiente de corregir. |
| Pendiente de verificación | Tratamiento ejecutado; falta verificar resultado o eficacia de AC obligatoria. |
| Cerrada | Todas las condiciones del apartado 4.7 verificadas por Calidad. |

Si reaparece el incumplimiento del mismo evento, reabrir y registrar el motivo sin eliminar el cierre anterior. Una nueva ocurrencia independiente recibe un nuevo ID de NC.

| Fecha y hora | Estado anterior | Estado nuevo | Motivo / evidencia | Responsable |
|---|---|---|---|---|
| | | | | |

## 6. Uso en el indicador y el futuro software

**IND-04 — Registro de no conformidades:** (eventos distintos de NC confirmada con registro F-QP-005 vinculado / total de eventos distintos de NC confirmada detectados en el período) × 100. Meta: 100 %. Si no hay eventos en el período, informar N/D.

El denominador se obtiene de fuentes de detección independientes del F-QP-005. Mantener el historial original para que el cierre, retrabajo o reapertura no eliminen detecciones ni alteren retroactivamente el indicador de conformidad inicial (IND-01).

El futuro software deberá validar ID único, vínculo al evento original, campos obligatorios, estados, prioridades, cantidades, evidencia de disposición y verificación, bloqueo de liberación cuando corresponda y condiciones de cierre. Mantendrá historial de cambios y relación con F-QP-006 cuando se requiera AC.

## 7. Control de versiones

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Plantilla inicial de identificación, alcance, prioridad, tratamiento, verificación y cierre | En revisión |
| 1.0 | 19/11/2026 | Aprobación del usuario | Aprobado |

- [x] **2.8.9.** Registro de no conformidades aprobado para el proyecto académico.

**Siguiente entregable:** [F-QP-006 — Registro de acciones correctivas](F-QP-006_registro_de_acciones_correctivas.md) (2.8.10).

> Plantilla académica sin registros operativos reales. No demuestra certificación del SGC.

# F-QP-006 — Registro de acciones correctivas

| Campo documental | Información |
|---|---|
| Código | F-QP-006 |
| Versión | 1.0 |
| Fecha | 19/11/2026 |
| Actividad | 2.8.10 — Registro de acciones correctivas |
| Estado | **Formato aprobado para el proyecto académico** |
| Empresa | QualityPrint (ficticia) |
| Proceso | PO-03 — Control de calidad |
| Responsable | Control de calidad |
| Procedimiento | [PR-QP-004 — Gestión de no conformidades](../procedimientos/PR-QP-004_gestion_de_no_conformidades.md) |
| Registro de origen | [F-QP-005 — Registro de no conformidades](F-QP-005_registro_de_no_conformidades.md) |

## 1. Objetivo

Identificar la causa comprobada de una no conformidad, ejecutar acciones para eliminarla o controlarla y verificar con evidencia que se cumple el criterio de eficacia definido antes de la ejecución.

## 2. Definiciones

| Término | Definición operativa |
|---|---|
| Corrección | Acción que resuelve el incumplimiento detectado en el caso concreto; se registra en F-QP-005. |
| Causa raíz | Factor demostrado mediante evidencias cuya eliminación evita la repetición de la falla. |
| Acción correctiva (AC) | Medida dirigida a eliminar la causa de una NC y evitar su repetición. |
| Recurrencia | Nuevo evento independiente de NC del mismo tipo asociado a la causa evaluada. |
| Evidencia de ejecución | Registro que demuestra que la acción planificada fue implementada. |
| Eficacia | Cumplimiento del criterio medible y previamente aprobado para demostrar el control de la causa. |

Una acción ejecutada no se considera eficaz hasta completar la evaluación prevista.

## 3. Reglas de aplicación

- Crear F-QP-006 obligatoriamente cuando una NC sea crítica, repetitiva o evidencie falla sistemática. Para los demás casos, Calidad justifica la decisión en F-QP-005.
- Asignar un ID único de AC. Vincular una o varias NC si existe evidencia de causa común; conservar sus identificadores independientes.
- Calidad dirige el análisis, verifica la ejecución y autoriza el cierre; Gerencia asigna recursos y responsables.
- No cerrar la AC por ausencia de nuevas NC si no se cumple el período o la cantidad de oportunidades de evaluación prevista.
- No cerrar una NC que requiera AC mientras esta no tenga eficacia verificada; su contención, disposición y reinspección se gestionan por separado en F-QP-005.

## 4. Formato para diligenciar

### 4.1. Identificación

| Campo | Dato |
|---|---|
| ID de AC | |
| Fecha de apertura | |
| Proceso afectado | |
| Descripción objetiva del problema | |
| Motivo de apertura (crítica, repetitiva, sistemática u otro justificado) | |
| Responsable del análisis | |
| Responsable de seguimiento (Calidad) | |
| Estado actual | Abierta |

| ID de NC vinculada | Requisito incumplido | Prioridad | Fecha de detección | Referencia a evidencia |
|---|---|---|---|---|
| | | | | |

### 4.2. Análisis de causa

| Campo | Dato |
|---|---|
| Método (cinco porqués u otro justificado) | |
| Fuentes consultadas (registros, equipo, materiales, método, condiciones) | |
| Alcance: otros pedidos, lotes o procesos expuestos a la misma causa | |
| Responsable y fecha del análisis | |

| ID de causa | Hipótesis o factor analizado | Evidencia que confirma o descarta | Resultado (Confirmada/Descartada/Pendiente) |
|---|---|---|---|
| | | | |

| Campo | Dato |
|---|---|
| Causa raíz confirmada y relación con el incumplimiento | |
| Evidencia que sustenta la conclusión | |
| Decisión de Calidad y fecha | |

Si la evidencia es insuficiente, mantener el análisis abierto. No registrar como causa confirmada una suposición, ni confundir el defecto observado con su causa.

### 4.3. Plan de acción

| ID de acción | ID de causa confirmada | Acción concreta | Responsable | Recursos | Fecha límite | Evidencia esperada |
|---|---|---|---|---|---|---|
| | | | | | | |

| Campo | Dato |
|---|---|
| Aprobación del plan (Gerencia / Calidad) | |
| Fecha de aprobación | |
| Documentos, procedimientos o riesgos que deben actualizarse | |

Cada causa confirmada debe tener al menos una acción asociada. Describir qué se cambia, dónde y cómo podrá comprobarse. Si una acción afecta documentación aprobada, aplicar DOC-QP-009 y conservar la versión anterior.

### 4.4. Plan de verificación de eficacia (antes de ejecutar)

| ID de criterio | Causa / acciones evaluadas | Variable o condición a medir | Valor inicial y fuente (si aplica) | Meta o límite de aceptación | Método y fuente de evidencia | Período o cantidad mínima de oportunidades | Fecha prevista / verificador |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

| Campo | Dato |
|---|---|
| Responsable de Calidad que aprueba los criterios | |
| Fecha de aprobación | |

El criterio debe indicar qué se comprobará, cuánto se acepta, con qué registros y durante cuánto tiempo o cuántos lotes/unidades. Si no se dispone de valor inicial, justificarlo y definir un criterio comprobable.

**Ejemplo ilustrativo (no ejecutado):** ante uso repetido de diseños de versión obsoleta, si se confirma acceso a archivos sustituidos, bloquear esas versiones. Verificar en los tres lotes siguientes que el 100 % de los diseños utilizados corresponden a la versión aprobada y que no se registra ningún uso de diseños obsoletos. Fuente: versión del diseño en F-QP-001 y registros de F-QP-003. Si se evalúan menos de tres lotes, la eficacia continúa pendiente.

### 4.5. Ejecución y seguimiento

| ID de acción | Fecha de ejecución | Resultado concreto | Evidencia | Responsable | Estado (Pendiente/En curso/Ejecutada) |
|---|---|---|---|---|---|
| | | | | | |

| Fecha | Desviación o retraso | Motivo | Nuevo plazo y autorización | Responsable |
|---|---|---|---|---|
| | | | | |

No sustituir los plazos originales. Registrar cambios aprobados y su justificación. Calidad verifica que todas las acciones previstas se ejecutaron.

### 4.6. Evaluación de eficacia

| ID de criterio | Período y cantidad realmente evaluados | Resultado medido | Meta aprobada | Evidencia y referencia de nuevas NC (si existen) | Resultado (Cumple/No cumple/Pendiente) | Verificador / fecha |
|---|---|---|---|---|---|---|
| | | | | | | |

| Decisión | Condición |
|---|---|
| Eficaz | Todas las acciones ejecutadas, todas las oportunidades mínimas evaluadas y todos los criterios aprobados cumplidos con evidencia. |
| No eficaz | Al menos un criterio incumplido; reabrir análisis, investigar y ajustar el plan. |
| Pendiente | La ejecución, la observación o la evidencia es insuficiente para decidir. |

Cuando el resultado sea No eficaz, conservar la evaluación fallida y registrar el nuevo ciclo de análisis, acciones y criterios. No modificar retroactivamente las metas para convertir un resultado desfavorable en favorable.

### 4.7. Cierre

- [ ] NC vinculadas y causas confirmadas con evidencia.
- [ ] Plan aprobado y acciones ejecutadas.
- [ ] Criterios definidos antes de ejecutar y evaluados con evidencia suficiente.
- [ ] Decisión de eficacia favorable.
- [ ] Cambios documentales y actualización de riesgos realizados cuando corresponda.
- [ ] Resultado comunicado y vinculado a cada F-QP-005 asociado.

| Campo | Dato |
|---|---|
| Decisión de eficacia (Eficaz/No eficaz/Pendiente) | |
| Conclusión y referencia a evidencias | |
| Documentos y riesgos actualizados o justificación de no aplicación | |
| Responsable de Calidad que autoriza el cierre | |
| Fecha de cierre | |
| Referencias de NC vinculadas notificadas | |

El cierre de la AC satisface el requisito de eficacia de las NC vinculadas, pero no cierra automáticamente una NC cuyo tratamiento y verificación estén pendientes.

## 5. Estados del registro

| Estado | Condición |
|---|---|
| Abierta | AC registrada; análisis de causa y plan pendientes o en elaboración. |
| En ejecución | Plan aprobado; acciones pendientes o en curso. |
| Pendiente de eficacia | Acciones ejecutadas; evaluación de eficacia aún pendiente. |
| En revisión de causa | Evaluación no eficaz o AC reabierta; análisis y plan deben revisarse. |
| Cerrada | Calidad verificó eficacia y cumplió todos los criterios de cierre. |

Si después del cierre se detecta una nueva NC asociada a la misma causa, evaluar la vinculación y reapertura de la AC. Preservar el cierre anterior, los resultados y las fechas; registrar la decisión y el nuevo evento con su ID propio.

| Fecha y hora | Estado anterior | Estado nuevo | Motivo / referencia | Responsable |
|---|---|---|---|---|
| | | | | |

## 6. Reglas para el futuro software

- Validar ID de AC único y existencia de las NC vinculadas.
- Bloquear la transición a ejecución sin causa demostrada, plan aprobado y criterios de eficacia definidos.
- No permitir cierre sin evidencia de ejecución, resultado favorable de todos los criterios y autorización de Calidad.
- Conservar plazos, resultados, versiones del plan, historial de reaperturas y vínculos con NC.
- Permitir consultar acciones pendientes, vencidas, en evaluación y cerradas, sin confundir ejecución con eficacia.
- Utilizar los eventos de NC de origen para IND-04 y preservar el historial original de defectos para IND-01; el cierre de una AC no modifica dichos resultados.

## 7. Control de versiones

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Plantilla inicial de análisis de causa, plan, ejecución, eficacia y cierre | En revisión |
| 1.0 | 19/11/2026 | Aprobación del usuario | Aprobado |

- [x] **2.8.10.** Registro de acciones correctivas aprobado para el proyecto académico.

**Siguiente etapa:** [DOC-QP-010 — Identificación de usuarios, roles y permisos](../../03_requisitos/DOC-QP-010_usuarios_roles_y_permisos.md) (3.1).

> Plantilla académica sin registros operativos reales. No acredita certificación del SGC.

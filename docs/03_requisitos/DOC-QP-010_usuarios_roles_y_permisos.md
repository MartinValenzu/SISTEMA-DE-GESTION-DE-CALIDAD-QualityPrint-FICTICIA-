# DOC-QP-010 — Identificación de usuarios, roles y permisos

| Campo documental | Información |
|---|---|
| Código | DOC-QP-010 |
| Apartado | 3.1 — Identificación de usuarios |
| Versión | 0.1 |
| Fecha | 19/11/2026 |
| Estado | **En revisión** |
| Proyecto | QualityPrint — Aplicación web de gestión de calidad |
| Elaboración | Responsable del proyecto |
| Revisión propuesta | Gerencia y Control de calidad |
| Aprobación del portafolio | Pendiente de confirmación del usuario |

## 1. Objetivo y alcance

Definir quién utilizará la aplicación, qué operaciones podrá realizar cada usuario y qué decisiones estarán restringidas a un rol específico. Esta especificación se utilizará al elaborar los requisitos funcionales, los casos de uso y el diseño de la base de datos.

**Referencias:** [DOC-QP-003 — Cargos](../02_sgc/DOC-QP-003_informacion_general_empresa.md), [PR-QP-001 — Pedidos](../02_sgc/procedimientos/PR-QP-001_recepcion_de_pedidos.md), [PR-QP-002 — Producción](../02_sgc/procedimientos/PR-QP-002_produccion_dtf.md), [PR-QP-003 — Inspección](../02_sgc/procedimientos/PR-QP-003_inspeccion_de_calidad.md) y [PR-QP-004 — No conformidades](../02_sgc/procedimientos/PR-QP-004_gestion_de_no_conformidades.md).

## 2. Definiciones

| Término | Definición |
|---|---|
| Usuario | Cuenta individual que identifica a una persona mediante sus credenciales. |
| Rol | Conjunto de permisos asignado a una cuenta según su función. |
| Permiso | Autorización para ejecutar una operación concreta sobre un módulo o registro. |
| Autenticación | Comprobación de la identidad del usuario antes de acceder. |
| Autorización | Comprobación de que el usuario tiene permiso para ejecutar la operación solicitada. |
| Trazabilidad | Registro de quién realizó una operación, cuándo y sobre qué dato. |

QualityPrint tiene cinco cargos empresariales. El sistema propone seis roles lógicos: los cinco cargos existentes y un rol adicional de administración técnica. Esto **no supone contratar un sexto trabajador**. Gerencia puede asumir la administración técnica mediante una asignación expresa, sin que ese rol le otorgue permisos de Calidad. Cada trabajador conserva una cuenta individual; no se comparten credenciales.

## 3.1.1. Usuario administrador

**Código de rol:** ADMIN.

Responsable técnico de las cuentas y permisos de la aplicación.

- Crear, consultar, actualizar y desactivar cuentas.
- Asignar o retirar roles autorizados por Gerencia.
- Gestionar restablecimientos de credenciales sin consultar contraseñas.
- Consultar eventos de seguridad y administrar las copias de seguridad.

**Restricción:** el rol ADMIN por sí solo no modifica pedidos, registros de producción o inspecciones, no libera prendas y no cierra NC ni AC. No puede borrar el historial de operaciones. Un usuario no puede asignarse nuevas facultades a sí mismo; los cambios de roles requieren autorización de Gerencia, registrada, y deben respetar las incompatibilidades definidas.

## 3.1.2. Gerente

**Código de rol:** GERENCIA.

Responsable de supervisar las actividades y tomar decisiones administrativas.

- Consultar pedidos, producción, inspecciones, NC, AC e indicadores de toda la empresa.
- Aprobar recursos y responsables del plan de acciones correctivas.
- Autorizar cambios de roles y consultar el historial de decisiones.
- Atender situaciones excepcionales sin alterar los requisitos de calidad.

**Restricción:** no modifica resultados técnicos de inspección ni autoriza la liberación de unidades no conformes. El acceso de gerencia a indicadores es de consulta, no de edición de sus resultados.

## 3.1.3. Responsable de calidad

**Código de rol:** CALIDAD.

Responsable de verificar el cumplimiento de los requisitos y decidir sobre productos no conformes.

- Registrar inspecciones de materiales, primera pieza e inspección final; identificar defectos.
- Autorizar materiales, primera pieza y liberación final cuando se cumplan los criterios.
- Registrar, clasificar y tratar NC; autorizar disposiciones y verificar correcciones.
- Elaborar y evaluar AC, aprobar criterios de eficacia y cerrar registros cuando proceda.
- Consultar pedidos, producción y evidencias necesarias; revisar indicadores.

**Restricción:** no modifica parámetros de producción registrados por el operador ni datos de aprobación del cliente. No libera unidades retenidas o rechazadas sin tratamiento y verificación conforme.

## 3.1.4. Operador de producción

**Código de rol:** PRODUCCION.

Responsable de ejecutar y documentar el estampado DTF.

- Consultar pedidos confirmados y diseños aprobados asignados a su operación.
- Registrar inspecciones de materiales, lotes, parámetros, insumos, cantidades y autocontroles.
- Reportar desviaciones, contener unidades afectadas y ejecutar retrabajos autorizados.
- Registrar evidencias de acciones que le hayan sido asignadas y entregar el lote a Calidad.

**Restricción:** no modifica la aprobación del cliente, no autoriza la primera pieza, no decide la liberación final y no cierra NC o AC.

## 3.1.5. Permisos y responsabilidades

### 3.1.5.1. Roles complementarios

Para cubrir los procesos ya aprobados, se definen también los dos cargos restantes:

| Rol | Operaciones permitidas | Restricción |
|---|---|---|
| COMERCIAL — Comercial y diseño | Gestionar clientes, pedidos, catálogo comercial y especificaciones; registrar la aprobación del diseño por el cliente y modificaciones aceptadas; registrar reclamaciones. | No aprueba en nombre del cliente ni cambia silenciosamente las versiones aceptadas; no libera productos. |
| LOGISTICA — Administración y logística | Registrar recepción de insumos, consultar cantidades autorizadas, registrar empaque y despacho, tramitar devolución o reposición autorizada. | No modifica especificaciones del pedido ni incluye en el despacho unidades que Calidad no haya liberado. |

El cliente y el proveedor intervienen en el proceso empresarial, pero **no tendrán cuenta en el MVP interno**. Comercial registra su comunicación y conserva la evidencia.

### 3.1.5.2. Matriz de permisos del MVP

**Convenciones:** E = crear o actualizar registros autorizados; C = consultar; A = autorizar la decisión indicada (incluye consulta); — = acceso denegado. E no incluye eliminar registros, aprobar decisiones reservadas a otro rol ni cambiar registros cerrados. Los permisos se aplican a registros de la función o asignación indicada; Gerencia y Calidad consultan los registros empresariales necesarios para supervisión y trazabilidad.

| Operación | ADMIN | GERENCIA | CALIDAD | PRODUCCION | COMERCIAL | LOGISTICA |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Administrar cuentas y aplicar roles autorizados | E | C | — | — | — | — |
| Autorizar cambios de roles | C | A | — | — | — | — |
| Gestionar clientes, pedidos y catálogo | — | C | C | C* | E | C* |
| Registrar aprobación o cambio aceptado por cliente | — | C | C | C* | E | C* |
| Registrar recepción de insumos | — | C | C | C* | — | E |
| Inspeccionar materiales | — | C | E | E | — | C* |
| Autorizar uso de materiales y primera pieza | — | C | A | C* | — | C* |
| Registrar lote, parámetros y autocontroles | — | C | C | E | C* | C* |
| Inspección final y defecto de inspección | — | C | E | C* | C* | C* |
| Autorizar liberación final o retención | — | C | A | C* | C* | C* |
| Reportar evento de detección de NC | — | E | E | E | E | E |
| Confirmar NC y determinar prioridad/disposición | — | C | E/A | C* | C* | C* |
| Registrar ejecución de disposición asignada | — | C | E | E* | E* | E* |
| Planificar AC y criterios de eficacia | — | C | E/A | C* | C* | C* |
| Aprobar recursos y responsables de AC | — | A | C | — | — | — |
| Registrar ejecución de acción asignada | — | E* | E | E* | E* | E* |
| Verificar eficacia y autorizar cierre de NC/AC | — | C | A | C* | C* | C* |
| Registrar empaque y despacho | — | C | C | — | C* | E |
| Consultar indicadores y dashboard | — | C | C | C* | C* | C* |
| Consultar eventos de seguridad | C | C** | — | — | — | — |
| Gestionar copias de seguridad | E | C** | — | — | — | — |

\* Acceso limitado: Producción consulta especificaciones técnicas y registros de sus lotes; Comercial consulta el avance de sus pedidos y reclamaciones; Logística consulta datos necesarios de insumos y entregas. En ejecución de disposición o AC, registrar solo las tareas asignadas. Los paneles operativos muestran únicamente datos de la función/alcance permitido (sin contactos de clientes innecesarios).
 
\** Gerencia consulta el historial de autorizaciones y estado de respaldos; no consulta secretos ni descarga bases de datos mediante ese permiso.

### 3.1.5.3. Reglas de autorización

| ID | Regla verificable |
|---|---|
| PER-01 | Una cuenta sin rol autorizado o inactiva no accede a funciones protegidas. |
| PER-02 | El servidor comprobará permisos en cada operación, incluso si se intenta invocar una ruta directamente. La interfaz ocultará acciones no autorizadas. |
| PER-03 | Solo CALIDAD puede autorizar la primera pieza y liberación definitiva. La persona que registró la producción de un lote no puede autorizar su liberación final, aunque tenga ambos roles. |
| PER-04 | Solo COMERCIAL registra la conformidad del cliente; un cambio de diseño genera una versión nueva y conserva la anterior. |
| PER-05 | Solo LOGISTICA registra el despacho de unidades liberadas; el sistema valida cantidades y requisitos pendientes antes de guardar. |
| PER-06 | Solo CALIDAD confirma NC, autoriza disposición y cierra NC/AC si se cumplen F-QP-005/F-QP-006. El responsable que ejecuta una AC puede registrar evidencia, pero no verificar su propia eficacia. |
| PER-07 | Registrar actor, fecha, operación, registro afectado y cambios de estado, así como valores anteriores y motivo de correcciones relevantes. Desactivar cuentas en lugar de eliminarlas. |
| PER-08 | Usuarios con varios roles reciben las operaciones de sus roles autorizados, excepto cuando exista conflicto de separación de responsabilidades: prevalece la restricción. No se permiten cambios autoautorizados de privilegios. |

El rol ADMIN no es una cuenta empresarial con acceso ilimitado. Las asignaciones de roles y las autorizaciones de Gerencia quedan registradas. Si la persona que ejecuta una AC también tiene CALIDAD, Gerencia deberá designar otra persona competente con el rol CALIDAD para verificarla; mientras no exista verificador independiente, la AC permanece pendiente. Esta asignación tampoco permite liberar un lote producido por esa misma persona.

La gestión inicial de la primera cuenta ADMIN se definirá en la etapa 5 mediante un procedimiento de inicialización controlado.

### 3.1.5.4. Criterios de aceptación para pruebas futuras

| Caso | Resultado esperado |
|---|---|
| Cuenta desactivada intenta iniciar sesión | Acceso denegado. |
| Operador intenta autorizar una liberación | Operación denegada; registro sin cambios. |
| Usuario con PRODUCCION y CALIDAD intenta liberar su propio lote | Operación denegada por separación de funciones. |
| Comercial registra aprobación del cliente con evidencia | Aprobación guardada, vinculada a pedido y versión de diseño. |
| Logística intenta despachar una unidad retenida | Despacho bloqueado. |
| Calidad intenta cerrar NC con AC obligatoria no eficaz | Cierre bloqueado. |
| Administrador sin otro rol intenta editar una inspección | Operación denegada. |
| Responsable de ejecución intenta verificar eficacia de su propia AC | Operación denegada. |
| Usuario autorizado corrige un registro cerrado mediante el flujo previsto | Se conserva versión/valor anterior, motivo y responsable. |

Estas son condiciones de aceptación de la futura aplicación; no se declara que el software esté implementado ni probado.

## 4. Estado del roadmap

- [ ] 3.1.1. Definir el usuario administrador.
- [ ] 3.1.2. Definir el gerente.
- [ ] 3.1.3. Definir el responsable de calidad.
- [ ] 3.1.4. Definir el operador de producción.
- [ ] 3.1.5. Definir permisos y responsabilidades.

Todos los apartados están redactados y pendientes de aprobación.

## 5. Control de cambios

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Identificación de usuarios, roles, matriz de permisos y criterios de autorización | En revisión |

**Siguiente apartado:** 3.2 — Requisitos funcionales del software.

# DOC-QP-016 — Diseño de interfaz del software

| Campo documental | Información |
|---|---|
| Código | DOC-QP-016 |
| Apartado | 4.3 — Diseño de interfaz |
| Versión | 1.0 |
| Fecha | 19/11/2026 |
| Estado | **Aprobado para el proyecto académico** |
| Proyecto | QualityPrint-SGC (empresa ficticia) |
| Elaboración | Responsable del proyecto |
| Revisión propuesta | Responsable del proyecto / Control de calidad |
| Aprobación del portafolio | Confirmada por el usuario el 19/11/2026 |

## 1. Objetivo

Definir la apariencia, navegación, estructura de pantallas y comportamiento esperado de los formularios de QualityPrint, de modo que los usuarios puedan ejecutar sus tareas sin confundir registro, autorización, liberación ni cierre.

**Base:** [DOC-QP-010 — Roles](../03_requisitos/DOC-QP-010_usuarios_roles_y_permisos.md), [DOC-QP-011 — RF](../03_requisitos/DOC-QP-011_requisitos_funcionales.md), [DOC-QP-012 — RNF](../03_requisitos/DOC-QP-012_requisitos_no_funcionales.md), [DOC-QP-013 — Casos de uso](../03_requisitos/DOC-QP-013_analisis_del_funcionamiento.md), [DOC-QP-014 — Arquitectura](DOC-QP-014_diseno_de_arquitectura.md), [DOC-QP-015 — Base de datos](DOC-QP-015_diseno_de_base_de_datos.md).

**Prototipo navegable:** [prototipo_interfaz.html](prototipo_interfaz.html). Descargar el archivo desde GitHub y abrirlo en el navegador local. Incluye 13 pantallas de menú y 3 vistas adicionales de detalle/formulario, selector de rol simulado, filtros de muestra y un formulario de pedido de ejemplo. No usa backend, no autentica, no guarda datos, no autoriza operaciones ni prueba seguridad. Los botones de acción muestran una vista informativa cuando su flujo real aún no existe. Los datos son ficticios.

## 4.3.1. Identidad visual

### Paleta de colores

| Elemento | Color | Uso |
|---|---|---|
| Primario | #145E75 | Botón principal, navegación y énfasis |
| Azul oscuro | #123B4C | Menú lateral e identidad |
| Cian | #4BC1D2 | Monograma QP y acento |
| Fondo general | #F3F6F8 | Área de trabajo |
| Superficies | #FFFFFF | Formularios, tablas, tarjetas |
| Texto | #172D3C | Contenido y títulos |
| Texto secundario | #506474 | Ayudas, metadatos |
| Bordes | #D4DFE5 | Separación de secciones |
| Verde | #166534 | Conforme, liberado o meta cumplida |
| Ámbar | #854D0E | Pendiente, retenido o advertencia |
| Rojo | #991B1B | Incumplimiento, bloqueo o error |

**Identidad:** monograma QP con nombre QualityPrint y subtítulo Sistema de gestión de calidad. Es identidad propuesta del proyecto, no un logotipo registrado ni marca de certificación.

**Tipografía:** familia de sistema sans-serif, texto base 15 px, títulos de página 30 px en escritorio y 25 px en móvil, títulos de secciones 17 px. Códigos y cantidades legibles; no depender de tipografía externa.

**Componentes:** botones de acción principal con fondo primario; secundarios con borde; acciones sensibles requieren confirmación y contexto. Tarjetas y tablas con bordes suaves, radios de 8–12 px, separación de 12–24 px. Todo estado incluye texto además de color. Los contrastes y tamaños serán comprobados en la interfaz real.

## 4.3.2. Menú de navegación

El diseño utiliza una barra lateral en escritorio, barra superior con identidad del usuario y un área central. El menú de móvil se abre con un botón visible y se cierra al seleccionar un módulo. El panel permanece accesible en máximo tres interacciones.

| Módulo | Roles con acceso | Acción de escritura principal |
|---|---|---|
| Panel principal | Todos | Consulta según rol; ADMIN solo datos técnicos |
| Usuarios y roles | ADMIN, GERENCIA | ADMIN administra; GERENCIA autoriza roles |
| Seguridad y respaldo | ADMIN, GERENCIA | ADMIN gestiona; GERENCIA consulta estado y autoriza restauración |
| Clientes | COMERCIAL, GERENCIA, CALIDAD | COMERCIAL |
| Catálogo | COMERCIAL, GERENCIA, CALIDAD | COMERCIAL |
| Pedidos | COMERCIAL, GERENCIA, CALIDAD, PRODUCCION, LOGISTICA | COMERCIAL confirma y registra aceptación |
| Materiales | LOGISTICA, PRODUCCION, CALIDAD, GERENCIA | LOGISTICA recibe; PRODUCCION/CALIDAD inspeccionan; CALIDAD autoriza uso |
| Producción DTF | PRODUCCION, CALIDAD, GERENCIA, COMERCIAL y LOGISTICA (consulta limitada) | PRODUCCION registra; CALIDAD decide primera pieza |
| Inspecciones / defectos | CALIDAD, GERENCIA; otros roles empresariales según alcance | CALIDAD registra y libera |
| No conformidades | Roles empresariales | Reporte por roles permitidos; CALIDAD confirma, dispone y cierra |
| Acciones correctivas | Roles empresariales según asignación | CALIDAD planifica/verifica; GERENCIA aprueba recursos; asignados ejecutan |
| Despachos | LOGISTICA, CALIDAD, GERENCIA, COMERCIAL (consulta limitada) | LOGISTICA registra |
| Mantenimiento | PRODUCCION, GERENCIA, CALIDAD (consulta) | GERENCIA programa; PRODUCCION registra ejecución |

Los accesos de consulta limitados no muestran contactos innecesarios ni registros ajenos a la función. La asignación múltiple de roles no permite saltar restricciones PER-03, PER-06 y PER-08. La navegación del prototipo muestra separación de módulos; los permisos reales se aplicarán en Flask.

### Acceso al sistema (CU-01)

Pantalla sin menú de negocio: identidad QualityPrint, campos usuario y contraseña, botón Iniciar sesión, aviso de uso interno, mensaje genérico de error. El usuario puede mostrar/ocultar la contraseña con control accesible. No existe registro público de cuentas. La sesión activa muestra usuario, rol y Cerrar sesión; el selector de rol del prototipo no existirá como mecanismo de autorización.

## 4.3.3. Dashboard

**Objetivo:** mostrar situación operativa e indicadores obtenidos desde los registros, según DOC-QP-011.

### Orden de la pantalla

1. Encabezado Panel principal y filtro mensual (mes calendario; mes actual por defecto).
2. Tarjetas operativas según rol: pedidos en curso, lotes en proceso, prendas retenidas, NC abiertas, AC pendientes/vencidas cuando aplique.
3. Tabla o tarjetas de IND-01 a IND-05: valor, numerador, denominador, meta, cumplimiento y vínculo al detalle permitido.
4. Accesos rápidos a módulos del rol y lista de tareas pendientes.

| Indicador | Visualización de ejemplo | Interpretación |
|---|---|---|
| IND-01 Defectos | 4 % (4/100), meta ≤ 5 % | Cumple |
| IND-02 Entregas puntuales | 95 % (19/20), meta ≥ 95 % | Cumple |
| IND-03 Cobertura de inspección | 100 % (20/20), meta 100 % | Cumple |
| IND-04 Registro NC | 80 % (4/5), meta 100 % | No cumple |
| IND-05 Mantenimiento | N/D (0/0), meta 100 % | Sin datos |

Son valores de demostración estáticos del prototipo. En producción cada indicador se calculará desde SQLite, con filtro y reglas de corte aprobados. Cambiar el mes actualiza las tarjetas, gráficos y detalle sobre la misma población; no se inventan datos. Con denominador cero se muestra N/D y sin dictamen de cumplimiento.

**Por rol:** ADMIN ve cuentas y eventos técnicos; GERENCIA ve panorama general; CALIDAD ve inspecciones, retenciones, NC/AC e indicadores autorizados; PRODUCCION ve lotes asignados y tareas; COMERCIAL ve pedidos/diseños de su alcance; LOGISTICA ve recepción y entregas.

## 4.3.4. Módulo de pedidos

| Vista | Campos y controles principales |
|---|---|
| Listado | Código, cliente/referencia autorizada, fecha acordada, estado comercial, avance operativo, botón Ver. Filtros por código, cliente, fecha y estado. |
| Nuevo pedido | Cliente activo, modalidad, fechas, líneas de variantes y cantidades, especificaciones, condiciones y cálculo del total. Guardar pendiente. |
| Detalle / revisión | Identidad, versión vigente, historial, líneas y diseños vinculados. Pestañas identificación, requisitos, diseño, producción, calidad y entrega. |
| Diseño | Versión de arte, referencia, dimensiones, posición, orientación, tolerancias y evidencia de aceptación. |
| Transferencia | Cuatro controles: pedido confirmado/viable, diseños vigentes aprobados, disponibilidad confirmada y requisitos completos. |
| Entrega | Unidades liberadas por línea, despachos y recepciones; cantidad pendiente y fecha final derivada. |

**Botones:** COMERCIAL puede crear, editar borrador, confirmar, registrar aprobación del cliente, solicitar modificación, cancelar y autorizar transferencia si procede. Otros roles consultan el alcance correspondiente.

**Bloqueos:** cantidad inválida, arte pendiente, cliente/instrucción no válidos o falta de aceptación impiden confirmar o transferir según el caso. La nueva versión de requisitos no sobrescribe la aceptada anterior. Cancelación exige motivo y confirmación. Las fechas originales y vigentes se muestran en historial.

El formulario de muestra del HTML solo ejemplifica una línea; la interfaz real permitirá varias líneas y sus diseños conforme F-QP-001.

## 4.3.5. Módulo de producción DTF

| Vista | Datos y acciones |
|---|---|
| Materiales y recepción | Partida, proveedor, referencia, cantidad/unidad, vencimiento si aplica, criterios C/NC/P/NA, evidencia, decisión de Calidad. |
| Lotes | Código, pedido/versión, líneas, cantidades, operador, configuración, estado. Filtros por pedido, estado y fecha. |
| Preparar lote | Equipos, instrucciones técnicas validadas, insumos liberados, líneas de pedido, unidades asignadas. |
| Primera pieza | Unidad, versión de configuración, resultados, evidencia, aceptación de Calidad. |
| Controles | Operación, parámetro, rango aprobado, valor observado, unidad de medida, resultado y observaciones. |
| Cierre | Procesadas, aptas para inspección, retenidas, descartadas y pendientes; conciliación y entrega a Calidad. |

**Acciones:** el operador registra materiales, configuración y controles; Calidad autoriza material y primera pieza. Si no hay primera pieza aceptada, la pantalla presenta bloqueo con causa y no habilita continuar con el resto del lote. Cambios de configuración invalidantes requieren nueva aceptación. No se controlará directamente la impresora desde el software.

## 4.3.6. Módulo de inspecciones

| Sección | Contenido y acción |
|---|---|
| Listado | Código de inspección, pedido, lote, fecha, número de unidades, estado y responsable. |
| Identificación individual | ID de prenda, revisión, línea, diseño(s), resultado y vínculo a inspección previa. |
| Criterios | DEF-01 a DEF-10, C/NC/P/NA, evidencias, dimensiones/posiciones, tolerancia, valor observado y unidad. |
| Pruebas adicionales | Método y criterio aprobados, muestra, resultado y evidencia cuando se exija. |
| Hallazgos | Código DEF, ID de unidad/revisión, evidencia, evento independiente y vínculo a NC. |
| Conciliación | A = B + C; B = D + E + F; G ≤ B; H ≤ D, según F-QP-004. Resultados actuales y defectos históricos diferenciados. |
| Liberación | IDs conformes, cantidad por línea, permiso parcial del cliente cuando aplique, confirmación y fecha de autorización. |

**Resultado:** estados de unidad siempre visibles (conforme, retenida, rechazada, pendiente de evaluación; liberada es autorización aparte). Una prenda con dos defectos sigue siendo una prenda. La reinspección crea otra revisión sin borrar la inicial. Los datos de la operación y los permisos de Calidad son comprobados por el servidor; la interfaz muestra el motivo de bloqueo.

## 4.3.7. Módulo de no conformidades y AC

### No conformidades

| Vista | Datos y controles |
|---|---|
| Eventos de detección | ID independiente, origen, requisito, descripción, fecha, evidencia y decisión de Calidad. |
| Listado NC | Código, origen, prioridad, responsable, plazo, estado, búsqueda y filtros. |
| Detalle NC | Identificación, alcance, cantidades, contención, notificaciones, disposición y responsable. |
| Tratamiento | Ejecución, plazo, evidencia, verificación y reinspección vinculada si aplica. |
| Cierre | Decisión sobre AC, vínculo a AC cuando corresponda, condición de cierre, motivo e historial. |

Los estados son Abierta, En tratamiento, Pendiente de verificación y Cerrada. Mostrar prioridad crítica/mayor/menor con texto. Si hay AC obligatoria sin eficacia o tratamiento no verificado, el botón Cerrar NC aparece bloqueado con explicación. Solo Calidad confirma y cierra; otros actores reportan o registran la tarea asignada.

### Acciones correctivas

| Sección | Datos |
|---|---|
| Apertura | ID AC, NC vinculadas, motivo, proceso, responsable y estado |
| Análisis | Método, hipótesis, evidencia, causa confirmada |
| Plan | Acciones por causa, recursos, responsable, plazo, criterio cuantificable y aprobaciones |
| Ejecución | Avances, fecha, resultados, evidencia y cambios de plazo |
| Eficacia | Criterio, período/cantidad mínima, resultado observado, meta, fuente y verificador independiente |
| Cierre | Eficaz / No eficaz / Pendiente, decisión, evidencia, documentos/riesgos e historial |

Los estados son Abierta, En ejecución, Pendiente de eficacia, En revisión de causa y Cerrada. Ejemplo de bloqueo: 2 de 3 lotes evaluados no permiten cierre. Una evaluación no eficaz conserva historial y retorna a revisión de causa. Cierre de AC no equivale a cierre automático de NC.

## 4.3.8. Formularios, tablas y filtros

### Componentes reutilizables

| Componente | Especificación |
|---|---|
| Formulario | Título, descripción breve, etiquetas visibles, indicador de campos obligatorios, ayuda, mensajes junto a campo y acciones Guardar/Cancelar. |
| Selector relacional | Buscar o escoger registro existente permitido; mostrar código y descripción; no aceptar cadenas como FK arbitraria. |
| Entrada de cantidad | Entero positivo en prendas; unidad visible y precisión definida para insumos/parámetros. |
| Fecha y hora | Formato local de presentación dd/mm/aaaa; valores internos según DOC-QP-015. |
| Confirmación sensible | Mostrar registro, operación, efecto y condición; botón secundario Cancelar y principal Confirmar. |
| Tabla | Cabecera semántica, filas legibles, estado textual, acción Ver; desplazamiento interno en móvil, sin desbordamiento global. |
| Filtros | Búsqueda, estado, rango de fechas y filtros de módulo; botón Limpiar, cantidad de resultados y paginación 25 por defecto / máximo 100. |
| Estado vacío | Texto «No hay registros para los filtros seleccionados» y opción Limpiar filtros. No mostrar números ficticios como si fueran reales. |
| Mensajes | Éxito con ID; error de validación específico; permiso denegado sin datos privados; conflicto de versión con acción Recargar. |
| Historial | Fecha, responsable, acción, revisión, motivo y referencia de evidencia; consulta sin sobrescribir registros. |

Los botones no autorizados no se muestran. Un botón del rol autorizado pero temporalmente bloqueado por estado puede aparecer deshabilitado con explicación visible; la validación del servidor permanece obligatoria. No permitir eliminación irreversible de registros históricos desde formularios ordinarios.

### Vistas complementarias

- Clientes/catálogo: listado, datos mínimos, variantes y desactivación con historial.
- Despachos: selección exclusiva de unidades liberadas vigentes, verificación de cantidades, registro de recepción y evidencia por unidad.
- Mantenimiento: equipo, fecha original/vigente y evidencia de ejecución.
- Administración: cuentas, roles autorizados, desactivación y restablecimiento de credencial; no mostrar hash ni contraseña.
- Soporte: eventos técnicos y estado de copias de seguridad; restauración operativa mediante procedimiento controlado, no botón público de sustitución de base.

## 4.3.9. Revisión de experiencia de usuario

### Adaptación por tamaño

| Ventana | Estructura propuesta |
|---|---|
| 1366 px | Menú lateral de 236 px, barra superior y área central; tarjetas en hasta cuatro columnas. |
| 768 px | Menú desplegable, tarjetas en dos columnas, formularios de dos columnas si el ancho lo permite. |
| 360 px | Menú desplegable, formularios de una columna, tarjetas compactas; tablas con desplazamiento interno. |

### Revisión y criterios futuros

| ID | Criterio | Método / estado |
|---|---|---|
| UX-01 | Menú coherente con rol y acceso al panel/listado en máximo tres interacciones | Revisar cada rol, RNF-10; pendiente de prueba visual |
| UX-02 | Campos obligatorios, errores específicos y datos válidos conservados | Probar formulario inválido en aplicación real, RNF-09 |
| UX-03 | Navegación por teclado y foco visible; texto además de color | Probar Tab/Shift+Tab/Enter, RNF-11 |
| UX-04 | Confirmaciones y bloqueos con explicación | Probar liberación, desactivación y cierre, RNF-12 |
| UX-05 | Sin desbordamiento global a 360, 768 y 1366 px | Ensayo en navegador, RNF-13–14 |
| UX-06 | Flujo de pedido e inspección en Chrome y Firefox | Etapa 7, RNF-15 |
| UX-07 | Datos y acciones corresponden a permisos y alcance de registros | Prueba del servidor, PER-01–08 |
| UX-08 | Indicadores y filtros coherentes con registros, N/D cuando corresponde | Prueba de integración, RF-40–48 |

**Verificación realizada sobre la maqueta:** revisión de estructura y sintaxis JavaScript; generación de 52 combinaciones rol/pantalla sin excepción en una comprobación de lógica con DOM simulado. Se verificó la plantilla de nuevo pedido y el retorno al panel si ese formulario se solicita desde ADMIN. La ejecución visual en navegador no pudo completarse en el entorno disponible; quedan pendientes las comprobaciones de interacción real, contraste, teclado y tamaños de ventana. No se declara prueba de la aplicación ni cumplimiento de RNF.

## 5. Trazabilidad y aprobación

| Apartado | Requisitos principales |
|---|---|
| Identidad, componentes y adaptación | RNF-08–15 |
| Navegación y permisos | RF-01–05,46; PER-01–08 |
| Panel e indicadores | RF-40–48 |
| Pedidos y catálogo | RF-06–17 |
| Producción y materiales | RF-18–23 |
| Inspección y defectos | RF-24–31 |
| NC y AC | RF-32–39 |
| Validaciones, historial y mensajes | RNF-09,12,16–20 |

- [x] 4.3.1. Definir identidad visual.
- [x] 4.3.2. Diseñar menú de navegación.
- [x] 4.3.3. Diseñar dashboard.
- [x] 4.3.4. Diseñar módulo de pedidos.
- [x] 4.3.5. Diseñar módulo de producción.
- [x] 4.3.6. Diseñar módulo de inspecciones.
- [x] 4.3.7. Diseñar módulo de no conformidades.
- [x] 4.3.8. Diseñar formularios, tablas y filtros.
- [x] 4.3.9. Revisar experiencia de usuario — revisión de diseño documental y prototipo; validación visual final pendiente.

Con la aprobación de este diseño se cierra la etapa 4 como diseño documental; las pruebas de visualización e implementación se completarán en etapas 6 y 7. El prototipo no sustituye la aplicación Flask ni sus controles.

## 6. Control de cambios

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | Identidad visual, navegación, pantallas, componentes, criterios UX y prototipo HTML | Sustituido |
| 1.0 | 19/11/2026 | Diseño de interfaz aprobado; validación visual de la implementación pendiente | Vigente |

**Siguiente etapa:** [DOC-QP-017 — Preparación de herramientas](../05_entorno/DOC-QP-017_preparacion_de_herramientas.md).

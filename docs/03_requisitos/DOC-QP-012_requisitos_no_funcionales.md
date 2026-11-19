# DOC-QP-012 — Requisitos no funcionales del software

| Campo documental | Información |
|---|---|
| Código | DOC-QP-012 |
| Apartado | 3.3 — Requisitos no funcionales |
| Versión | 0.1 |
| Fecha | 19/11/2026 |
| Estado | **En revisión** |
| Proyecto | QualityPrint-SGC (empresa ficticia) |
| Elaboración | Responsable del proyecto |
| Revisión propuesta | Gerencia y Control de calidad |
| Aprobación del portafolio | Pendiente de confirmación del usuario |

## 1. Objetivo y alcance

Establecer condiciones comprobables de seguridad, facilidad de uso, adaptación de pantalla, integridad, rendimiento, recuperación y mantenibilidad que deberá cumplir la primera versión de QualityPrint-SGC.

Un requisito no funcional (RNF) establece una propiedad o restricción de calidad del sistema; los requisitos funcionales (RF) especifican las operaciones que realiza. Los valores numéricos de este documento son **metas internas propuestas del MVP**, no resultados medidos ni garantías de certificación.

**Referencias:** [DOC-QP-010 — Roles y permisos](DOC-QP-010_usuarios_roles_y_permisos.md), [DOC-QP-011 — Requisitos funcionales](DOC-QP-011_requisitos_funcionales.md), [DOC-QP-009 — Gestión documental](../02_sgc/DOC-QP-009_gestion_documental.md) y [DOC-QP-002 — Organización y tecnologías](../01_proyecto/DOC-QP-002_organizacion_inicial_del_proyecto.md).

**Contexto técnico:** aplicación web monolítica en Python/Flask, plantillas Jinja2, HTML/CSS/JavaScript y base SQLite con SQLAlchemy; hasta cinco trabajadores concurrentes. El código será público, pero la base, evidencias privadas, credenciales y secretos no formarán parte del repositorio. Usar datos ficticios.

## 3.3.1. Seguridad de acceso

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-01 | Aplicar las autorizaciones de DOC-QP-010 en el servidor, con denegación por defecto y alcance de registro. | Solicitudes a rutas protegidas sin sesión, sin rol, con un ID ajeno al alcance o con conflicto de funciones se rechazan sin revelar ni modificar el registro. |
| RNF-02 | Las contraseñas tendrán entre 12 y 128 caracteres; almacenar únicamente un hash de contraseña con sal individual y costo computacional, mediante una biblioteca confiable. No registrar la contraseña en texto claro ni cifrado reversible. | Dos cuentas con igual contraseña tienen hashes distintos. Una contraseña de 11 caracteres se rechaza, una de 12 y otra de 128 se aceptan; ninguna contraseña aparece en base, registros de actividad ni respuestas. |
| RNF-03 | Limitar intentos de autenticación: tras 5 fallos del mismo usuario en una ventana de 15 minutos, bloquear nuevos intentos durante 15 minutos. Limitar también a 20 intentos por IP en 15 minutos. | El sexto intento del usuario durante el bloqueo se rechaza aunque use otra IP; el intento 21 desde una IP también se limita. Al vencer el período se permite intentar de nuevo. Mensajes no revelan si la cuenta existe. |
| RNF-04 | Finalizar la sesión por cierre voluntario, 30 minutos de inactividad o 8 horas desde inicio, lo que ocurra primero. Revocar sesiones por desactivación, restablecimiento de credenciales o cambio de roles. | La sesión previa no permite acceder tras cualquiera de las condiciones, incluso mediante una solicitud directa. Las pruebas pueden utilizar un reloj controlado. |
| RNF-05 | Proteger solicitudes que cambian datos contra falsificación de solicitudes, tratar entradas no confiables como datos y utilizar consultas parametrizadas mediante la capa de acceso a datos. | Una solicitud de escritura sin token válido se rechaza; una entrada de prueba con sintaxis SQL no altera la consulta y texto con etiquetas HTML se presenta sin ejecutar código. |
| RNF-06 | Mantener secretos fuera del código y de Git, desactivar depuración en despliegues compartidos y exigir HTTPS y cookies de sesión seguras en despliegues accesibles por red. | No aparecen secretos en archivos versionados ni respuestas de error; una instalación compartida utiliza HTTPS, cookies HttpOnly, Secure y SameSite, y no muestra trazas internas. Se admite HTTP solo en desarrollo local de bucle invertido con datos ficticios. |
| RNF-07 | Registrar eventos de autenticación exitosa o fallida, bloqueos, cambios de roles, restablecimientos y rechazos de autorización, con fecha, actor identificable cuando exista, tipo y resultado, sin secretos. | ADMIN puede consultar los eventos; otros roles solo los previstos en DOC-QP-010. El historial no se modifica desde las funciones ordinarias de la aplicación. |

## 3.3.2. Facilidad de uso

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-08 | Utilizar interfaz en español y etiquetas consistentes con los estados y nombres de la documentación aprobada. | Los formularios de pedido, lote, inspección, NC y AC muestran las mismas denominaciones de campos y estados que los documentos fuente. |
| RNF-09 | Mostrar campos obligatorios antes de enviar y mensajes de validación junto al dato incorrecto, conservando los datos válidos enviados. | Al omitir un campo obligatorio o introducir una cantidad inválida, se indica el campo y el motivo; los otros datos del formulario se conservan y no se guarda un registro inválido. |
| RNF-10 | Facilitar navegación uniforme y recuperación de información mediante menú y búsqueda/filtros. | Desde cualquier pantalla autenticada se llega al panel principal y al listado de cada módulo autorizado en máximo 3 interacciones (sin contar inicio de sesión). |
| RNF-11 | Permitir uso con teclado, controles con etiquetas accesibles, foco visible y estados acompañados de texto además del color. | Se completa un formulario de pedido y se navega mediante Tab, Shift+Tab y Enter; el foco es visible y las etiquetas, errores y estados son comprensibles sin depender del color. |
| RNF-12 | Confirmar acciones sensibles antes de ejecutarlas e indicar el resultado después del guardado. | Desactivar una cuenta, cancelar un pedido, autorizar liberación o cerrar NC/AC exige confirmación explícita; cancelar la confirmación no modifica datos. Un guardado correcto muestra confirmación e identificador del registro. |

## 3.3.3. Diseño adaptable a diferentes pantallas

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-13 | Adaptar acceso, menú, panel, listados y formularios a anchos de ventana de 360, 768 y 1366 píxeles CSS. | En cada ancho, la página no presenta desplazamiento horizontal global, superposición ni controles inaccesibles. Las tablas anchas pueden desplazarse dentro de su propio contenedor. |
| RNF-14 | Mantener acciones y contenido esencial disponibles sin depender del paso del puntero. | En una ventana de 360 píxeles se pueden abrir módulos, llenar un formulario, consultar resultados y confirmar decisiones mediante interacción táctil o clic; no se exige un gesto de hover. |
| RNF-15 | Verificar funcionamiento en los navegadores Chrome y Firefox de escritorio instalados para la prueba y sus vistas adaptables. | Ejecutar inicio de sesión, registro de pedido, filtros e inspección en ambos navegadores; registrar versiones y resultados reproducibles sin errores que impidan completar las tareas. |

## 3.3.4. Integridad de la información

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-16 | Garantizar identificadores únicos, vínculos existentes, obligatoriedad y restricciones de datos tanto en base de datos como en la lógica de negocio, según corresponda. | Intentar insertar ID duplicado, referencia inexistente, cantidad de prenda negativa o campo obligatorio vacío produce rechazo y no deja referencias huérfanas. |
| RNF-17 | Ejecutar operaciones relacionadas como una unidad de trabajo atómica; impedir guardados parciales y duplicación por solicitudes repetidas. | Simular fallo durante registro de pedido con varias líneas o durante liberación: la base vuelve al estado anterior. Un doble envío de la misma operación no duplica líneas, unidades ni cantidades. |
| RNF-18 | Validar cambios de estado, conciliaciones, versiones aprobadas y reglas de negocio del SGC antes de guardar. | Se bloquean transferencia con diseño pendiente, lote sin primera pieza aceptada, despacho de unidad retenida y cierre de NC sin AC eficaz cuando esta es obligatoria. |
| RNF-19 | Conservar historial de registros y decisiones mediante identificador, actor, fecha, valor anterior/nuevo y motivo; restringir su modificación a procedimientos controlados. | Una actualización autorizada de requisitos o reapertura conserva la revisión anterior y no elimina evidencias ni altera silenciosamente indicadores históricos. |
| RNF-20 | Controlar ediciones simultáneas de un registro para evitar sobrescrituras no advertidas; garantizar que una unidad no se libera ni despacha dos veces. | Dos sesiones editan la misma versión: se acepta la primera actualización y la segunda recibe conflicto y debe recargar. Dos solicitudes para despachar la misma unidad solo permiten un despacho. |
| RNF-21 | Registrar fecha y hora coherentes y aplicar la zona horaria America/Bogota para fechas de negocio y filtros mensuales. | Un evento cercano al cambio de mes se incluye según fecha local de Colombia; las fechas de auditoría se conservan con referencia temporal inequívoca y su valor mostrado es consistente con el filtro. |

## 3.3.5. Rendimiento

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-22 | Responder a consultas paginadas y guardados ordinarios de los módulos en un máximo de 2 segundos para al menos el 95 % de las solicitudes de la prueba definida abajo. | Medir los tiempos HTTP de solicitudes válidas (sin transferencia de archivos grandes); el percentil 95 es ≤ 2 s por tipo de operación. |
| RNF-23 | Generar el dashboard mensual con los indicadores calculados en máximo 3 segundos para al menos el 95 % de las solicitudes de prueba. | Con la base de datos de referencia, medir el percentil 95 del panel y verificar que sus resultados corresponden a los registros, no a valores fijos. |
| RNF-24 | Atender 5 usuarios autenticados concurrentes, con las operaciones válidas del escenario de prueba, sin pérdida de registros ni errores internos del servidor. | Durante 5 minutos, ejecutar lectura y escritura en cuentas y registros permitidos; cero respuestas 5xx y cero pérdidas o duplicados. Los conflictos de edición controlados se prueban aparte y no cuentan como fallo interno. |
| RNF-25 | Paginar listados de registros: 25 filas por defecto, máximo 100 por página; filtrar en el servidor. | Una consulta con 300 registros devuelve 25 por defecto, permite avanzar páginas y no devuelve más de 100 filas por solicitud, manteniendo el total y filtros correctos. |

### Escenario de referencia

- Equipo de ensayo: entorno local de al menos 4 núcleos lógicos disponibles, 8 GB de RAM y almacenamiento SSD; registrar especificaciones efectivas, sistema operativo, versión de aplicación y configuración de prueba.
- Datos ficticios: 200 clientes, 1.000 pedidos, 2.000 lotes, 10.000 prendas únicas, 100.000 resultados de criterios de inspección, 500 NC y 100 AC. Mantener relaciones válidas y datos suficientes en el mes evaluado.
- Carga: cinco sesiones con roles empresariales, una operación por sesión cada 2 segundos aproximadamente durante 5 minutos; incluir lecturas de listados, filtros, guardados ordinarios y consultas de dashboard con al menos 30 muestras válidas por tipo medido.
- Medir duración de solicitud HTTP completa en la red local desde el cliente de prueba hasta recibir la respuesta, excluyendo el tiempo humano de diligenciamiento. Registrar herramientas, datos de ensayo, resultados y cantidad real de muestras. El percentil 95 se calcula ordenando los tiempos y tomando la posición techo de 0,95 × número de muestras.
- Estos límites no son acuerdos de nivel de servicio para Internet ni una afirmación de capacidad ya probada.

## 3.3.6. Copias de seguridad

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-26 | Crear una copia consistente de la base de datos y de los archivos de evidencia vinculados al finalizar cada jornada con cambios y antes de una actualización de estructura o restauración. Meta: no superar 24 horas desde el último respaldo válido mientras existan cambios sin respaldar (RPO). | Registrar fecha/hora, versión, ubicación, archivos incluidos y resultado. Si falla la copia, se mantiene el respaldo anterior y se avisa al ADMIN. La copia se obtiene mediante un método consistente, no copiando una base activa sin control. |
| RNF-27 | Mantener al menos las 7 copias diarias exitosas más recientes disponibles, si existen, fuera de Git y del directorio público, con acceso restringido a ADMIN; conservar al menos una en almacenamiento separado del disco principal. | Se verifica inventario y acceso a las copias, ausencia de exposición desde las rutas web comunes y conservación de una copia independiente; una copia inválida no reemplaza a una válida. |
| RNF-28 | Restaurar un respaldo en un entorno aislado y recuperar el servicio y sus relaciones dentro de 60 minutos (RTO), con verificación de integridad. | En la prueba de restauración del conjunto de referencia, recuperar cuentas, pedidos, lotes, inspecciones, defectos, NC, AC y evidencias; comparar conteos e identificadores y verificar inicio de sesión y consultas. Registrar tiempo y resultado. |
| RNF-29 | Verificar restauración como mínimo una vez al mes cuando el sistema esté en uso y antes de publicar una versión que modifique datos. Las restauraciones sobre la base operativa requieren autorización de Gerencia, respaldo previo y ejecución controlada. | Existe registro de ensayo mensual o previo a la publicación con identificador del respaldo, fecha, responsable, tiempos y resultado. Un ensayo fallido genera incidencia y no se declara recuperable. |

RPO: pérdida máxima de datos admitida, expresada como intervalo temporal. RTO: tiempo objetivo para restablecer el servicio desde el inicio de la recuperación. Los respaldos son responsabilidad técnica del ADMIN; la programación y ejecución concreta se definirá en etapas 4 y 5. Las restauraciones no se ejecutarán mediante una ruta pública de descarga o sustitución de archivos.

## 3.3.7. Mantenibilidad del código

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RNF-30 | Organizar el código por responsabilidad: rutas, lógica de negocio, modelos/acceso a datos, plantillas, recursos estáticos y pruebas. | El repositorio separa esas responsabilidades; las reglas de liberación y cierre se prueban sin depender de manipular HTML. |
| RNF-31 | Documentar instalación, configuración, inicialización, migración de base de datos, ejecución y pruebas; declarar dependencias reproducibles. | Una persona puede seguir README y guía en un entorno limpio, instalar dependencias declaradas, inicializar datos ficticios, iniciar la aplicación y ejecutar las pruebas sin usar secretos del autor. |
| RNF-32 | Mantener historial de cambios mediante Git, commits descriptivos, exclusión de archivos sensibles/generados y actualización de requisitos cuando cambie el comportamiento. | Cada cambio funcional de la versión candidata tiene commit y referencia a RF/RNF o incidencia; la revisión del repositorio no encuentra archivos de base privada ni configuración secreta versionados. |
| RNF-33 | Automatizar pruebas de las reglas críticas y mantener una cobertura mínima del 80 % de líneas de la lógica de negocio y autorización, medida sobre los módulos definidos para ese alcance. | La suite de pytest de la versión candidata completa sin fallos y el reporte de cobertura alcanza el umbral acordado; las pruebas obligatorias incluyen permisos, conciliaciones, liberación, cierre NC/AC e indicadores. La cobertura no sustituye la prueba de cada regla crítica. |

## 4. Trazabilidad y condiciones de aceptación

| Apartado | Identificadores | Método principal de verificación |
|---|---|---|
| 3.3.1 Seguridad | RNF-01–07 | Pruebas de autenticación, autorización, entradas y configuración |
| 3.3.2 Facilidad de uso | RNF-08–12 | Recorrido de interfaz, validación y teclado |
| 3.3.3 Adaptación | RNF-13–15 | Prueba de ventanas y navegadores |
| 3.3.4 Integridad | RNF-16–21 | Pruebas de restricciones, transacciones y concurrencia |
| 3.3.5 Rendimiento | RNF-22–25 | Medición reproducible con datos de referencia |
| 3.3.6 Respaldo | RNF-26–29 | Creación, verificación y restauración de copias |
| 3.3.7 Mantenibilidad | RNF-30–33 | Revisión técnica, instalación limpia y pruebas automatizadas |

**Total:** 33 requisitos no funcionales propuestos. Se verificarán en las etapas de diseño, desarrollo y pruebas. Si alguna meta requiere un ajuste después de ensayar, registrar la evidencia, justificación y cambio aprobado; no reducirla retroactivamente para declarar una prueba exitosa.

## 5. Estado del roadmap y control de cambios

- [ ] 3.3.1. Seguridad de acceso.
- [ ] 3.3.2. Facilidad de uso.
- [ ] 3.3.3. Diseño adaptable a diferentes pantallas.
- [ ] 3.3.4. Integridad de la información.
- [ ] 3.3.5. Rendimiento.
- [ ] 3.3.6. Copias de seguridad.
- [ ] 3.3.7. Mantenibilidad del código.

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 19/11/2026 | 33 requisitos no funcionales y criterios medibles de aceptación | En revisión |

**Siguiente apartado:** 3.4 — Análisis del funcionamiento.

# DOC-QP-002 — Organización inicial del proyecto

| Campo | Información |
|---|---|
| Proyecto | QualityPrint — Sistema de Gestión de Calidad (SGC) |
| Código | DOC-QP-002 |
| Etapa | 1. Inicio y organización del proyecto |
| Apartado de la ruta | 1.2. Organización inicial |
| Versión | 1.2 |
| Fecha de elaboración | 10 de noviembre de 2026 |
| Estado | Aprobado para el proyecto académico |
| Naturaleza | Proyecto académico y de portafolio profesional |
| Empresa objeto de estudio | QualityPrint (empresa ficticia) |

## Propósito del documento

Establecer las herramientas de trabajo, las tecnologías de desarrollo, las etapas y los entregables del proyecto QualityPrint-SGC. Complementa **DOC-QP-001 — Ficha de definición del proyecto**, sin reemplazarlo. Se utiliza para tomar decisiones técnicas coherentes, controlar el alcance y preparar el repositorio de GitHub.

**Contexto del proyecto:** QualityPrint simula una pequeña empresa de estampado textil DTF (*Direct to Film*), con hasta cinco trabajadores y una impresora DTF. Se desarrollará una aplicación web para centralizar pedidos, registros de producción, inspecciones, no conformidades e indicadores. Todos los registros utilizados en el proyecto serán ficticios.

---

## 1.2.1. Definir las herramientas que utilizaremos

### 1.2.1.1. Herramientas principales

| Herramienta | Uso en el proyecto | Etapa de uso | Decisión |
|---|---|---|---|
| GitHub | Alojar el repositorio, visualizar documentación y presentar el código en el portafolio | Desde la etapa 1 | Obligatoria |
| Git | Registrar cambios del código y sincronizar el proyecto local con GitHub | Desde la etapa 5 | Obligatoria |
| Visual Studio Code | Editar archivos Markdown, Python, HTML, CSS y JavaScript | Desde la etapa 1 (opcional); esencial desde la 5 | Obligatoria para desarrollo local |
| Navegador web y DevTools | Comprobar pantallas, formularios, navegación y errores | Etapas 6–8 | Obligatoria |
| diagrams.net (draw.io) | Elaborar mapa de procesos, diagramas de flujo, casos de uso y arquitectura | Etapas 2–4 | Recomendada |
| Excel, Google Sheets o Calc | Preparar matrices de riesgos, indicadores y datos de prueba | Etapas 2–3 y 7 | Recomendada; elegir una |
| Figma | Crear prototipos de interfaz antes de programar | Etapa 4 | Opcional |

### 1.2.1.2. Herramientas de soporte y organización

- **Markdown (`.md`):** formato principal para documentos técnicos versionables en GitHub.
- **GitHub Issues:** opcional para registrar mejoras y errores cuando comience el desarrollo.
- **`.gitignore`:** excluir archivos temporales, entornos virtuales, secretos y bases de datos locales.
- **`README.md`:** portada del proyecto, enlaces a documentos e instrucciones de ejecución.
- **`ROADMAP_QUALITYPRINT.md`:** lista general de actividades por etapas y subetapas.

### 1.2.1.3. Orden de adopción de herramientas

1. **Etapa 1:** cuenta de GitHub y archivos Markdown; el repositorio se creará en el punto 1.3.
2. **Etapas 2–4:** diagrams.net y una hoja de cálculo para documentación y análisis; Figma si es útil.
3. **Etapa 5:** instalar Python, Git y Visual Studio Code; configurar el entorno local.
4. **Etapas 6–8:** navegador/DevTools, herramientas de prueba y despliegue compatibles con Flask.

**Criterio de elección:** priorizar herramientas gratuitas o con planes gratuitos suficientes para el proyecto; evitar dependencias y gastos innecesarios.

---

## 1.2.2. Definir las tecnologías de desarrollo

### 1.2.2.1. Tecnologías de la primera versión (MVP)

| Capa | Tecnología | Función |
|---|---|---|
| Lenguaje principal | Python | Implementar las reglas de negocio y el backend |
| Framework web | Flask | Recibir solicitudes, gestionar rutas y generar respuestas web |
| Plantillas HTML | Jinja2 | Generar vistas HTML desde Flask |
| Estructura visual | HTML5 | Definir formularios, tablas y páginas |
| Presentación visual | CSS3, Bootstrap opcional | Estilos y diseño adaptable |
| Interactividad | JavaScript | Validaciones y comportamiento de la interfaz |
| Base de datos | SQLite | Guardar datos del prototipo local |
| Acceso a datos | SQLAlchemy | Definir modelos y consultar la base de datos |
| Entorno aislado | `venv` y `pip` | Instalar y controlar dependencias de Python |
| Pruebas | `pytest` | Comprobar reglas de negocio y rutas importantes |
| Control de versiones | Git y GitHub | Historial, respaldo y publicación del código |

### 1.2.2.2. Arquitectura prevista

El MVP se desarrollará como **aplicación web monolítica con Flask**, utilizando plantillas renderizadas en el servidor. Esta arquitectura es adecuada para aprender, evita separar prematuramente frontend y backend en repositorios diferentes y permite evolucionar posteriormente.

```text
Usuario en el navegador
        ↓
Interfaz: HTML + CSS + JavaScript
        ↓
Servidor: Python + Flask + Jinja2
        ↓
Modelos de datos: SQLAlchemy
        ↓
Base de datos: SQLite
```

### 1.2.2.3. Módulos iniciales del software

1. **Clientes y pedidos:** registrar clientes ficticios, detalles del pedido y estado.
2. **Producción DTF:** asociar lotes a pedidos y guardar datos de producción.
3. **Inspecciones:** registrar criterios y resultados por pedido o lote.
4. **No conformidades:** documentar defectos, responsables, seguimiento y estado.
5. **Dashboard:** visualizar conteos e indicadores calculados con registros almacenados.

El sistema de usuarios y permisos se especificará en la etapa de requisitos; su alcance de implementación dependerá de los criterios de seguridad definidos para el MVP. **La primera versión no incluye** facturación, integración física con la impresora, aplicación móvil nativa ni certificación ISO.

### 1.2.2.4. Criterios técnicos y posibles mejoras

- Mantener código organizado en rutas, modelos, plantillas y archivos estáticos.
- Guardar dependencias en `requirements.txt` y excluir secretos del repositorio.
- Usar exclusivamente datos ficticios de clientes, trabajadores y pedidos.
- No definir temperaturas, tiempos o presiones universales para DTF: los parámetros deberán corresponder a insumos/equipos concretos y a validaciones de proceso.
- Evaluar PostgreSQL y un servicio de alojamiento compatible con Flask al preparar una demostración pública; **GitHub Pages no ejecuta servidores Flask**.

---

## 1.2.3. Definir las etapas del proyecto

### 1.2.3.1. Ruta de trabajo

| Etapa | Nombre | Actividades principales | Resultado esperado |
|---|---|---|---|
| 1 | Inicio y organización | Definir el proyecto, herramientas y repositorio | Base documental y repositorio organizado |
| 2 | Empresa ficticia y SGC | Identidad, mapa de procesos, riesgos, controles DTF y formatos | Documentación básica del SGC |
| 3 | Análisis de requisitos | Usuarios, requisitos, reglas, casos de uso y prioridades | Especificación del software |
| 4 | Diseño del software | Arquitectura, base de datos, prototipos y diagramas | Diseño técnico verificable |
| 5 | Entorno de desarrollo | Instalar herramientas, iniciar Flask y conectar Git | Proyecto ejecutable localmente |
| 6 | Desarrollo del MVP | Implementar módulos e integración | Aplicación web funcional |
| 7 | Pruebas y correcciones | Pruebas funcionales, datos, seguridad básica y errores | Evidencia de funcionamiento |
| 8 | Publicación y portafolio | README, instalación, capturas, release y demo si es viable | Proyecto presentable públicamente |
| 9 | Evolución | Mejoras funcionales y técnicas | Nuevas versiones documentadas |

### 1.2.3.2. Orden y dependencias

- **GitHub comienza en la etapa 1**, no al terminar el software. Allí se almacenarán progresivamente documentos y código.
- Las **etapas 2 y 3** definen los procesos y requisitos necesarios para evitar programar funciones sin propósito.
- Las **etapas 4 y 5** diseñan e inicializan la solución técnica.
- Las **etapas 6 y 7** se ejecutan de forma iterativa: se prueba cada módulo mientras se desarrolla.
- La **etapa 8** muestra la primera versión usable en el portafolio; la 9 es posterior y opcional.

### 1.2.3.3. Método de seguimiento

1. Seleccionar una actividad pendiente del roadmap.
2. Elaborar el documento, diagrama, código o prueba correspondiente.
3. Revisar el resultado contra su criterio de aceptación.
4. Guardar la evidencia en la carpeta correcta y subir el cambio a GitHub cuando exista el repositorio.
5. Marcar `[x]` únicamente después de completar y verificar; conservar `[ ]` mientras sea borrador.
6. Si cambia el alcance, actualizar DOC-QP-001, este documento y la hoja de ruta cuando corresponda.

---

## 1.2.4. Establecer los entregables de cada etapa

### 1.2.4.1. Matriz de entregables

| Etapa | Entregables | Ubicación sugerida | Criterio de aceptación |
|---|---|---|---|
| 1 | DOC-QP-001, DOC-QP-002, README, roadmap, checklist y repositorio | `docs/01_proyecto/` y raíz | Archivos organizados, aprobados y accesibles en GitHub |
| 2 | Caracterización empresarial, política/objetivos, mapa, riesgos, procedimientos y formatos DTF | `docs/02_sgc/` | Coherencia entre proceso, controles y registros |
| 3 | Requisitos funcionales/no funcionales, roles, casos de uso y reglas | `docs/03_requisitos/` | Requisitos claros, priorizados y verificables |
| 4 | Diagrama de arquitectura, DER, diccionario de datos y prototipos | `docs/04_diseno/` | Diseño suficiente para construir los módulos |
| 5 | Proyecto Flask inicial, `requirements.txt`, `.gitignore` y guía de arranque | `app/`, raíz y `docs/05_entorno/` | Aplicación inicia en un equipo local |
| 6 | Código fuente y módulos de pedidos, producción, inspecciones, no conformidades y dashboard | `app/` | Flujo completo funciona con datos de ejemplo |
| 7 | Casos de prueba, resultados, incidencias y correcciones | `tests/` y `docs/07_pruebas/` | Pruebas esenciales ejecutadas y problemas críticos resueltos |
| 8 | README final, capturas, guía de uso, versión publicada y demo si procede | Raíz, `docs/08_portafolio/` y GitHub Releases | Otra persona puede entender y ejecutar el proyecto |
| 9 | Documentación de mejoras, nuevas funciones, pruebas y versiones | `docs/09_mejoras/` | Cada mejora está documentada y probada |

### 1.2.4.2. Entregables mínimos del MVP

Para considerar lista la primera versión del software, deberá existir evidencia de que:

- [ ] Un pedido puede registrarse y relacionarse con un lote de producción.
- [ ] Una inspección puede registrarse sobre un pedido o lote.
- [ ] Un defecto puede generar una no conformidad rastreable.
- [ ] El dashboard muestra indicadores obtenidos de los datos almacenados.
- [ ] Los formularios validan la información obligatoria.
- [ ] Las pruebas esenciales se ejecutaron y documentaron.
- [ ] Un tercero puede instalar el sistema siguiendo el README.

Estas casillas **no pertenecen al cierre de la etapa 1.2**: sirven como criterios futuros para las etapas 6–8.

### 1.2.4.3. Criterios para cerrar este documento

- [x] **1.2.1:** se revisó y aprobó la lista de herramientas.
- [x] **1.2.2:** se revisó y aprobó la selección tecnológica y el MVP.
- [x] **1.2.3:** se revisaron y aprobaron las nueve etapas.
- [x] **1.2.4:** se revisaron y aprobaron los entregables y sus criterios.

**Estado actual:** los cuatro apartados se consideran aprobados para el proyecto académico y están publicados en el repositorio.

---

## Organización de documentos en GitHub

```text
QualityPrint-SGC/
├── README.md
├── ROADMAP_QUALITYPRINT.md
├── ETAPA_1_CHECKLIST.md
├── .gitignore
└── docs/
    └── 01_proyecto/
        ├── DOC-QP-001_ficha_del_proyecto.md
        └── DOC-QP-002_organizacion_inicial_del_proyecto.md
```

Se guardará **un documento por tema principal**. Así, DOC-QP-001 contiene la definición del proyecto y DOC-QP-002 contiene exclusivamente la organización inicial y sus subpuntos 1.2.1–1.2.4. Los documentos de etapas futuras tendrán sus propios códigos y archivos.

## Control de versiones

| Versión | Fecha | Cambio | Estado |
|---|---|---|---|
| 1.0 | 10/11/2026 | Borrador inicial de herramientas y planificación | Sustituido |
| 1.1 | 10/11/2026 | Desarrollo separado y numerado de 1.2.1 a 1.2.4, con entregables y criterios | Revisado |
| 1.2 | 10/11/2026 | Aprobación de la sección 1.2 y verificación en GitHub | Aprobado |

**Actividad posterior:** **1.3 — Preparación de GitHub**: repositorio creado, público y documentación inicial organizada y publicada. Próximo paso: **etapa 2**, documentación de la empresa y del SGC.

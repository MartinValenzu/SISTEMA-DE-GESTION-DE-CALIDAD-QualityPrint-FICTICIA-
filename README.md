# QualityPrint — Sistema de Gestión de Calidad (SGC)

**Proyecto académico y de portafolio. Empresa ficticia de estampados textiles DTF (Direct to Film).**

## ¿Qué es QualityPrint?
QualityPrint simula una pequeña empresa de personalización textil que cuenta con **una impresora DTF** y **hasta cinco trabajadores**. El proyecto combina el diseño documental de un Sistema de Gestión de Calidad con el desarrollo progresivo de una **aplicación web para gestionar pedidos, registros de producción, inspecciones y no conformidades**.

> **Estado actual:** Etapa 1 completada (18/18); Etapa 2 completada (56/56); Etapa 3 completada (28/28); Etapa 4 en elaboración — apartado 4.1 aprobado (DOC-QP-014), apartado 4.2 en revisión (DOC-QP-015). El software todavía **no está desarrollado**. La empresa y sus datos son ficticios; no se afirma certificación ISO.

## Objetivo
Diseñar, desarrollar y evaluar un prototipo web capaz de centralizar registros y facilitar la trazabilidad de calidad de pedidos de estampado DTF, con un panel básico de indicadores.

## Documentación inicial
| Documento | Descripción |
|---|---|
| [DOC-QP-001 — Ficha del proyecto](docs/01_proyecto/DOC-QP-001_ficha_del_proyecto.md) | Problema, solución, objetivos, alcance y restricciones |
| [DOC-QP-002 — Organización inicial](docs/01_proyecto/DOC-QP-002_organizacion_inicial_del_proyecto.md) | Herramientas, tecnologías, etapas y entregables |
| [DOC-QP-003 — Información general de la empresa](docs/02_sgc/DOC-QP-003_informacion_general_empresa.md) | Caracterización, clientes, actividad, organigrama y cargos (aprobado) |
| [DOC-QP-004 — Direccionamiento estratégico](docs/02_sgc/DOC-QP-004_direccionamiento_estrategico.md) | Misión, visión, política, objetivos e indicadores (aprobado) |
| [DOC-QP-005 — Contexto de la organización](docs/02_sgc/DOC-QP-005_contexto_de_la_organizacion.md) | Factores internos y externos, interesados, necesidades y alcance del SGC (aprobado) |
| [DOC-QP-006 — Procesos y mapa de procesos](docs/02_sgc/DOC-QP-006_procesos_y_mapa_de_procesos.md) | Procesos estratégicos, operativos y de apoyo; mapa, entradas, salidas y responsables (aprobado) |
| [DOC-QP-007 — Proceso de producción DTF](docs/02_sgc/DOC-QP-007_proceso_de_produccion_DTF.md) | Diez etapas de producción, controles, registros y seguridad (aprobado) |
| [DOC-QP-008 — Gestión de riesgos y oportunidades](docs/02_sgc/DOC-QP-008_gestion_de_riesgos_y_oportunidades.md) | Matriz simulada de riesgos, causas, controles, responsables y oportunidades (aprobado) |
| [DOC-QP-009 — Gestión documental](docs/02_sgc/DOC-QP-009_gestion_documental.md) | Codificación, versiones, responsables y procedimiento (aprobado) |
| [LM-QP-001 — Listado maestro de documentos](docs/02_sgc/LM-QP-001_listado_maestro_de_documentos.md) | Registro maestro de documentos, versiones, estados y enlaces (aprobado) |
| [PR-QP-001 — Procedimiento de recepción de pedidos](docs/02_sgc/procedimientos/PR-QP-001_recepcion_de_pedidos.md) | Revisión y confirmación de pedidos antes de la producción (aprobado) |
| [PR-QP-002 — Procedimiento de producción DTF](docs/02_sgc/procedimientos/PR-QP-002_produccion_dtf.md) | Materiales, parámetros, primera pieza, producción y cierre de lote (aprobado) |
| [PR-QP-003 — Procedimiento de inspección de calidad](docs/02_sgc/procedimientos/PR-QP-003_inspeccion_de_calidad.md) | Criterios, defectos, inspección individual y liberación (aprobado) |
| [PR-QP-004 — Procedimiento de gestión de no conformidades](docs/02_sgc/procedimientos/PR-QP-004_gestion_de_no_conformidades.md) | Contención, disposición, causa, acción correctiva y cierre (aprobado) |
| [F-QP-001 — Formato de recepción de pedidos](docs/02_sgc/formatos/F-QP-001_recepcion_de_pedidos.md) | Plantilla de pedido, requisitos, aprobaciones y cambios (aprobado) |
| [F-QP-002 — Inspección de materiales DTF](docs/02_sgc/formatos/F-QP-002_inspeccion_de_materiales.md) | Plantilla de verificación, retención y liberación de materiales (aprobado) |
| [F-QP-003 — Registro de producción DTF](docs/02_sgc/formatos/F-QP-003_registro_de_produccion_dtf.md) | Plantilla de parámetros, primera pieza, incidencias y cierre de lote (aprobado) |
| [F-QP-004 — Formato de inspección final](docs/02_sgc/formatos/F-QP-004_inspeccion_final.md) | Inspección individual, defectos, reinspección y liberación de prendas (aprobado) |
| [F-QP-005 — Registro de no conformidades](docs/02_sgc/formatos/F-QP-005_registro_de_no_conformidades.md) | Identificación, contención, disposición, verificación y cierre de NC (aprobado) |
| [F-QP-006 — Registro de acciones correctivas](docs/02_sgc/formatos/F-QP-006_registro_de_acciones_correctivas.md) | Análisis de causa, plan, ejecución, eficacia y cierre de AC (aprobado) |
| [DOC-QP-010 — Usuarios, roles y permisos](docs/03_requisitos/DOC-QP-010_usuarios_roles_y_permisos.md) | Perfiles, matriz de permisos y reglas de autorización (aprobado) |
| [DOC-QP-011 — Requisitos funcionales](docs/03_requisitos/DOC-QP-011_requisitos_funcionales.md) | 48 requisitos y criterios de aceptación del software (aprobado) |
| [DOC-QP-012 — Requisitos no funcionales](docs/03_requisitos/DOC-QP-012_requisitos_no_funcionales.md) | 33 requisitos de seguridad, usabilidad, integridad, rendimiento, respaldo y mantenibilidad (aprobado) |
| [DOC-QP-013 — Análisis del funcionamiento](docs/03_requisitos/DOC-QP-013_analisis_del_funcionamiento.md) | Flujos, 18 casos de uso, 8 escenarios, 23 reglas y prioridades (aprobado) |
| [DOC-QP-014 — Diseño de arquitectura](docs/04_diseno/DOC-QP-014_diseno_de_arquitectura.md) | Arquitectura modular, comunicación HTTP, persistencia y diagramas (aprobado) |
| [DOC-QP-015 — Diseño de base de datos](docs/04_diseno/DOC-QP-015_diseno_de_base_de_datos.md) | Diccionario de 62 tablas, claves y MER por dominios (en revisión) |
| [ROADMAP_QUALITYPRINT.md](ROADMAP_QUALITYPRINT.md) | Hoja de ruta detallada con casillas de avance |
| [ETAPA_1_CHECKLIST.md](ETAPA_1_CHECKLIST.md) | Evidencias de la etapa inicial |
| [docs/README.md](docs/README.md) | Índice de la documentación |

## Funcionalidades previstas del MVP
- Clientes y pedidos.
- Registro de lotes de producción DTF.
- Inspecciones de calidad.
- Registro y seguimiento de no conformidades.
- Dashboard con indicadores derivados de los registros.

Estas funcionalidades están **planificadas**, no implementadas todavía.

## Tecnologías previstas
- **Backend:** Python, Flask y Jinja2.
- **Frontend:** HTML, CSS y JavaScript (Bootstrap opcional).
- **Base de datos inicial:** SQLite con SQLAlchemy.
- **Pruebas:** pytest.
- **Organización:** Git, GitHub y documentación Markdown.

## Organización del repositorio
```text
README.md
ROADMAP_QUALITYPRINT.md
ETAPA_1_CHECKLIST.md
.gitignore
docs/
  README.md
  01_proyecto/
    DOC-QP-001_ficha_del_proyecto.md
    DOC-QP-002_organizacion_inicial_del_proyecto.md
  02_sgc/
    DOC-QP-003_informacion_general_empresa.md
    DOC-QP-004_direccionamiento_estrategico.md
    DOC-QP-005_contexto_de_la_organizacion.md
    DOC-QP-006_procesos_y_mapa_de_procesos.md
    DOC-QP-007_proceso_de_produccion_DTF.md
    DOC-QP-008_gestion_de_riesgos_y_oportunidades.md
    DOC-QP-009_gestion_documental.md
    LM-QP-001_listado_maestro_de_documentos.md
    procedimientos/
      PR-QP-001_recepcion_de_pedidos.md
      PR-QP-002_produccion_dtf.md
      PR-QP-003_inspeccion_de_calidad.md
      PR-QP-004_gestion_de_no_conformidades.md
    formatos/
      F-QP-001_recepcion_de_pedidos.md
      F-QP-002_inspeccion_de_materiales.md
      F-QP-003_registro_de_produccion_dtf.md
      F-QP-004_inspeccion_final.md
      F-QP-005_registro_de_no_conformidades.md
      F-QP-006_registro_de_acciones_correctivas.md
  03_requisitos/
    README.md
    DOC-QP-010_usuarios_roles_y_permisos.md
    DOC-QP-011_requisitos_funcionales.md
    DOC-QP-012_requisitos_no_funcionales.md
    DOC-QP-013_analisis_del_funcionamiento.md
  04_diseno/
    README.md
    DOC-QP-014_diseno_de_arquitectura.md
    DOC-QP-015_diseno_de_base_de_datos.md
```

Las carpetas de las siguientes etapas están preparadas; sus documentos se elaborarán progresivamente.

## Etapas
1. Inicio y organización — **completada**.
2. Documentación de la empresa y del SGC — **completada**.
3. Requisitos del software — **completada**.
4. Arquitectura, diseño y base de datos — **en elaboración**.
5. Entorno de desarrollo.
6. Desarrollo del MVP.
7. Pruebas.
8. Publicación y portafolio.
9. Mejoras.

## Cómo ejecutar la aplicación
**Aún no disponible:** el entorno y las instrucciones de ejecución se agregarán cuando comience la etapa 5. En este momento este repositorio contiene la documentación base del proyecto.

## Alcance y aviso
Todos los casos, datos y procesos empresariales se presentan como **simulaciones educativas**. Se seguirán buenas prácticas de gestión de calidad, sin atribuir auditorías, certificaciones ni resultados de producción reales.

## Control de avance
Consulta [ROADMAP_QUALITYPRINT.md](ROADMAP_QUALITYPRINT.md) antes de marcar una actividad como terminada. Cada casilla debe corresponder a un entregable comprobable.

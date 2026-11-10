# QualityPrint — Sistema de Gestión de Calidad (SGC)

**Proyecto académico y de portafolio. Empresa ficticia de estampados textiles DTF (Direct to Film).**

## ¿Qué es QualityPrint?
QualityPrint simula una pequeña empresa de personalización textil que cuenta con **una impresora DTF** y **hasta cinco trabajadores**. El proyecto combina el diseño documental de un Sistema de Gestión de Calidad con el desarrollo progresivo de una **aplicación web para gestionar pedidos, registros de producción, inspecciones y no conformidades**.

> **Estado actual:** Etapa 1 completada; Etapas 2.1 y 2.2 aprobadas; Etapa 2.3 en revisión (DOC-QP-005). El software todavía **no está desarrollado**. La empresa y sus datos son ficticios; no se afirma certificación ISO.

## Objetivo
Diseñar, desarrollar y evaluar un prototipo web capaz de centralizar registros y facilitar la trazabilidad de calidad de pedidos de estampado DTF, con un panel básico de indicadores.

## Documentación inicial
| Documento | Descripción |
|---|---|
| [DOC-QP-001 — Ficha del proyecto](docs/01_proyecto/DOC-QP-001_ficha_del_proyecto.md) | Problema, solución, objetivos, alcance y restricciones |
| [DOC-QP-002 — Organización inicial](docs/01_proyecto/DOC-QP-002_organizacion_inicial_del_proyecto.md) | Herramientas, tecnologías, etapas y entregables |
| [DOC-QP-003 — Información general de la empresa](docs/02_sgc/DOC-QP-003_informacion_general_empresa.md) | Caracterización, clientes, actividad, organigrama y cargos (aprobado) |
| [DOC-QP-004 — Direccionamiento estratégico](docs/02_sgc/DOC-QP-004_direccionamiento_estrategico.md) | Misión, visión, política, objetivos e indicadores (aprobado) |
| [DOC-QP-005 — Contexto de la organización](docs/02_sgc/DOC-QP-005_contexto_de_la_organizacion.md) | Factores internos y externos, interesados, necesidades y alcance del SGC (en revisión) |
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
  03_requisitos/
  04_diseno/
```

Las carpetas de las siguientes etapas están preparadas; sus documentos se elaborarán progresivamente.

## Etapas
1. Inicio y organización — **completada**.
2. Documentación de la empresa y del SGC — **en elaboración**.
3. Requisitos del software.
4. Arquitectura, diseño y base de datos.
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

# DOC-QP-001 — Ficha de definición del proyecto

| Campo | Información |
|---|---|
| Proyecto | QualityPrint — Sistema de Gestión de Calidad |
| Código | DOC-QP-001 |
| Versión | 0.1 |
| Fecha de elaboración | 10 de noviembre de 2026 |
| Estado | Borrador para revisión |
| Naturaleza | Proyecto de aprendizaje y portafolio de desarrollo de software |
| Organización de referencia | QualityPrint (empresa ficticia) |
| Actividad | Estampados textiles mediante tecnología DTF (Direct to Film) |

## 1. Descripción de la empresa ficticia

QualityPrint es una empresa ficticia dedicada a la personalización de prendas textiles utilizando la tecnología de impresión DTF. Para el caso de estudio se considera una empresa pequeña, con un equipo de trabajo de hasta cinco personas y una impresora DTF. Atiende pedidos de camisetas, sudaderas y uniformes personalizados. La producción se realiza principalmente bajo pedido.

**Supuestos iniciales:** la empresa opera con una sola unidad de impresión DTF; dispone de prensa térmica y los elementos auxiliares necesarios; los cargos y funciones concretos se definirán en la documentación organizacional. Estos supuestos no describen una empresa real.

## 2. Planteamiento del problema

En el escenario simulado, los pedidos, parámetros de producción, inspecciones y defectos se registran en medios dispersos o de forma manual. Esto dificulta relacionar un producto no conforme con su pedido y lote, consultar el historial de calidad, hacer seguimiento a las acciones correctivas y calcular indicadores confiables.

**Problema central:** ausencia de un medio centralizado y trazable para registrar y controlar los aspectos esenciales de calidad en los pedidos de estampado DTF de QualityPrint.

## 3. Justificación

Se propone desarrollar una aplicación web que permita organizar los registros de calidad, mejorar la trazabilidad desde el pedido hasta la inspección final y facilitar el análisis de defectos. El proyecto integra análisis de requisitos, modelado de bases de datos, desarrollo web, pruebas y documentación técnica. Su carácter ficticio permite utilizar datos de demostración y construir un portafolio reproducible sin manejar datos reales de clientes.

## 4. Objetivo general

Diseñar y desarrollar un prototipo funcional de aplicación web para apoyar el control y seguimiento de la calidad en los procesos de estampado DTF de la empresa ficticia QualityPrint, mediante la gestión centralizada de pedidos, producción, inspecciones y no conformidades.

## 5. Objetivos específicos

1. Documentar los procesos operativos principales de QualityPrint y los puntos de control de calidad.
2. Identificar los usuarios, requisitos y reglas de negocio del sistema.
3. Diseñar el modelo de datos y las interfaces principales de la aplicación.
4. Implementar módulos para registrar pedidos, lotes de producción, inspecciones y no conformidades.
5. Incorporar un panel básico con indicadores calculados a partir de los registros almacenados.
6. Verificar el funcionamiento mediante pruebas con datos ficticios.
7. Publicar el código fuente, la documentación y evidencias de ejecución en un repositorio de GitHub.

## 6. Alcance de la versión inicial (MVP)

**Incluye:**
- Registro, consulta y actualización controlada de clientes y pedidos de prueba.
- Registro de lotes de producción DTF vinculados a pedidos.
- Registro de inspecciones y sus criterios de aceptación.
- Registro y seguimiento básico de productos no conformes y acciones asociadas.
- Panel de indicadores: pedidos, inspecciones, defectos y no conformidades.
- Almacenamiento local en base de datos y validación de formularios.
- Documentación de instalación, arquitectura y pruebas.

**No incluye en la primera versión:**
- Facturación electrónica, contabilidad o pasarelas de pago.
- Integración automática con impresoras o maquinaria DTF.
- Gestión avanzada de inventario, compras o proveedores.
- Certificación ISO o afirmaciones de cumplimiento certificado.
- Aplicación móvil nativa ni operación de múltiples sedes.

## 7. Usuarios previstos

| Rol de negocio | Necesidad principal |
|---|---|
| Dirección/gerencia | Consultar resultados e indicadores |
| Comercial y diseño | Registrar y revisar pedidos y diseños aprobados |
| Operación DTF | Registrar lotes y parámetros de producción |
| Responsable de calidad | Registrar inspecciones, defectos y seguimiento |

La asignación definitiva de permisos se diseñará en la etapa de requisitos. Una persona podrá desempeñar más de una función por tratarse de una empresa pequeña.

## 8. Tecnologías preliminares

- **Lenguaje y backend:** Python y Flask.
- **Interfaz web:** HTML, CSS, JavaScript y, si resulta conveniente, Bootstrap.
- **Persistencia:** SQLite con SQLAlchemy para la primera versión.
- **Entorno de desarrollo:** Visual Studio Code y Git.
- **Repositorio y portafolio:** GitHub.
- **Diagramas:** diagrams.net; Figma será opcional para prototipos.

Las decisiones técnicas podrán ajustarse si aparecen requisitos que lo justifiquen.

## 9. Entregables del proyecto

1. Documentación básica de la empresa ficticia y del Sistema de Gestión de Calidad (SGC).
2. Especificación de requisitos y reglas de negocio.
3. Diagramas de procesos, arquitectura y modelo entidad-relación.
4. Código fuente de la aplicación web y esquema de base de datos.
5. Pruebas realizadas con datos de demostración.
6. README, instrucciones de instalación y capturas de pantalla.
7. Versión inicial publicada en el repositorio de GitHub y, si es viable, una demostración web.

## 10. Restricciones y criterios de éxito

**Restricciones:** proyecto individual de aprendizaje; herramientas de preferencia gratuitas; información de una empresa y clientes ficticios; desarrollo incremental por etapas. Los valores técnicos de curado, transferencia, adherencia y demás controles DTF deben definirse a partir de información del fabricante y pruebas de validación, no asumirse como valores universales.

**Criterios iniciales de éxito:**
- Un pedido puede registrarse y vincularse a un lote de producción.
- Un lote puede asociarse a una inspección con resultados guardados.
- Una inspección no conforme puede generar y mostrar un registro de no conformidad.
- Los indicadores reflejan correctamente los datos de prueba registrados.
- El sistema puede instalarse siguiendo el README y supera sus pruebas principales.

## 11. Límites del ejercicio académico

QualityPrint, su personal, pedidos y métricas son ficticios. El software será un prototipo demostrativo, no un sistema certificado ni una evaluación real de conformidad con ISO 9001. Cualquier referencia normativa se verificará durante la documentación del SGC.

## 12. Control de cambios

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 2026-11-10 | Primera propuesta de ficha del proyecto | Pendiente de revisión |

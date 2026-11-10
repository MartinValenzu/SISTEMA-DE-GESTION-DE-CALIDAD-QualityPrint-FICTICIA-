# DOC-QP-001 — Ficha de definición del proyecto

| Campo | Información |
|---|---|
| Nombre del proyecto | QualityPrint — Sistema de Gestión de Calidad |
| Código | DOC-QP-001 |
| Versión del documento | 1.1 |
| Fecha de actualización | 10 de noviembre de 2026 |
| Estado | **En revisión: puntos 1.1.5, 1.1.6 y 1.1.7 pendientes de validación** |
| Naturaleza | Proyecto académico y de portafolio |
| Organización de referencia | QualityPrint (empresa ficticia) |
| Sector | Estampados textiles mediante tecnología DTF (Direct to Film) |

> **Nota metodológica:** la situación de QualityPrint es un escenario simulado. No se ha efectuado un diagnóstico real a una empresa. Las necesidades descritas se plantean como supuestos de diseño para el desarrollo del software.

## 1. Definición del proyecto

### 1.1.1. Nombre del proyecto

**QualityPrint — Sistema de Gestión de Calidad para una empresa de estampados textiles DTF.**

### 1.1.2. Tipo de sistema

Aplicación web de apoyo a un Sistema de Gestión de Calidad (SGC), orientada a registrar, consultar y dar seguimiento a la información de calidad de los procesos de estampado textil DTF.

### 1.1.3. Descripción de la empresa ficticia

QualityPrint es una pequeña empresa ficticia que personaliza camisetas, sudaderas y uniformes mediante impresión DTF. Trabaja principalmente bajo pedido y atiende clientes particulares y empresariales.

### 1.1.4. Tamaño y características de la empresa

Se proyectan **hasta cinco trabajadores** y **una impresora DTF**, además de los equipos auxiliares necesarios, como una prensa térmica. Los roles propuestos son dirección, atención comercial y diseño, operación DTF, control de calidad y apoyo administrativo. Una persona puede desempeñar más de una función.

### 1.1.5. Identificación del problema que resolverá el software

**Situación problemática (simulada):** en QualityPrint, la información relacionada con los pedidos, diseños aprobados, lotes de producción, parámetros de operación, inspecciones y defectos se conserva en registros manuales o archivos separados. Esta situación dificulta consultar oportunamente el estado de calidad de un pedido y reconstruir qué ocurrió durante su producción.

**Causas supuestas:**

- Ausencia de una herramienta única para reunir los registros de pedidos, producción e inspección.
- Falta de un identificador común que relacione pedido, lote, inspección y defecto.
- Seguimiento manual de las no conformidades y de las acciones tomadas.
- Cálculo no sistemático de indicadores de calidad.

**Consecuencias previstas:**

- Mayor tiempo para localizar información y verificar un pedido.
- Riesgo de pérdida, duplicidad o inconsistencia de los registros.
- Dificultad para identificar defectos recurrentes y hacer seguimiento a las correcciones.
- Limitaciones para tomar decisiones basadas en datos registrados.

**Problema central:** QualityPrint no dispone, dentro de este escenario ficticio, de un sistema centralizado que permita registrar y consultar con trazabilidad la información esencial de calidad de sus pedidos de estampado DTF.

**Pregunta orientadora:** ¿Cómo desarrollar una aplicación web que permita centralizar los registros de producción e inspección y facilitar el seguimiento de las no conformidades en una pequeña empresa ficticia de estampados DTF?

### 1.1.6. Definición de la solución propuesta

Se propone diseñar y desarrollar **QualityPrint**, una aplicación web que centralice los datos de los pedidos, los lotes de producción DTF, las inspecciones y las no conformidades. Cada registro estará asociado a los datos pertinentes para poder consultar el historial de calidad de un pedido.

La primera versión funcional, o **MVP**, contará con:

1. **Gestión de clientes y pedidos:** registrar, consultar y actualizar la información básica de pedidos de prueba.
2. **Registro de producción DTF:** vincular pedidos con lotes y guardar responsables, materiales y parámetros utilizados.
3. **Inspecciones de calidad:** documentar criterios y resultados de verificación del producto.
4. **No conformidades:** registrar defectos, su estado y las acciones de seguimiento.
5. **Dashboard básico:** presentar indicadores calculados a partir de los registros disponibles.

**Tecnología inicial propuesta:** Python, Flask, HTML, CSS, JavaScript, SQLite y SQLAlchemy. El sistema se desarrollará y probará con datos ficticios.

**Beneficio esperado:** disponer de registros organizados y relacionados entre sí, que faciliten la consulta de información, el seguimiento de defectos y el análisis básico del desempeño de calidad. Estos son beneficios esperados, no resultados medidos aún.

### 1.1.7. Objetivos del proyecto

#### Objetivo general

**Diseñar, desarrollar y evaluar un prototipo funcional de aplicación web para apoyar la gestión y el seguimiento de la calidad en los procesos de estampado textil DTF de la empresa ficticia QualityPrint, mediante el registro centralizado de pedidos, producción, inspecciones y no conformidades.**

#### Objetivos específicos

1. **Caracterizar** el proceso operativo de estampado DTF e identificar los puntos de control de calidad relevantes para el sistema.
2. **Definir y documentar** los requisitos funcionales, no funcionales, usuarios y reglas de negocio de la aplicación.
3. **Diseñar** la arquitectura, el modelo de base de datos y los prototipos de las interfaces principales.
4. **Implementar** módulos para administrar pedidos, lotes de producción, inspecciones y no conformidades de la empresa ficticia.
5. **Incorporar** indicadores básicos de calidad a partir de los registros de demostración almacenados.
6. **Verificar** el funcionamiento de los módulos y la consistencia de sus datos mediante pruebas documentadas.
7. **Publicar y documentar** el proyecto en GitHub con instrucciones de instalación, capturas y evidencias de ejecución para su presentación en un portafolio profesional.

## 2. Justificación

La propuesta articula la documentación de procesos de calidad con una solución informática que modela situaciones típicas de la producción DTF. Desde el aprendizaje de desarrollo de software, permite demostrar análisis de necesidades, diseño de datos, programación web, pruebas y uso de control de versiones. Al trabajar con una empresa ficticia y registros de prueba se facilita la reproducción de escenarios sin utilizar información real de clientes.

## 3. Alcance de la primera versión (MVP)

**Incluye:** gestión básica de clientes y pedidos; lotes de producción; registro de inspecciones; registro y seguimiento de no conformidades; dashboard con indicadores; validación de formularios; almacenamiento local; documentación técnica y pruebas.

**No incluye inicialmente:** facturación, contabilidad, pagos, integración directa con la impresora, control de varias sedes, inventario avanzado, aplicación móvil nativa ni certificación ISO. Estas funciones podrán evaluarse para versiones posteriores.

## 4. Usuarios previstos

| Rol | Uso principal |
|---|---|
| Gerencia | Consultar indicadores y seguimiento general |
| Comercial y diseño | Registrar y consultar pedidos y aprobación del diseño |
| Operación DTF | Registrar lotes y parámetros de producción |
| Calidad | Registrar inspecciones, no conformidades y seguimiento |

La asignación concreta de permisos se establecerá en la etapa de análisis de requisitos.

## 5. Tecnologías preliminares

- **Backend:** Python y Flask.
- **Frontend:** HTML, CSS y JavaScript; Bootstrap opcional.
- **Persistencia:** SQLite con SQLAlchemy.
- **Herramientas:** Visual Studio Code, Git, GitHub y diagrams.net; Figma opcional.

Las tecnologías se confirmarán durante la fase de diseño técnico.

## 6. Entregables del proyecto

1. Documentación esencial de la empresa ficticia y del SGC.
2. Documento de requisitos y casos de uso.
3. Diagramas de procesos, arquitectura y modelo entidad-relación.
4. Código de la aplicación web y estructura de base de datos.
5. Resultados de pruebas con datos de demostración.
6. README, guía de instalación, capturas y repositorio GitHub.

## 7. Restricciones y criterios de éxito

**Restricciones:** empresa ficticia, equipo de desarrollo académico, recursos preferentemente gratuitos, uso de datos de prueba y desarrollo incremental. Los valores de operación DTF se definirán mediante información técnica de los insumos/equipos y validación, no mediante parámetros universales inventados.

**Criterios mínimos de éxito del MVP:**

- Un pedido puede asociarse a un lote de producción y consultarse posteriormente.
- Se registra una inspección asociada al lote/pedido.
- Una inspección no conforme puede vincularse a un registro de no conformidad.
- El dashboard muestra información coherente con los registros guardados.
- El sistema se puede instalar siguiendo el README y supera los casos de prueba esenciales.

## 8. Control de cambios

| Versión | Fecha | Cambio | Estado |
|---|---|---|---|
| 0.1 | 2026-11-10 | Primera propuesta | Borrador |
| 1.0 | 2026-11-10 | Revisión inicial | Reabierta para corrección |
| 1.1 | 2026-11-10 | Se explicitan y amplían 1.1.5, 1.1.6 y 1.1.7 | Pendiente de aprobación |

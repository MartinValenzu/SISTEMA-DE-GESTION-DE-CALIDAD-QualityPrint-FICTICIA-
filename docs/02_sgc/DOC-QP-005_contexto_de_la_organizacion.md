# DOC-QP-005 — Contexto de la organización

| Campo | Información |
|---|---|
| Proyecto | QualityPrint — Sistema de Gestión de Calidad |
| Código documental | DOC-QP-005 |
| Etapa | 2. Documentación de la empresa y del SGC |
| Apartado | 2.3. Contexto de la organización |
| Versión | 1.0 |
| Fecha | 10 de noviembre de 2026 |
| Estado | **Aprobado para el caso de estudio** |
| Responsable propuesto | Gerencia general y apoyo de Control de calidad |
| Organización | QualityPrint — empresa ficticia |

> **Aclaración:** QualityPrint es un caso de estudio para portafolio. Los factores, necesidades, riesgos y condiciones son supuestos de diseño; no proceden de entrevistas, auditorías o mediciones en una empresa real. Las referencias a requisitos legales no implican que se haya realizado una evaluación jurídica específica.

## 1. Propósito

Identificar condiciones internas y externas que pueden influir en los resultados del Sistema de Gestión de Calidad (SGC), reconocer las partes interesadas pertinentes y delimitar formalmente las actividades que cubrirá QualityPrint.

Este documento conecta la caracterización de la empresa con el futuro mapa de procesos, la matriz de riesgos, los procedimientos y el software.

**Documentos relacionados:** [DOC-QP-001](../01_proyecto/DOC-QP-001_ficha_del_proyecto.md), [DOC-QP-003](DOC-QP-003_informacion_general_empresa.md), [DOC-QP-004](DOC-QP-004_direccionamiento_estrategico.md) y [ROADMAP](../../ROADMAP_QUALITYPRINT.md).

---

## 2.3.1. Identificar factores internos

### 2.3.1.1. Descripción del entorno interno

QualityPrint se modela como una pequeña empresa de **cinco trabajadores**, con **una impresora DTF**, equipos de transferencia térmica y producción bajo pedido. Su desempeño depende de coordinar adecuadamente el registro de especificaciones, la preparación del diseño, la impresión, la transferencia y la inspección final.

### 2.3.1.2. Matriz de factores internos

| ID | Factor interno | Condición considerada (supuesto) | Efecto potencial en calidad | Tratamiento inicial propuesto |
|---|---|---|---|---|
| FI-01 | Tamaño del equipo | Cinco trabajadores y posibles funciones compartidas | Dependencia de personas clave y riesgo de tareas sin responsable | Definir roles y suplencias |
| FI-02 | Capacidad productiva | Una impresora DTF | Una falla del equipo puede detener todos los pedidos | Mantenimiento preventivo y plan de contingencia |
| FI-03 | Conocimiento técnico | Competencias DTF por documentar | Variabilidad en impresión, curado y transferencia | Instrucciones de trabajo y capacitación |
| FI-04 | Gestión de registros | Registros manuales/dispersos en el escenario inicial | Dificultad de trazabilidad y consulta | Diseñar identificación de pedido, lote e inspección |
| FI-05 | Control del diseño | Personal comercial valida arte y especificaciones | Errores de tamaño, texto o ubicación | Aprobación documentada del cliente |
| FI-06 | Inspección final | Función de calidad separada de operación cuando sea viable | Liberación de unidades con defectos si no existe criterio | Lista de verificación y registro de liberación |
| FI-07 | Recursos financieros | Presupuesto limitado propio de una empresa pequeña | Dificultad de invertir en materiales, equipos y software | Priorizar controles críticos y herramientas asequibles |
| FI-08 | Cultura de mejora | SGC aún por definir en el caso de estudio | Se repiten defectos si no se analizan causas | Registro de no conformidades y seguimiento |

### 2.3.1.3. Fortalezas y limitaciones

**Fortalezas potenciales del modelo:** cercanía con el cliente, comunicación rápida entre cinco funciones, posibilidad de implementar controles sencillos y enfoque en un solo método de estampado.

**Limitaciones potenciales:** dependencia de una sola impresora, concentración de funciones, poca redundancia operativa y ausencia inicial de registros centralizados.

**Conclusión:** los factores internos deberán revisarse al caracterizar los procesos (apartado 2.4) y al desarrollar la matriz de riesgos (apartado 2.6).

---

## 2.3.2. Identificar factores externos

### 2.3.2.1. Entorno externo

Para este proyecto ficticio se consideran tendencias y condiciones posibles del sector textil y de los insumos DTF, sin afirmar que actualmente estén afectando a una empresa concreta.

### 2.3.2.2. Matriz de factores externos

| ID | Factor externo | Escenario o condición posible | Efecto potencial | Respuesta de gestión propuesta |
|---|---|---|---|---|
| FE-01 | Proveedores de tinta, film y polvo adhesivo | Variación de especificaciones o disponibilidad | Diferencias de adherencia, color o continuidad | Evaluar proveedores y conservar fichas técnicas |
| FE-02 | Mercado y preferencias | Cambios de diseños y demanda por temporada | Necesidad de adaptar plazos y capacidades | Revisar pedidos y planificar la producción |
| FE-03 | Competencia | Alternativas en precio, calidad o tiempo | Mayor exigencia de cumplimiento | Medir defectos, reclamos y entregas |
| FE-04 | Tecnología | Nuevos insumos y equipos DTF | Posibilidades de mejora y necesidad de capacitación | Validar cambios antes de implementarlos |
| FE-05 | Condiciones económicas | Variación de costos de materiales y energía | Presión sobre disponibilidad y continuidad | Planificar compras, consumos y presupuesto |
| FE-06 | Requisitos aplicables | Normas de seguridad, actividad económica y obligaciones que correspondan a la jurisdicción | Riesgos operativos o de incumplimiento | Identificar obligaciones concretas al definir ubicación legal |
| FE-07 | Condiciones ambientales y del lugar de trabajo | Temperatura, humedad, ventilación y energía eléctrica | Posibles variaciones del proceso o interrupciones | Verificar instrucciones técnicas y condiciones de operación |
| FE-08 | Logística y transporte | Retrasos, daños o errores de despacho | Pedidos incompletos o entrega fuera de plazo | Verificación de cantidades y registros de salida |

### 2.3.2.3. Priorización inicial

En el supuesto de una empresa con **una sola impresora DTF**, se priorizará la continuidad del equipo, la calidad de los insumos, la aprobación de los diseños y la entrega en fecha. La evaluación formal de probabilidad y severidad se desarrollará en la matriz de riesgos; estas prioridades **no equivalen a una medición real**.

### 2.3.2.4. Seguimiento del entorno

Gerencia revisará los factores al menos una vez al año en la simulación y cuando haya cambios relevantes de equipo, proveedor, materiales, gama de productos o requisitos del cliente. Las decisiones se registrarán para mantener control de cambios.

---

## 2.3.3. Identificar partes interesadas

### 2.3.3.1. Definición

Las partes interesadas son personas u organizaciones que pueden afectar el funcionamiento del SGC, verse afectadas por sus resultados o establecer requisitos relevantes para QualityPrint.

### 2.3.3.2. Matriz de identificación

| ID | Parte interesada | Relación con QualityPrint | Relevancia para el SGC |
|---|---|---|---|
| PI-01 | Clientes particulares | Solicitan prendas personalizadas | Alta: definen requisitos y evalúan entregas |
| PI-02 | Empresas y emprendimientos clientes | Encargan uniformes, prendas de marca y pedidos recurrentes | Alta: requieren consistencia y trazabilidad |
| PI-03 | Trabajadores | Ejecutan ventas, diseño, producción, control y logística | Alta: su competencia afecta la calidad |
| PI-04 | Gerencia | Define recursos y objetivos | Alta: decide prioridades y mejora |
| PI-05 | Proveedores de insumos | Suministran film, tintas, adhesivo y prendas | Alta: condicionan el resultado del proceso |
| PI-06 | Prestadores de mantenimiento | Apoyan reparación/calibración cuando sea necesario | Media/alta: contribuyen a la disponibilidad del equipo |
| PI-07 | Operadores logísticos | Transportan pedidos terminados cuando se externalice | Media: influyen en integridad y entrega |
| PI-08 | Autoridades aplicables | Establecen obligaciones relevantes según actividad y jurisdicción | Alta cuando existan requisitos aplicables |
| PI-09 | Comunidad o entorno próximo | Puede verse afectado por la operación | A determinar según ubicación y condiciones reales |

### 2.3.3.3. Selección de partes pertinentes

Para el **primer alcance del SGC** se considerarán centrales los clientes, trabajadores, gerencia, proveedores y autoridades aplicables. Los demás actores serán objeto de seguimiento según los servicios efectivamente contratados y la ubicación que se defina en el escenario.

---

## 2.3.4. Identificar necesidades y expectativas

### 2.3.4.1. Matriz de necesidades, evidencias y respuesta

| Parte interesada | Necesidad / expectativa relevante | Método de conocimiento propuesto | Respuesta de QualityPrint | Evidencia prevista |
|---|---|---|---|---|
| Clientes | Diseños correctos, tamaños, colores, cantidades y entrega acordada | Requisitos de pedido y aprobación del diseño | Confirmar especificaciones; inspeccionar antes de entrega | Orden, diseño aprobado e inspección |
| Trabajadores | Instrucciones claras, recursos y formación | Revisión de competencias y necesidades de operación | Asignar responsabilidades, capacitar y facilitar instrucciones | Matriz de funciones y registro de formación |
| Gerencia | Control de defectos, plazos y resultados | Indicadores y reuniones de revisión | Analizar datos y decidir mejoras | Reportes y acciones |
| Proveedores | Especificaciones claras, comunicación de cambios | Órdenes de compra y fichas técnicas | Acordar características de insumos | Recepción y verificación de materiales |
| Mantenimiento | Información técnica y acceso controlado al equipo | Manuales e historial de incidencias | Planificar y registrar intervenciones | Plan e historial de mantenimiento |
| Logística | Producto liberado y datos correctos de despacho | Orden de entrega | Verificar cantidades y estado | Registro de despacho |
| Autoridades aplicables | Cumplimiento de obligaciones según país y actividad | Identificación documental de requisitos aplicables | Determinar responsables y conservar evidencias | Registro legal aplicable, por elaborar |

### 2.3.4.2. Requisitos que deben trasladarse a los procesos

1. **Identificación única:** cada pedido debe relacionarse con el diseño aprobado, lote, inspección y, cuando corresponda, no conformidad.
2. **Confirmación previa a producción:** se debe conservar la aceptación del diseño y las especificaciones del cliente.
3. **Control de materiales y equipo:** insumos y ajustes utilizados deben ser apropiados y documentados según el proceso.
4. **Inspección documentada:** antes de liberar un pedido deben registrarse resultados y decisión.
5. **Tratamiento de defectos:** cuando se detecte un producto no conforme debe identificarse, retenerse o gestionarse para evitar una entrega no autorizada.
6. **Seguimiento:** la gerencia debe poder consultar resultados periódicos, con datos suficientes para calcular indicadores.

### 2.3.4.3. Revisión de necesidades

Las necesidades se revisarán ante cambios de especificaciones, reclamaciones, fallas recurrentes o nuevos productos. Las que se traduzcan en requisitos del software serán formalizadas en la **etapa 3**; esta matriz no sustituye el documento de requisitos informáticos.

---

## 2.3.5. Definir el alcance del SGC

### 2.3.5.1. Declaración propuesta del alcance

> **El Sistema de Gestión de Calidad de QualityPrint comprende la planificación y control de los pedidos de personalización textil mediante tecnología DTF, desde la recepción y confirmación de requisitos del cliente y la aprobación del diseño hasta la preparación de materiales, impresión DTF, aplicación y curado del adhesivo, transferencia a la prenda, acabado, inspección, liberación, empaque y entrega. Incluye los procesos de apoyo necesarios para controlar proveedores, compras, recursos y equipos, competencias del personal, documentos y registros, no conformidades, seguimiento de resultados y mejora continua. El alcance corresponde a una única operación ficticia de estampado textil DTF con una impresora y hasta cinco trabajadores.**

### 2.3.5.2. Límites y condiciones del alcance

| Tema | Decisión de alcance |
|---|---|
| Operación | Una empresa ficticia de producción bajo pedido |
| Personal | Cinco trabajadores previstos; funciones pueden combinarse |
| Tecnología principal | Estampado DTF; una impresora DTF y equipos auxiliares |
| Productos | Camisetas, sudaderas, uniformes y otras prendas compatibles previamente verificadas |
| Diseño | Se contempla diseño preparado por personal propio o proporcionado por el cliente, siempre con aprobación documentada |
| Procesos de apoyo | Compras, evaluación de proveedores, mantenimiento, documentación, formación y análisis de datos |
| Servicios externos | Se controlarán aquellos que afecten la calidad del pedido; no se supone que la empresa los preste internamente |
| Localización | **No se define dirección física** por tratarse de un caso ficticio |
| Métodos fuera del alcance productivo | Serigrafía, bordado y sublimación no forman parte de la operación DTF definida |
| Sistemas ajenos | Facturación, contabilidad y comercio electrónico completo no son módulos previstos del software inicial |

**Importante:** las actividades no ofrecidas por QualityPrint (por ejemplo, bordado) están fuera del **alcance operativo elegido**. Esto no implica declarar automáticamente *no aplicable* ningún requisito de una norma de gestión. Toda justificación de aplicabilidad de requisitos se estudiará y documentará separadamente cuando corresponda.

### 2.3.5.3. Inicio y fin del flujo principal

- **Entrada inicial:** solicitud del cliente y especificaciones de diseño, prenda y cantidades.
- **Inicio de control:** revisión del pedido y aprobación de requisitos antes de producir.
- **Transformación:** preparación, impresión DTF, aplicación y curado, transferencia y acabado.
- **Verificación:** inspección documentada y decisión de liberación/retención.
- **Salida final:** pedido entregado conforme a requisitos y evidencia de entrega.
- **Retroalimentación:** observaciones, reclamaciones, defectos e indicadores para mejorar.

### 2.3.5.4. Diferencia entre el alcance del SGC y el del software

El **SGC** abarca la gestión y los controles empresariales descritos arriba, incluidos recursos, proveedores y operaciones físicas. La **primera versión del software** solo implementará módulos de clientes/pedidos, lotes DTF, inspecciones, no conformidades y un dashboard básico.

No se debe presentar el software como una implementación automática de todo el SGC ni como evidencia de certificación.

### 2.3.5.5. Responsable, disponibilidad y mantenimiento

- **Responsable de establecer y revisar el alcance (simulado):** Gerencia general.
- **Apoyo:** Control de calidad.
- **Medio de publicación:** `docs/02_sgc/DOC-QP-005_contexto_de_la_organizacion.md`.
- **Revisión:** anual en el escenario ficticio y siempre que cambien de manera relevante productos, métodos, capacidad o servicios contratados.
- **Estado:** alcance aprobado como propuesta de la empresa ficticia; no constituye certificación ni verificación real.

---

## 3. Consecuencias para las etapas siguientes

| Documento o módulo futuro | Insumo de este análisis |
|---|---|
| 2.4. Mapa de procesos | Entradas, actividades, salidas y responsables |
| 2.5. Proceso de producción DTF | Factores técnicos, materiales y puntos de control |
| 2.6. Matriz de riesgos y oportunidades | FI-01–FI-08, FE-01–FE-08 |
| 2.7. Gestión documental | Evidencias, control y revisión de registros |
| 2.8. Procedimientos y formatos | Requisitos de aprobación, inspección, liberación y acciones |
| Etapa 3. Requisitos del software | Identificadores, relaciones y necesidades de los roles |
| Etapas 6–7. Desarrollo y pruebas | Flujos y controles que deben implementarse y probarse |

## 4. Lista de verificación del apartado 2.3

- [x] **2.3.1.** Identificar factores internos.
- [x] **2.3.2.** Identificar factores externos.
- [x] **2.3.3.** Identificar partes interesadas.
- [x] **2.3.4.** Identificar necesidades y expectativas.
- [x] **2.3.5.** Definir el alcance del SGC.

**Criterios de aprobación:** que la documentación sea consistente con la empresa de cinco trabajadores y una impresora DTF, que se distingan los supuestos de hechos reales, que el alcance cubra los procesos definidos sin confundirlos con módulos del software y que las matrices sean una base utilizable para las próximas etapas.

## 5. Control de cambios

| Versión | Fecha | Descripción | Estado |
|---|---|---|---|
| 0.1 | 10/11/2026 | Elaboración de los subpuntos 2.3.1–2.3.5 | Borrador |
| 1.0 | 10/11/2026 | Aprobación de los cinco subpuntos | Aprobado |

**Siguiente apartado:** [DOC-QP-006 — Procesos y mapa de procesos](DOC-QP-006_procesos_y_mapa_de_procesos.md), en revisión.

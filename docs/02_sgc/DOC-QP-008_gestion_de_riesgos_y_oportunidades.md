# DOC-QP-008 — Gestión de riesgos y oportunidades

| Campo | Información |
|---|---|
| Proyecto | QualityPrint — Sistema de Gestión de Calidad |
| Código documental | DOC-QP-008 |
| Etapa | 2. Documentación de la empresa y del SGC |
| Apartado | 2.6. Gestión de riesgos y oportunidades |
| Versión | 1.0 |
| Fecha | 10 de noviembre de 2026 |
| Estado | **Aprobado para el caso de estudio** |
| Organización | QualityPrint — empresa ficticia |
| Responsable del documento | Gerencia general, con apoyo de Control de calidad |

> **Aviso metodológico:** los peligros, probabilidades, impactos y puntuaciones incluidos aquí son **supuestos de una simulación académica**, no observaciones ni mediciones reales. Este documento no constituye una evaluación profesional de seguridad y salud en el trabajo, cumplimiento normativo o certificación ISO. Los riesgos físicos, químicos, térmicos y de ventilación requieren evaluación específica del equipo, los materiales, las fichas de datos de seguridad (SDS) y el lugar donde opere una empresa real.

## 1. Propósito y alcance

Identificar, analizar, priorizar y proponer tratamientos para los riesgos y oportunidades que puedan afectar el cumplimiento de requisitos de clientes, la conformidad de las prendas, la trazabilidad, las entregas y la mejora del Sistema de Gestión de Calidad (SGC) en la empresa ficticia QualityPrint.

Se consideran los procesos estratégicos, operativos y de apoyo establecidos en [DOC-QP-006](DOC-QP-006_procesos_y_mapa_de_procesos.md), así como el flujo productivo descrito en [DOC-QP-007](DOC-QP-007_proceso_de_produccion_DTF.md).

**Documentos relacionados:** [DOC-QP-003 — Empresa](DOC-QP-003_informacion_general_empresa.md), [DOC-QP-004 — Dirección estratégica](DOC-QP-004_direccionamiento_estrategico.md), [DOC-QP-005 — Contexto](DOC-QP-005_contexto_de_la_organizacion.md) y [ROADMAP](../../ROADMAP_QUALITYPRINT.md).

### 1.1. Objetivos de este análisis
- Evitar que un producto no conforme llegue al cliente.
- Prevenir errores del diseño, producción e inspección.
- Favorecer la continuidad del proceso con una sola impresora DTF.
- Establecer responsabilidades claras sobre los controles.
- Conservar información útil para indicadores, acciones correctivas y futuros requisitos del software.

### 1.2. Qué incluye y qué no incluye
**Incluye:** eventos posibles, causas, consecuencias sobre calidad, matriz de priorización, controles propuestos, responsables, oportunidades y criterios de seguimiento.

**No incluye:** mediciones en campo, fichas reales de equipos elegidos, un inventario validado de sustancias, valoración reglamentaria de riesgos laborales ni un análisis cuantitativo basado en incidentes reales.

---

## 2.6.1. Identificar riesgos de los procesos

### 2.6.1.1. Definición operativa
Se considera **riesgo** un evento o condición incierta que podría afectar negativamente los resultados planificados del SGC. Una **oportunidad** es una condición que, si se aprovecha, podría mejorar los procesos o sus resultados.

### 2.6.1.2. Riesgos iniciales por proceso

| ID | Proceso | Evento de riesgo | Consecuencia posible |
|---|---|---|---|
| R-01 | PO-01 Pedido | Especificaciones incompletas o incorrectas | Prenda no conforme, reproceso o reclamación |
| R-02 | PO-01 Diseño | Imprimir un arte sin aprobación o versión equivocada | Diseño incorrecto en el pedido |
| R-03 | PA-01 Materiales | Material textil o consumible DTF incompatible o defectuoso | Mala adherencia, acabado o retrabajo |
| R-04 | PO-02 Impresión | Bandas, errores de cobertura de tinta o fallos de impresión | Transferencia defectuosa o pérdida de insumos |
| R-05 | PO-02 Adhesivo/curado | Distribución o curado incorrecto del adhesivo | Desprendimiento o apariencia deficiente |
| R-06 | PO-02 Transferencia | Ajustes o despegue incorrectos para la combinación de materiales | Transferencia defectuosa o daño de la prenda |
| R-07 | PO-03 Inspección | No detectar un defecto o liberar sin registrar inspección | Entrega de productos no conformes |
| R-08 | PO-03 No conformidades | No identificar, separar o seguir producto retenido | Mezcla con producto conforme y entrega indebida |
| R-09 | PA-02 Mantenimiento | Falla de la única impresora o de equipo auxiliar | Interrupción de producción y retrasos |
| R-10 | PO-04 Entrega | Confusión de tallas, referencias o cantidades | Entrega incorrecta y reclamación |
| R-11 | PA-03 Documentación | Registros perdidos, incompletos o duplicados | Pérdida de trazabilidad y errores de análisis |
| R-12 | PA-04 Personal | Ausencia o preparación insuficiente de una persona clave | Errores de ejecución y dependencia operativa |
| R-13 | PE-02 Mejora | No revisar indicadores ni cerrar acciones | Repetición de problemas |
| R-14 | Entorno de producción | Exposición no controlada a polvo, vapores, calor o equipos | Daño a personas y posible interrupción de operaciones |

**R-14** se incorpora como condición crítica de seguridad relacionada con la operación. No se le asigna un nivel de riesgo laboral concluyente sin una valoración técnica específica. Su tratamiento **no debe posponerse** por una puntuación baja o por ausencia de accidentes previos.

### 2.6.1.3. Relación con factores del contexto
- La **única impresora DTF** aumenta la dependencia del mantenimiento (FI-02 y R-09).
- La posible **acumulación de funciones** afecta la inspección y el registro de responsabilidades (FI-01, R-07 y R-12).
- Los **proveedores de materiales** condicionan compatibilidad y calidad (FE-01 y R-03).
- Los registros dispersos del escenario inicial afectan el seguimiento de productos y acciones (FI-04, R-11 y R-13).

---

## 2.6.2. Identificar posibles causas

### 2.6.2.1. Matriz de causas

| Riesgo | Causa o desencadenante hipotético | Señal de alerta propuesta |
|---|---|---|
| R-01 | Pedido sin revisión de detalles, tallas o plazo | Campos obligatorios vacíos; cambios sin registrar |
| R-02 | Archivos sin control de versiones; aprobación no conservada | Existen varias versiones sin identificación |
| R-03 | Recepción sin comprobar ficha técnica, compatibilidad o estado | Insumos sin referencia o discrepancia con el pedido |
| R-04 | Configuración de RIP no verificada o condiciones del equipo inadecuadas | Defectos repetidos en film o incidencias |
| R-05 | Aplicación irregular o instrucciones técnicas no validadas | Áreas sin adhesivo, exceso o diferencias visibles |
| R-06 | Confundir tipo de despegue o usar valores de otra combinación | Bordes levantados, daño o transferencia incompleta |
| R-07 | Criterios ambiguos, carga de trabajo o inspección omitida | Pedido despachado sin registro de liberación |
| R-08 | No contar con identificación física o digital de unidades retenidas | Mezcla de lotes y estados inconsistentes |
| R-09 | Mantenimiento preventivo no planificado o no ejecutado | Fallas frecuentes y actividades vencidas |
| R-10 | Etiquetado o verificación final insuficientes | Cantidad de despacho distinta de la orden |
| R-11 | Formularios dispersos, datos duplicados o acceso no controlado | Registros contradictorios o faltantes |
| R-12 | Capacitación insuficiente y falta de suplencias | Tareas críticas sin responsable competente |
| R-13 | No establecer revisión periódica de indicadores y acciones | Hallazgos reiterados y acciones sin cierre |
| R-14 | Falta de extracción, desconocimiento de SDS, protección o instrucciones | Ausencia de controles documentados y de revisión del puesto |

### 2.6.2.2. Identificación de causas raíz
Las causas anteriores son hipótesis iniciales. Ante una no conformidad concreta, se deberá investigar su causa usando evidencia, por ejemplo con **5 porqués**, diagrama de Ishikawa o revisión de registros, sin considerar causa raíz a la primera suposición.

---

## 2.6.3. Evaluar probabilidad e impacto

### 2.6.3.1. Escala de probabilidad (P)

| Valor | Descripción | Criterio cualitativo para la simulación |
|---|---|---|
| 1 | Muy baja | Evento excepcional en el escenario previsto |
| 2 | Baja | Evento poco frecuente, pero posible |
| 3 | Media | Puede ocurrir ocasionalmente |
| 4 | Alta | Se espera que ocurra con relativa frecuencia |
| 5 | Muy alta | Podría ocurrir repetidamente si no se controla |

### 2.6.3.2. Escala de impacto en calidad (I)

| Valor | Descripción | Efecto posible sobre calidad y servicio |
|---|---|---|
| 1 | Insignificante | Incidencia menor sin afectar requisitos del cliente |
| 2 | Menor | Corrección simple y limitada |
| 3 | Moderado | Retrabajo, desperdicio o demora relevante |
| 4 | Alto | Pedido no conforme, reclamación o pérdida considerable |
| 5 | Crítico | Afectación grave del cumplimiento, continuidad o confianza |

### 2.6.3.3. Cálculo de prioridad
Para la **matriz de calidad de este caso simulado**:

```text
Puntaje = Probabilidad (P) × Impacto (I)
Rango posible: 1 a 25
```

| Puntaje | Clasificación propuesta | Criterio de gestión |
|---|---|---|
| 1–5 | Bajo | Mantener seguimiento de rutina |
| 6–10 | Moderado | Definir o reforzar controles y revisión |
| 11–15 | Alto | Priorizar plan de tratamiento y seguimiento |
| 16–25 | Muy alto | Tratar de manera preferente antes de exposición significativa del proceso |

**Límite importante:** multiplicar escalas ordinales es una herramienta **cualitativa de priorización**, no una probabilidad matemática ni una medida de seguridad industrial. No se deben usar estos umbrales para autorizar condiciones inseguras de trabajo.

### 2.6.3.4. Matriz de calor (referencia numérica)

| Impacto \ Probabilidad | P=1 | P=2 | P=3 | P=4 | P=5 |
|---|---:|---:|---:|---:|---:|
| I=5 | 5 | 10 | 15 | 20 | 25 |
| I=4 | 4 | 8 | 12 | 16 | 20 |
| I=3 | 3 | 6 | 9 | 12 | 15 |
| I=2 | 2 | 4 | 6 | 8 | 10 |
| I=1 | 1 | 2 | 3 | 4 | 5 |

---

## 2.6.4. Definir controles preventivos

### 2.6.4.1. Jerarquía práctica para la calidad
1. **Evitar o reducir el origen:** revisar requisitos, aprobación de arte, selección técnica de materiales y preparación del equipo.
2. **Detectar antes de liberar:** inspección durante proceso y al final, criterios verificables, identificación de lote.
3. **Contener el problema:** retención e identificación de productos potencialmente no conformes.
4. **Corregir y aprender:** documentar disposición, reinspección, causa y acción correctiva, cuando corresponda.

### 2.6.4.2. Controles previstos por riesgo

| Riesgo | Medida preventiva o de detección | Evidencia prevista |
|---|---|---|
| R-01 | Pedido con campos obligatorios y confirmación de requisitos | Pedido y aceptación |
| R-02 | Control de versiones del arte y aprobación antes de producir | Versión aprobada |
| R-03 | Inspección de recepción, ficha técnica y compatibilidad | Registro de materiales |
| R-04 | Validación de configuración RIP y control de film impreso | Registro de impresión |
| R-05 | Instrucciones validadas para adhesivo y curado, verificación visual | Registro de producción |
| R-06 | Parámetros de prensa y tipo de despegue validados según proveedor | Registro de transferencia |
| R-07 | Inspección final obligatoria antes de decisión de entrega | Inspección y liberación |
| R-08 | Identificación, retención y disposición documentada | No conformidad / reinspección |
| R-09 | Plan de mantenimiento, inspecciones previas y contingencia de equipo | Plan y registros |
| R-10 | Verificación de empaque contra pedido y liberación | Lista de despacho |
| R-11 | Identificadores únicos, validaciones y control documental | Registros relacionados |
| R-12 | Matriz de competencias y suplencias autorizadas | Registro de capacitación |
| R-13 | Revisión mensual de indicadores y seguimiento de acciones | Acta o registro de revisión |
| R-14 | Evaluación específica del puesto, SDS, extracción/ventilación apropiada, EPP y capacitación | Evaluación y controles de seguridad específicos |

### 2.6.4.3. Eficacia de los controles
Un control solo se considerará **implementado y eficaz** cuando exista evidencia de aplicación y seguimiento. En este caso los controles permanecen **propuestos**, sin afirmar que se ejecutaron en una empresa real.

---

## 2.6.5. Asignar responsables

### 2.6.5.1. Matriz de responsabilidad

| Riesgos | Responsable principal propuesto | Apoyo |
|---|---|---|
| R-01 y R-02 | Comercial y diseño | Calidad |
| R-03 | Administración/logística | Operador DTF |
| R-04, R-05 y R-06 | Operador DTF | Calidad |
| R-07 y R-08 | Control de calidad | Gerencia y operador |
| R-09 | Operador DTF | Gerencia / servicio técnico |
| R-10 | Administración/logística | Comercial |
| R-11 | Control de calidad | Gerencia / desarrollo del software |
| R-12 | Gerencia | Responsables de las funciones |
| R-13 | Gerencia | Control de calidad |
| R-14 | Gerencia | Operación DTF y especialista competente en seguridad cuando corresponda |

### 2.6.5.2. Seguimiento y escalamiento
- **Operación DTF:** informa fallos, defectos o condiciones inseguras antes de continuar una operación.
- **Control de calidad:** documenta problemas de conformidad, retiene lotes afectados y revisa evidencias.
- **Gerencia:** asigna recursos y resuelve prioridades; las decisiones de seguridad deben basarse en evaluación competente y requisitos aplicables.
- **Periodicidad propuesta:** revisar los riesgos de calidad mensualmente durante la simulación y ante cambios relevantes en materiales, equipo, clientes o procesos.
- **Escalamiento:** una condición potencialmente peligrosa o un defecto crítico no espera la siguiente revisión mensual.

---

## 2.6.6. Elaborar la matriz de riesgos

### 2.6.6.1. Matriz de priorización inicial (datos completamente simulados)

Los valores de P e I se escogieron solo para **mostrar el funcionamiento del método**. No reflejan frecuencias ni severidades reales.

| ID | Riesgo resumido | P | I | P×I | Nivel ilustrativo | Responsable |
|---|---|---:|---:|---:|---|---|
| R-01 | Pedido incompleto | 3 | 3 | 9 | Moderado | Comercial/diseño |
| R-02 | Arte no aprobado/incorrecto | 3 | 4 | 12 | Alto | Comercial/diseño |
| R-03 | Material incompatible | 3 | 4 | 12 | Alto | Administración/logística |
| R-04 | Fallo en impresión | 3 | 3 | 9 | Moderado | Operador DTF |
| R-05 | Adhesivo o curado incorrecto | 3 | 4 | 12 | Alto | Operador DTF |
| R-06 | Transferencia incorrecta | 3 | 4 | 12 | Alto | Operador DTF |
| R-07 | Inspección insuficiente | 3 | 5 | 15 | Alto | Control de calidad |
| R-08 | Producto retenido entregado | 2 | 5 | 10 | Moderado* | Control de calidad |
| R-09 | Falla de la única impresora | 3 | 4 | 12 | Alto | Operador DTF |
| R-10 | Error de empaque/entrega | 3 | 3 | 9 | Moderado | Administración/logística |
| R-11 | Pérdida de trazabilidad | 3 | 4 | 12 | Alto | Control de calidad |
| R-12 | Falta de competencia/suplencia | 3 | 3 | 9 | Moderado | Gerencia |
| R-13 | No seguimiento de mejoras | 3 | 3 | 9 | Moderado | Gerencia |

\* **R-08:** aunque su puntuación simulada resulte «moderada», la **retención y la prohibición de despacho sin liberación son controles obligatorios**. Las cifras de la matriz no sustituyen reglas críticas del proceso.

**R-14 — Seguridad de las personas:** se registra por separado como **riesgo de evaluación específica pendiente**, **sin asignar P×I académico**. La operación requiere controles de seguridad adecuados independientemente de la puntuación del resto de los riesgos.

### 2.6.6.2. Orden preliminar de atención
Se propone comenzar por: **R-07 (inspección), R-02 (arte), R-03 (materiales), R-05 (curado), R-06 (transferencia), R-09 (equipo) y R-11 (trazabilidad)**. Para la seguridad de las personas (R-14) se requiere un análisis especializado previo a la ejecución física.

### 2.6.6.3. Ejemplo de ficha de tratamiento (sin evidencia de ejecución)

| Campo | Ejemplo propuesto |
|---|---|
| Riesgo | R-02 — Diseño equivocado o no aprobado |
| Causa supuesta | Varias versiones de arte sin identificación |
| Medida | Exigir ID de pedido, versión de archivo y aceptación del cliente |
| Responsable | Comercial y diseño |
| Evidencia esperada | Registro de aprobación y versión vinculada al lote |
| Prioridad ilustrativa | 12 — Alto |
| Fecha objetivo | **Por definir** |
| Estado | **Propuesto; no implementado ni verificado** |
| Comprobación futura | Confirmar que ningún lote se creó sin aprobación documentada |

### 2.6.6.4. Riesgo residual
Después de documentar controles implementados, se podrá volver a estimar P e I para obtener una prioridad **residual**. En esta versión no se inventan reducciones de puntaje: **no existen resultados reales de efectividad**.

---

## 3. Identificación y aprovechamiento de oportunidades

| ID | Oportunidad | Beneficio esperado (hipotético) | Acción propuesta | Responsable |
|---|---|---|---|---|
| O-01 | Centralizar registros con QualityPrint-SGC | Mejor trazabilidad y consulta | Implementar vínculos pedido-lote-inspección-NC | Desarrollo / Calidad |
| O-02 | Estandarizar verificación del pedido | Menos errores de diseño y cantidades | Lista de requisitos y aprobación del arte | Comercial/diseño |
| O-03 | Establecer indicadores y revisiones | Detectar defectos recurrentes | Dashboard y revisión periódica | Gerencia / Calidad |
| O-04 | Documentar parámetros válidos por combinación de insumos | Mayor consistencia del proceso | Fichas técnicas e instrucciones por material/equipo | Operador DTF / Calidad |
| O-05 | Capacitar y definir suplentes | Menor dependencia de personas | Matriz de competencias | Gerencia |
| O-06 | Revisar mantenimiento preventivo | Menor riesgo de parada del único equipo | Plan de mantenimiento según fabricante | Operador / Gerencia |

**Criterio para evaluar oportunidades:** comprobar en una revisión posterior si la acción fue ejecutada, qué registros aportó y si produjo cambios observables. No afirmar mejoras porcentuales sin datos.

---

## 4. Integración con el software futuro

El software **no elimina por sí mismo** los riesgos físicos del proceso DTF. Sí puede apoyar controles administrativos y de trazabilidad:

| Necesidad de control | Función posible en el MVP |
|---|---|
| Pedido incompleto o diseño no autorizado | Validar campos y conservar aprobación/versión |
| Pérdida de rastreabilidad | Relacionar pedido, lote, inspección y NC |
| Falta de evidencia de inspección | Registrar inspección y decisión de liberación |
| Productos retenidos | Registrar estado y restringir cambio de estado sin autorización |
| Repetición de defectos | Registrar códigos de defecto y consultar indicadores |
| Acciones sin seguimiento | Registrar responsable, plazo y estado de acción |

Inventarios, mantenimiento y matriz de riesgos dentro del software podrán evaluarse como **ampliaciones futuras** conforme a las etapas 3 y 9 del proyecto.

---

## 5. Revisión y actualización de la matriz

1. **En la creación:** asignar ID, evento, proceso, causa, consecuencia, control y responsable.
2. **En la valoración:** documentar la justificación de P e I y la versión de la matriz.
3. **En la respuesta:** definir tratamiento, responsable, fecha objetivo y evidencia esperada.
4. **En el seguimiento:** registrar estado, resultados y nuevas incidencias.
5. **Tras cambios relevantes:** revisar cuando cambien equipos, insumos, volumen de pedidos, personal o criterios de calidad.
6. **En el cierre:** conservar control de versiones sin borrar resultados anteriores.

**Responsable de aprobación del contenido (simulado):** Gerencia general; **custodia de registros:** Control de calidad.  
**Frecuencia propuesta de revisión:** mensual en ejercicios simulados y ante cambios relevantes; esta frecuencia es un criterio planificado, no actividad ejecutada.

---

## 6. Lista de verificación — aprobada

- [x] **2.6.1.** Identificar riesgos de los procesos.
- [x] **2.6.2.** Identificar posibles causas.
- [x] **2.6.3.** Evaluar probabilidad e impacto.
- [x] **2.6.4.** Definir controles preventivos.
- [x] **2.6.5.** Asignar responsables.
- [x] **2.6.6.** Elaborar la matriz de riesgos.

### Criterios de aprobación
- La matriz está alineada con los procesos de DOC-QP-006 y el flujo de DOC-QP-007.
- Los puntajes tienen un método reproducible y se identifican como simulados.
- Los riesgos críticos del proceso conservan controles obligatorios aunque la puntuación sea baja.
- Las condiciones de seguridad no se evalúan de modo superficial con la matriz de calidad.
- Cada tratamiento propuesto posee responsable y evidencia verificable.
- Las oportunidades están diferenciadas de los riesgos y se pueden seguir posteriormente.
- No se presentan acciones propuestas como controles ya implementados.

## 7. Control de cambios

| Versión | Fecha | Modificación | Estado |
|---|---|---|---|
| 0.1 | 10/11/2026 | Identificación, evaluación ilustrativa y matriz inicial de riesgos/oportunidades | Borrador |
| 1.0 | 10/11/2026 | Aprobación de los seis subpuntos del apartado 2.6 | Aprobado |

**Siguiente documento:** [DOC-QP-009 — Gestión documental](DOC-QP-009_gestion_documental.md) y [LM-QP-001 — Listado maestro](LM-QP-001_listado_maestro_de_documentos.md), en revisión.

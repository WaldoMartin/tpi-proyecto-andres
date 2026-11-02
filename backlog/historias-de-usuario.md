# Backlog – Historias de usuario

Sistema de Gestión de Inventario y Trazabilidad de Donaciones – Proyecto Andrés 5 panes y dos peces.

Cada historia sigue el formato **Como [rol], quiero [acción] para [beneficio]**. Los roles salen del organigrama (Entrega 3), y las entidades salen del diccionario de datos (`Insumo_Alimento`, `Donacion`, `Racion_Diaria`).

Prioridad con el método MoSCoW: **M** = imprescindible, **S** = importante, **C** = deseable. La estimación está en *story points* (escala de Fibonacci).

| ID | Historia de usuario | Criterios de aceptación | Prior. | Pts | Sprint |
|---|---|---|---|---|---|
| HU-01 | Como **administrador del sistema**, quiero gestionar usuarios y roles (voluntariado, cocina, dirección, administración) para que cada persona acceda solo a lo que le corresponde. | Se pueden crear, editar y desactivar usuarios. Cada usuario tiene un rol. Un voluntario no puede ver la sección de finanzas. | M | 3 | 1 |
| HU-02 | Como **voluntario**, quiero registrar una donación (insumo, cantidad, fecha, vencimiento) para que el stock se actualice automáticamente. | Al guardar, `Cantidad_Stock` aumenta. Los campos obligatorios se validan. El registro se completa en menos de 3 minutos. | M | 5 | 1 |
| HU-03 | Como **responsable de cocina**, quiero consultar el stock disponible para planificar el menú del día. | El listado muestra insumo, cantidad y vencimiento. Responde en menos de 1,5 s (meta de la Entrega 2). | M | 3 | 1 |
| HU-04 | Como **voluntario**, quiero dejar constancia de una donación rechazada y su motivo para mantener la trazabilidad. | La donación queda marcada como "rechazada" con un motivo y no suma stock. | S | 2 | 2 |
| HU-05 | Como **responsable de cocina**, quiero que el sistema calcule los insumos necesarios para 100 raciones y me diga si alcanzan. | Con un menú elegido, el sistema muestra el faltante por insumo, o "stock suficiente". | M | 8 | 2 |
| HU-06 | Como **responsable de cocina**, quiero ver primero los perecederos próximos a vencer para usarlos antes. | Los insumos con vencimiento en 7 días o menos aparecen arriba y resaltados. | S | 3 | 2 |
| HU-07 | Como **responsable de cocina**, quiero registrar la ración diaria elaborada para descontar el stock y marcar si hubo faltantes. | Se crea un registro en `Racion_Diaria`. El stock baja según el menú. `Hubo_Faltantes` es verdadero si se elaboraron menos de 100 raciones. | M | 5 | 2 |
| HU-08 | Como **Dirección (pastores)**, quiero recibir una alerta cuando un insumo baja del mínimo para decidir a tiempo entre una campaña o una compra. | La alerta aparece en el panel y por correo. Indica el insumo, el stock actual y el mínimo. | M | 5 | 3 |
| HU-09 | Como **Administración y Finanzas**, quiero registrar las compras hechas con fondos para rendir cuentas de los gastos. | Cada compra suma stock y queda registrada con su monto, fecha y comprobante. | S | 5 | 3 |
| HU-10 | Como **Administración y Finanzas**, quiero emitir un comprobante de agradecimiento al donante para dar transparencia. | Se genera un comprobante por donación con fecha, detalle y número. | C | 3 | 3 |
| HU-11 | Como **Dirección**, quiero un tablero mensual con los indicadores (raciones, quiebres de stock, donaciones, mermas) para rendir cuentas ante la congregación. | El tablero muestra los indicadores del documento `control/indicadores.md` y se puede filtrar por mes. | S | 8 | 3 |

**Total:** 50 puntos, en 3 sprints alineados al Gantt de la Entrega 2:

- **Sprint 1** (09/11 – 20/11/2026): HU-01, HU-02, HU-03, con 11 pts.
- **Sprint 2** (23/11 – 03/12/2026): HU-04 a HU-07, con 18 pts.
- **Sprint 3** (04/12 – 17/12/2026, en paralelo con QA): HU-08 a HU-11, con 21 pts.

## Tareas de documentación (TPI)

Estas tareas también se cargan en el tablero, porque son el trabajo real de esta entrega:

| ID | Tarea | Rama |
|---|---|---|
| DOC-01 | Subir las Entregas 1, 2 y 3 al repositorio | `docs/entregas-previas` |
| DOC-02 | Modelar el proceso de negocio en BPMN | `feature/proceso-bpmn` |
| DOC-03 | Redactar las historias de usuario y armar el tablero | `feature/backlog` |
| DOC-04 | Definir los indicadores de control | `feature/indicadores` |
| DOC-05 | Redactar la declaración de uso de IA | `docs/uso-ia` |
| DOC-06 | Integrar el PDF final y revisar los enlaces | `docs/pdf-final` |

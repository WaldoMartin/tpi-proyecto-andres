# Mecanismos de control – Indicadores

El control cierra el ciclo administrativo: planear, organizar, dirigir y controlar. Se aplican sus cuatro pasos:

1. **Establecer estándares.** Son las metas de la Entrega 2 y la meta operativa de 100 raciones diarias.
2. **Medir el desempeño.** Los datos salen del propio sistema: `Racion_Diaria`, `Donacion` e `Insumo_Alimento`.
3. **Comparar** el resultado contra la meta.
4. **Corregir.** Cada desvío tiene un responsable, tomado del organigrama de la Entrega 3.

## A. Indicadores del proceso (funcionamiento del sistema en la organización)

| # | Indicador | Fórmula | Meta | Frecuencia | Fuente | Responsable |
|---|---|---|---|---|---|---|
| 1 | Cumplimiento de raciones | Días con 100 raciones o más ÷ días operativos × 100 | ≥ 95 % | Semanal | `Racion_Diaria.Cantidad_Producida` | Área de Producción |
| 2 | Quiebres de stock | Cantidad de días con `Hubo_Faltantes` = Verdadero | ≤ 2 por mes | Mensual | `Racion_Diaria.Hubo_Faltantes` | Dirección |
| 3 | Trazabilidad de donaciones | Donaciones registradas en el sistema ÷ donaciones recibidas × 100 | 100 % | Mensual | `Donacion` y planilla de recepción | Administración y Finanzas |
| 4 | Merma por vencimiento | Unidades vencidas ÷ unidades ingresadas × 100 | < 5 % | Mensual | `Insumo_Alimento.Fecha_Vencimiento` (*) | Área de Producción |
| 5 | Tiempo de reacción ante alertas | Horas entre la alerta de faltante y la decisión de Dirección | < 24 h | Por evento | Registro de alertas | Dirección |
| 6 | Tiempo de respuesta del sistema | Percentil 95 del tiempo de las consultas de stock | < 1,5 s | Semanal | Registro del servidor | Equipo de desarrollo |

(*) **Ajuste incorporado al diccionario de datos.** Con el campo booleano `Perecedero` no alcanza para calcular la merma ni ordenar por vencimiento. Por eso se agrega a la entidad `Insumo_Alimento` el campo **`Fecha_Vencimiento` (Date)**: la fecha en que vence el lote ingresado.

## B. Indicadores del proyecto (gestión del desarrollo)

| # | Indicador | Fórmula | Meta | Fuente |
|---|---|---|---|---|
| 7 | Cumplimiento del cronograma | Tareas del Gantt terminadas en fecha ÷ tareas planificadas × 100 | ≥ 90 % | Gantt (Entrega 2) |
| 8 | Avance del backlog | Historias en "Hecho" ÷ total de historias × 100 | 100 % al 17/12/2026 | Tablero de GitHub Projects |
| 9 | Desvío de la velocidad | Diferencia entre los puntos completados y los planificados por sprint, ÷ planificados | ≤ 20 % | Tablero (story points) |
| 10 | Integración por Pull Request | Cambios que llegaron a `main` por PR ÷ total de cambios × 100 | 100 % | Historial de GitHub |

## Acciones correctivas

| Si el desvío es… | Acción |
|---|---|
| Cumplimiento de raciones por debajo de 95 % | Dirección revisa las alertas no atendidas y organiza una campaña de donación específica. |
| Más de 2 quiebres de stock por mes | Se sube el stock mínimo de los insumos críticos. Administración evalúa compras preventivas. |
| Merma de 5 % o más | Cocina planifica el menú con los perecederos primero (HU-06) y se revisa la recepción. |
| Desvío de velocidad mayor a 20 % | Se repriorizan las historias "C" (deseables) al sprint siguiente. |

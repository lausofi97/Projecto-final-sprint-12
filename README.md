# Rappi+ | Rentabilidad, embudo, cohortes y experimento de checkout

**Autora:** Laura Sofía Arias González  
**Tipo:** Proyecto académico de análisis de datos — TripleTen  
**Herramientas:** Python · pandas · SQL · PostgreSQL · SQLAlchemy · statsmodels · Tableau

## Resumen ejecutivo

Integré limpieza de pedidos, cálculo de KPIs, consultas SQL de embudo y cohortes, una prueba A/B y un dashboard ejecutivo.

## Pregunta de negocio

¿Cómo evaluar la rentabilidad y el comportamiento de los usuarios, y existe evidencia para cambiar el checkout?

## Proceso de análisis

1. Limpieza y estandarización de pedidos, catálogo y gasto de marketing.
2. Unión many-to-one de pedidos y catálogo para estimar costos; separación de pedidos con costo conocido.
3. Cálculo de ingresos, costos y resultado parcial después de marketing.
4. Embudo SQL con usuarios presentes en las etapas previas y análisis de cohortes mensuales.
5. Prueba Z bilateral de dos proporciones para evaluar conversión de checkout.
6. Publicación de un dashboard en Tableau Public.

## Hallazgos principales

- Los ingresos de los pedidos con costo conocido fueron 9.610.018,94. Después de restar sus costos y todo el gasto de marketing, el resultado parcial fue 2.909.306,40, igual que en Tableau. Es parcial porque excluye los ingresos de pedidos sin costo conocido. La moneda no está especificada en los datos.
- Conversión del experimento: tratamiento 16,29 % y control 15,69 %, diferencia observada +0,60 puntos porcentuales.
- La prueba bilateral reporta p ≈ 0,416 con α = 0,05: no se rechaza H₀. No equivale a demostrar igualdad o ausencia de efecto.
- El embudo restringido reporta 7.796 visitantes y 3.857 compradores; exige verificar orden temporal antes de llamarlo embudo secuencial.

## Recomendación

Mantener la versión de control mientras se diseña una prueba con efecto mínimo detectable, potencia y duración definidos. Reconciliar KPIs del notebook y Tableau antes de presentar rentabilidad consolidada.

## Ver el análisis

[Notebook del proyecto](https://github.com/lausofi97/Projecto-final-sprint-12/blob/main/S12%20Estudiante_Proyecto_Final%20%283%29.ipynb)

[Dashboard en Tableau](https://public.tableau.com/app/profile/laura.sofia.arias.gonzalez/viz/ProyectoFinalbootcampDAsprint12/Dashboard1) — incluye el resultado parcial de 2.909.306,40, consistente con el notebook.

## Alcance y limitaciones

- El resultado de rentabilidad es parcial, condicionado a costos conocidos y a los gastos incluidos; no debe llamarse utilidad neta.
- El dashboard muestra cifras distintas al notebook: se requiere reconciliar filtros, cobertura y cálculo de costos.
- La consulta de embudo exige presencia en pasos anteriores, pero no verifica timestamps ni una misma sesión.
- La retención usa semana_num >= k: mide actividad desde un umbral, no retención exclusiva en cada semana.
- El filtro de cantidad < 10.000 excluye tanto 10.000 como 20.000 unidades: documentar y validar la regla.

## Reproducibilidad

1. Descarga o clona este repositorio.
2. Abre el notebook enlazado en Jupyter.
3. Instala las librerías importadas en el notebook en un entorno virtual.
4. Ajusta las rutas de los datos a tu entorno. Los datasets no están incluidos en el repositorio revisado.
5. Ejecuta todas las celdas en orden y revisa las salidas.

Los resultados anteriores se documentan a partir de las salidas guardadas del notebook; no representan una ejecución independiente de punta a punta.

La sección SQL requiere acceso autorizado a las tablas `events`, `users` y `user_activity`. Configura la conexión mediante variables de entorno; no publiques credenciales en el notebook.

## Contacto

[LinkedIn](https://www.linkedin.com/in/laura-sofia-arias) · [GitHub](https://github.com/lausofi97)

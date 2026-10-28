# Delitos por departamento en Argentina

TP5 de Python para Economistas (UNLP). Acá dejo la ficha de datos para el trabajo final.

## Ficha de datos

- **Pregunta:** quiero ver si las características de los departamentos (edades, educación, condiciones de las viviendas) se relacionan con la tasa de delitos denunciados cada 100.000 habitantes, y qué tan bien se puede predecir esa tasa.
- **Fuente (URL):**
  - Delitos: base "SNIC - Departamentos. Anual. Años 2000-2025", del Ministerio de Seguridad: https://www.argentina.gob.ar/seguridad/estadisticascriminales/bases-de-datos
  - Población y demás datos: Censo 2022 del INDEC, resultados definitivos por departamento. Voy a usar los cuadros de estructura por sexo y edad, condiciones habitacionales y educación, y el índice de privación material de los hogares: https://www.indec.gob.ar/indec/web/Nivel4-Tema-2-41-165
  - Códigos oficiales de los departamentos: Georef, documentación en https://www.argentina.gob.ar/georef
- **Método de obtención:** descarga directa del CSV del SNIC y de las planillas Excel del INDEC. También voy a usar la API Georef para los códigos oficiales, así después puedo unir todo con los mapas de la clase 6. No hace falta scraping porque hay fuente oficial.
- **Unidad de observación y período:** departamento (incluye los partidos de Buenos Aires y las comunas de CABA). Voy a trabajar con 2022 para que coincida con el Censo, aunque la base del SNIC cubre de 2000 a 2025.
- **Condiciones de uso o licencia:** son datos abiertos oficiales, sin clave y sin datos personales, porque son números agregados por departamento. Según los términos y condiciones de argentina.gob.ar, los contenidos del sitio están bajo la licencia Creative Commons Atribución 4.0, salvo que se diga otra cosa, así que voy a citar la fuente.
- **Cómo voy a verificar los datos:** que los departamentos de cada provincia sumen el total provincial, y que la población de los departamentos sume el total de cada provincia en el Censo 2022. Al unir las tablas voy a usar `LEFT JOIN` para ver qué departamentos quedan sin pareja y no perder filas sin darme cuenta. Por último, voy a recalcular la tasa cada 100.000 habitantes y compararla con la que publica el Ministerio, si está.
- **Para qué me sirve en la tesis:** me permitiría seguir con este trabajo en la materia de Machine Learning, que empiezo la semana que viene, si tengo que hacer algún trabajo práctico, y eventualmente podría ser un tema de tesis.

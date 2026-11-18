# Santiago en movimiento

Aplicación de cartografía interactiva desarrollada por **Felipe Mancilla**, geógrafo, para explorar la distribución del trabajo en el Área Metropolitana de Santiago.

[Abrir la aplicación](https://famancilla.github.io/santiago-en-movimiento/)

## Funcionalidades

- Selección de 48 comunas y comparación de los censos 2002 y 2024.
- Tres principales destinos laborales externos por comuna.
- Cantidad de personas y porcentaje respecto del total de ocupados residentes de la comuna de origen.
- Mapa de puestos de trabajo por cada 100 ocupados residentes.
- Descarga CSV y documentación metodológica dentro de la app.

## Tecnología

HTML, CSS y JavaScript; cartografía interactiva con Leaflet 1.9.4. Datos JSON locales, sin backend ni instalación para el visitante. El mapa base requiere conexión a servicios Esri.

## Fuentes

- [Visualizador de conmutación laboral del INE](https://conmutacion-laboral.ine.gob.cl/): estadísticas de los censos 2002 y 2024 y cartografía comunal.
- [Resultados Censo 2024](https://censo2024.ine.gob.cl/resultados/).
- Mapa base: Esri World Topographic Map, con atribución visible en el mapa.

Extracción original: 16 de noviembre de 2026. Esta aplicación es independiente y no constituye un producto oficial del INE. Los datos se incluyen como una copia estática; no se actualizan automáticamente.

## Método y límites

El porcentaje por destino es `100 × personas del vínculo / ocupados residentes del origen`, usando el mismo año. El denominador incluye a quienes trabajan en su comuna; no es la suma de los tres destinos ni la población total. Se redondea a un decimal; el CSV incluye cuatro decimales.

La concentración se expresa como `100 × puestos de trabajo / ocupados residentes`. Los puestos conservan la definición del visualizador del INE: ocupados no conmutantes residentes más entradas de ocupados. No son vacantes ni una tasa de empleo.

Se muestran 144 vínculos por año: tres destinos externos por cada una de las 48 comunas. No es una matriz origen-destino completa y no cubre necesariamente toda la Región Metropolitana. Algunos destinos están fuera de las 48 comunas.

Las líneas unen puntos referenciales, no rutas. Sus grosores varían con la raíz cuadrada de la cantidad de personas. La animación indica dirección, no velocidad. No se calculan tiempos, modos de transporte ni viajes diarios. Los límites se simplificaron para la visualización web. La comparación histórica sigue los datos armonizados publicados por el INE.

## Ejecutar en un computador

Desde esta carpeta, con Python instalado:

```bash
python -m http.server 8000
```

Abrir http://localhost:8000. Es necesario servir la carpeta por HTTP para cargar los JSON; abrir index.html directamente puede bloquear su lectura.

## Autoría y componentes externos

Diseño y desarrollo: Felipe Mancilla. Los datos y servicios de terceros mantienen sus respectivas condiciones de uso. Leaflet se distribuye bajo licencia BSD-2-Clause, incluida en LICENSE-Leaflet.txt. Este repositorio no concede una licencia general adicional sobre el código propio.

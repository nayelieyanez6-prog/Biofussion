# Biofussion
Monitoreo de cambios superficiales asociados a la minería aurífera mediante radar SAR en la Amazonía ecuatoriana.
# M.I.N.E.S.
### Multi-spectral Intelligence for Natural Ecosystem Surveillance

**NASA Space Apps Challenge 2026**

Español | English

---

# Español

## Descripción del proyecto

M.I.N.E.S. es una aplicación web diseñada para facilitar la exploración y comparación de cambios ambientales en la Amazonía ecuatoriana mediante imágenes satelitales y datos geoespaciales abiertos.

La plataforma permite comparar un mismo lugar en dos momentos diferentes, estimar cambios en la cobertura vegetal y cuerpos de agua, identificar zonas candidatas a verificación y consultar información relacionada con las pasadas del satélite NISAR (NASA–ISRO).

Su propósito es facilitar la identificación de posibles transformaciones del paisaje y contribuir al monitoreo ambiental mediante herramientas accesibles e interactivas.

> **Importante:** M.I.N.E.S. identifica cambios visuales entre imágenes de dos fechas. No confirma la existencia de minería legal o ilegal ni demuestra daño ambiental. Las zonas señaladas son únicamente candidatas a verificación y requieren contrastarse con otras fuentes o trabajo de campo.

## Objetivo general

Facilitar la visualización, comparación y seguimiento de posibles cambios ambientales en la Amazonía ecuatoriana mediante imágenes satelitales públicas, metadatos de pasadas NISAR y capas de contexto territorial, identificando zonas que puedan requerir una verificación posterior.

## Funcionalidades principales

- **Comparación temporal:** visualización de dos imágenes satelitales mediante paneles independientes (Antes y Después).
- **Análisis de cobertura:** estimación visual de vegetación, agua/sombra y suelo/otros.
- **Detección de cambios:** identificación de posibles transformaciones en la cobertura vegetal y cuerpos de agua.
- **Zonas candidatas a verificación:** localización de sectores que presentan cambios visuales relevantes.
- **Consulta NISAR:** visualización de metadatos, fechas de adquisición y huellas de pasadas disponibles.
- **Contexto territorial:** consulta de áreas protegidas, territorios indígenas y concesiones mineras de referencia.
- **Validación manual:** clasificación de zonas como pendientes, verificadas o descartadas.
- **Exportación de resultados:** descarga de información en formatos GeoJSON, CSV y Markdown.
- **Carga de información geográfica:** incorporación de capas propias mediante GeoJSON y shapefiles comprimidos.

## Metodología

El funcionamiento de M.I.N.E.S. se desarrolla principalmente en el navegador del usuario.

1. Se selecciona una ubicación de interés dentro de la Amazonía ecuatoriana.
2. Se eligen dos momentos temporales para comparar las imágenes.
3. Se descargan las teselas de imágenes satelitales disponibles.
4. Se realiza una clasificación visual de píxeles utilizando reglas basadas en color RGB y el índice Excess Green (ExG).
5. Se comparan las imágenes para identificar posibles transiciones entre vegetación, suelo y agua/sombra.
6. Se generan estadísticas aproximadas y zonas candidatas a verificación.
7. Se consulta información complementaria de NISAR y de las capas territoriales disponibles.
8. El usuario puede validar manualmente los resultados y exportar la información.

**Nota metodológica:** El análisis implementado utiliza el color RGB de las imágenes visualizadas. No procesa directamente bandas espectrales individuales ni imágenes de retrodispersión SAR de NISAR.

## Tecnologías utilizadas

| Tecnología | Aplicación |
|---|---|
| HTML5 | Estructura de la aplicación |
| CSS3 | Diseño e interfaz |
| JavaScript | Lógica y procesamiento |
| Leaflet 1.9.4 | Visualización de mapas |
| shpjs 4.0.4 | Lectura de shapefiles |
| Canvas 2D API | Lectura y clasificación de píxeles |
| OpenStreetMap | Información geográfica |

## Fuentes de datos

| Fuente | Información utilizada |
|---|---|
| NASA GIBS / HLS | Imágenes satelitales por fecha |
| EOX Sentinel-2 Cloudless | Mosaicos anuales de imágenes |
| NASA–ISRO NISAR | Metadatos y huellas de pasadas |
| ASF DAAC | Consulta de productos NISAR |
| OpenStreetMap | Nombres de lugares y elementos geográficos |
| Nominatim | Búsqueda y geocodificación |
| Overpass API | Consulta de información geográfica |
| CARTO | Etiquetas cartográficas |
| MAATE / SNAP | Referencias de áreas protegidas |
| RAISG | Referencias territoriales |
| ARCOM | Referencias de información minera |

## Instalación y ejecución

M.I.N.E.S. es una aplicación web estática de un solo archivo principal (`index.html`). No requiere instalar dependencias ni disponer de un servidor backend propio.

### Opción 1. Ejecutar localmente

1. Clonar el repositorio:

```bash
git clone https://github.com/USUARIO/REPOSITORIO.git
```

2. Ingresar a la carpeta:

```bash
cd REPOSITORIO
```

3. Iniciar un servidor local:

```bash
python3 -m http.server 8000
```

4. Abrir en el navegador:

```text
http://localhost:8000
```

### Opción 2. Ejecutar mediante GitHub Pages

1. Ingresar al repositorio.
2. Abrir **Settings → Pages**.
3. Seleccionar la rama `main`.
4. Seleccionar la carpeta `/ (root)`.
5. Guardar los cambios y acceder al enlace generado por GitHub Pages.

## Estructura del repositorio

```text
M.I.N.E.S/
│
├── index.html
├── README.md
├── LICENSE
└── .gitignore
```

## Limitaciones

- Los cambios identificados no demuestran actividad minera.
- La clasificación se basa en reglas de color RGB y no en índices espectrales calibrados.
- Las sombras, nubes y superficies oscuras pueden generar confusiones en la clasificación.
- NISAR se utiliza para consultar metadatos y huellas, no para procesar imágenes SAR.
- Los territorios indígenas y concesiones mineras incorporados como referencia se representan mediante puntos, no mediante límites territoriales oficiales.
- Los resultados son aproximaciones y requieren validación independiente.
- La aplicación depende de servicios externos y de una conexión a internet.
- Los resultados de validación manual no persisten después de recargar la página.

## Impacto esperado

M.I.N.E.S. busca contribuir a la vigilancia ambiental de la Amazonía ecuatoriana mediante una herramienta de exploración geoespacial accesible.

Está orientada a estudiantes, investigadores, comunidades, organizaciones ambientales y técnicos interesados en identificar posibles transformaciones del paisaje y priorizar zonas para una evaluación posterior.

---

# English

## Project description

M.I.N.E.S. is a web application designed to facilitate the exploration and comparison of environmental changes in the Ecuadorian Amazon using satellite imagery and open geospatial data.

The platform allows users to compare the same location at two different points in time, estimate changes in vegetation cover and water bodies, identify candidate areas for verification, and explore information related to NASA–ISRO NISAR satellite passes.

Its purpose is to make landscape transformations easier to explore and support environmental monitoring through accessible and interactive tools.

> **Important:** M.I.N.E.S. identifies visual changes between images from two dates. It does not confirm legal or illegal mining, nor does it prove environmental damage. Flagged areas are only candidates for verification and require independent assessment.

## General objective

To facilitate the visualization, comparison and monitoring of potential environmental changes in the Ecuadorian Amazon using public satellite imagery, NISAR pass metadata and territorial context layers, identifying areas that may require further verification.

## Main features

- **Temporal comparison:** independent Before and After satellite imagery panels.
- **Land cover analysis:** visual estimation of vegetation, water/shadow and soil/other.
- **Change detection:** identification of potential transformations in vegetation cover and water bodies.
- **Candidate verification zones:** identification of areas with relevant visual changes.
- **NISAR information:** visualization of available pass metadata, acquisition dates and footprints.
- **Territorial context:** protected areas, Indigenous territories and reference mining concessions.
- **Manual validation:** classification of candidate zones as pending, verified or discarded.
- **Data export:** GeoJSON, CSV and Markdown formats.
- **Geospatial data upload:** support for GeoJSON and zipped shapefiles.

## Methodology

The application performs its processing primarily within the user's browser.

1. Select an area of interest in the Ecuadorian Amazon.
2. Choose two temporal moments for comparison.
3. Retrieve available satellite imagery tiles.
4. Classify image pixels using RGB-based rules and the Excess Green (ExG) index.
5. Compare both images to identify potential transitions between vegetation, soil and water/shadow.
6. Generate approximate statistics and candidate verification zones.
7. Consult complementary NISAR metadata and territorial information.
8. Manually validate and export the results.

**Methodological note:** The implemented analysis uses RGB image colors. It does not directly process individual spectral bands or NISAR SAR backscatter imagery.

## Technologies

- HTML5
- CSS3
- JavaScript
- Leaflet 1.9.4
- shpjs 4.0.4
- Canvas 2D API
- OpenStreetMap

## Data sources

- NASA GIBS / HLS
- EOX Sentinel-2 Cloudless
- NASA–ISRO NISAR
- ASF DAAC
- OpenStreetMap
- Nominatim
- Overpass API
- CARTO
- MAATE / SNAP
- RAISG
- ARCOM

## Limitations

- Detected changes do not confirm mining activity.
- Classification relies on RGB color rules rather than calibrated spectral indices.
- Shadows, clouds and dark surfaces may cause classification errors.
- NISAR is used for metadata and footprint exploration, not SAR image processing.
- Reference Indigenous territories and mining concessions are represented by points, not official boundaries.
- Results are approximate and require independent validation.
- The application depends on external services and internet connectivity.
- Manual validation data is not preserved after reloading the application.

## Expected impact

M.I.N.E.S. aims to support environmental monitoring in the Ecuadorian Amazon through an accessible geospatial exploration tool.

It is intended for students, researchers, communities, environmental organizations and technical professionals interested in identifying potential landscape changes and prioritizing areas for further assessment.

---

## AI transparency / Transparencia sobre IA

The application does not use artificial intelligence or machine learning models for its image analysis. Its classification and scoring processes rely on predefined RGB-based rules and heuristic formulas.

The development team should disclose any AI assistance used during coding, debugging, design and documentation.

## Team / Equipo

**Project:** M.I.N.E.S. — Multi-spectral Intelligence for Natural Ecosystem Surveillance

**Challenge:** NASA Space Apps Challenge 2026

**Team members:** To be completed by the team.

**Repository:** To be completed.

**Application:** To be completed.

## References and acknowledgements

- [NASA Earthdata GIBS](https://www.earthdata.nasa.gov/data/tools/gibs)
- [NASA Harmonized Landsat Sentinel-2 (HLS)](https://hls.gsfc.nasa.gov/)
- [NASA–ISRO NISAR](https://nisar.jpl.nasa.gov/)
- [ASF DAAC](https://asf.alaska.edu/)
- [EOX Sentinel-2 Cloudless](https://s2maps.eu/)
- [OpenStreetMap](https://www.openstreetmap.org/copyright)
- [Leaflet](https://leafletjs.com/)
- [shpjs](https://github.com/calvinmetcalf/shapefile-js)
- [RAISG](https://www.amazoniasocioambiental.org/en/maps/)
- [ARCOM](https://www.gob.ec/arcom/tramites/emision-reporte-grafico-catastral-provincia-sector-mineria)
- [MAATE Ecuador](https://www.ambiente.gob.ec/)

## License

This project is licensed under the **Apache License 2.0**.

See the LICENSE file for details.

Third-party datasets, libraries, satellite imagery and external services remain subject to their respective licenses and terms of use.

---

*Developed for NASA Space Apps Challenge 2026.*

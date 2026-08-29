# mapa-tlacotepec

Cartografía comunitaria de Tlacotepec de Benito Juárez, Puebla, México, construida a partir de datos geoestadísticos abiertos del INEGI (AGEB) para apoyar la planeación y el trabajo de salud comunitaria.

## 📍 Contexto

Este proyecto busca mejorar el acceso a información cartográfica útil para la salud en la comunidad de Tlacotepec de Benito Juárez. Transforma datos geoestadísticos abiertos en mapas claros y localizados que pueden facilitar la planeación, la identificación de zonas y el trabajo comunitario en campo.

El objetivo es acercar información territorial pública a quienes realizan acciones de prevención, atención y promoción de la salud, especialmente en comunidades donde las herramientas cartográficas detalladas no siempre son fáciles de consultar.

## 🗺️ Cobertura

- **9 AGEBs urbanos** en 2 localidades:
  - **Cabecera** (localidad 0001): AGEBs 0094, 0183, 0198, 0200, 0215, 022A
  - **Santo Nombre** (localidad 0020): AGEBs 0268, 0338, 0342
- **~13,533 habitantes**
- **3,372 viviendas**
- **289 manzanas**

## ⚙️ Qué hace el proyecto

- Procesa cartografía geoestadística oficial del INEGI (AGEBs, manzanas, vialidades, frentes de manzana y números exteriores) para el municipio 21177, Puebla.
- Genera atlas de mapas en PDF completamente vectoriales mediante `matplotlib`, incluyendo:
  - Mapas generales por AGEB con simbología DENUE (sitios de interés público)
  - Atlas con números exteriores, indexado por sección
  - Atlas manzana por manzana
  - Versiones diferenciadas por color para facilitar la identificación de cada AGEB
- Cruza datos del **DENUE** (Directorio Estadístico Nacional de Unidades Económicas) para ubicar servicios y comercios relevantes.
- Manipula directamente los flujos de contenido de los PDF vectoriales para recolorear capas sin rasterizarlas.
- Genera documentos DOCX estructurados a partir de plantillas y datos procesados.

## 🛠️ Stack técnico

- Python para procesamiento geoespacial y manipulación de PDF
- PyMuPDF (`fitz`) para edición de contenido vectorial en PDF
- matplotlib para generación de mapas
- python-docx y manipulación XML para documentos Word
- Datos fuente: cartografía geoestadística del INEGI, DENUE y censo RESAGEBURB2020

## 📁 Estructura

```
mapa-tlacotepec/
├── README.md
├── src/
│   ├── color_replace.py       # Recoloreo de capas en PDF vectoriales
│   ├── merge_runs.py          # Utilidades para manipulación de DOCX
│   └── denue_cruce.py         # Cruce de datos DENUE con AGEBs
├── docs/
│   └── ejemplos/              # Muestras de los atlas generados
└── LICENSE
```

## 📄 Fuente de datos

- Cartografía geoestadística: [INEGI](https://www.inegi.org.mx/)
- DENUE (Directorio Estadístico Nacional de Unidades Económicas): INEGI
- Censo RESAGEBURB2020: INEGI

## Licencia

Ver [LICENSE](LICENSE). La licencia aplica al código y al procesamiento y edición cartográfica propios. Los datos originales del INEGI conservan sus respectivos términos de uso.

# CHANGELOG

## [Día 1] — Ejercicio 01
- chore: inicialización del repositorio y estructura de directorios.
- chore: creación de README.md, CHANGELOG.md y .gitignore.

## [Día 2] — Ejercicio 02
- feat: descarga del dataset raw y exploración inicial (head, tipos de datos, nulos).

## [Día 3] — Ejercicio 03
- feat: normalización de fechas, horas, ubicaciones y patentes.
- feat: eliminación de nulos relevantes y outliers.
- feat: cálculo de exceso_velocidad y exceso_velocidad_real.
- feat: guardado del dataset limpio en data/interim.

## [Día 4] — Ejercicio 04
- feat: implementación de la clase FineAnalyzer.

## [Día 5] — Ejercicio 05
- feat: generación de los 5 gráficos de análisis.

## [Día 6] — Ejercicio 06
- feat: cálculo del porcentaje de infracciones defaulteadas.

## [Día 7] — Ejercicio 07
- docs: redacción de conclusiones finales.


## Sprint 2

### [Día 1] - Ejercicio 01
- chore: cambio a la rama Sprint_2 partiendo de Sprint_1.
- feat: descarga y descompresión del dataset de imágenes en data/raw/imgs.
- chore: incorporación de .gitignore para datos crudos.
- docs: actualización del README.md al contexto del Sprint 2.

### [Día 2] - Ejercicio 02
- feat: listado de imágenes con nombre y tamaño en KB.
- feat: clasificación plates/completes por área media.
- feat: persistencia de group_images en data/interim/group_images.json.
- feat: función reutilizable mostrar_imagenes (grilla 4x2).

### [Día 3] - Ejercicio 03
- feat: conversión a escala de grises en data/interim/imgs/03_01_gray_scale.
- feat: suavizado (Gaussian blur) en data/interim/imgs/03_02_blur.
- feat: detección de bordes (Canny) en data/interim/imgs/03_03_canny.
- feat: incorporación de gray_path, blur_path y canny_path a group_images.

### [Día 4] - Ejercicio 04
- feat: extracción de patentes con easyocr (extraer_patente) y normalización.
- feat: match por SequenceMatcher con umbral 80% contra speeding_fines.csv.
- feat: dataset enriquecido en data/processed/speeding_fines_image.csv.
- feat: actualización de group_images.json con las patentes detectadas.

### [Día 5] - Ejercicio 05
- feat: métricas de cobertura imagen/multa en dataset procesado.
- feat: conteo vectorizado de imágenes OCR sin match al 80%.
- feat: multas IMPAGA con y sin imagen asociada.

### [Día 6] - Ejercicio 06
- docs: conclusiones Sprint 2 en data/Readme.md.
Día 1 (Ej 01): inicialización de Sprint_3, README y .gitignore
Día 2 (Ej 02): migración de imágenes a DVC
Día 3 (Ej 03): modelo lógico del dominio
Día 4 (Ej 04): función procesar_fila_csv
Día 5 (Ej 05): modelo relacional con SQLAlchemy
Día 6 (Ej 06): creación y poblado de la base de datos transito
Día 7 (Ej 07): consultas analíticas sobre transito
Día 8 (Ej 08): base vectorial patente_vectorial
Día 9 (Ej 09): función buscar_patente_imagen
Día 10 (Ej 10): conclusiones Sprint 3

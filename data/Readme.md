## Sprint 2 — Imágenes y datos
### Cobertura
No todas las multas del CSV interim tienen imagen asociada. El OCR
más el match al 80% (SequenceMatcher, izquierda a derecha) prioriza
por multa la mejor patente detectada, no una biyección 1:1.
### Calidad del pipeline visual
La clasificación plates/completes por área separa recortes de
patente de fotos del vehículo. Gris, blur y Canny preparan bordes;
EasyOCR sobre la imagen original es una base simple aceptable por la
consigna.
### Datos tabulares
`exceso_velocidad` (con tolerancia del 5%) define el universo de
infracciones. `estado_multa == IMPAGA` representa multas pendientes
de pago en este dataset.
### Limitaciones
OCR confunde caracteres similares (I/L, 0/O). Imágenes sin match y
multas sin imagen muestran que el enlace patente–foto es parcial.
Fechas relleno (1932-01-01) del Sprint 1 siguen afectando análisis
temporales si se mezclan sin filtrar.


## Sprint 3 — Base de datos y búsqueda vectorial

### Logros
Se migró el dataset procesado a una base relacional SQLite (`transito`)
mediante SQLAlchemy, con tablas para vehículos, radares, multas y
evidencias. Las imágenes pesadas quedaron versionadas con DVC y las
consultas analíticas permiten identificar patentes reincidentes, radares
activos y multas sin respaldo visual.

Se incorporó ChromaDB con embeddings de OpenCLIP para vincular la base
relacional con una base vectorial (`patente_vectorial`). La función
`buscar_patente_imagen` permite recuperar los datos de un vehículo a
partir de una foto por similitud, sin depender exclusivamente del OCR.

### Limitaciones
No todas las multas tienen evidencia visual (aprox. 40% del total). La
búsqueda por imagen depende de la calidad del recorte y del modelo
preentrenado; puede confundir patentes similares. Persisten fechas de
relleno del Sprint 1 que afectan análisis temporales si no se filtran.

### Aprendizajes
El Sprint 3 muestra cómo combinar POO, ORM, versionado de datos y
búsqueda semántica en un flujo reproducible. Separar modelo lógico,
modelo relacional y base vectorial facilita escalar el sistema sin
perder trazabilidad entre la foto, la multa y el vehículo.

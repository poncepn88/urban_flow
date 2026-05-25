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

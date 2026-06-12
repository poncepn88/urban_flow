# Urban Flow — Sprint 3

## Objetivo
Profesionalizar la solución persistiendo los datos en una base de datos
relacional mediante el ORM SQLAlchemy, versionando los datos binarios con DVC
y preparando una base vectorial para búsquedas por imagen.

## Introducción y contexto
Los radares urbanos de Vaalserberg generan multas por exceso de velocidad y
las cámaras asociadas registran la evidencia visual. Tras depurar los datos
(Sprint 1) y validar la evidencia visual (Sprint 2), el sistema creció en
volumen y ya no es viable trabajar únicamente con archivos CSV. En este
Sprint 3 se migra la información a una base de datos estructurada y se
versionan los binarios con DVC.

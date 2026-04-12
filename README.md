ASIGNACIÓN 3: Diseño, Normalización e Implementación de Bases de Datos 
Relacionales
Demostrar la capacidad de transformar datos no estructurados (JSON/CSV) en un modelo 
relacional óptimo mediante el proceso de normalización (1NF a 4NF/BCNF) y su 
Implementación funcional en un entorno de desarrollo profesional (Kaggle + SQLite).

FASE 1: Configuración y Entorno de Desarrollo 
1. Plataforma: Crear una cuenta en Kaggle de forma pública y generar un nuevo 
Notebook. 
2. Dataset: Agregar el dataset TMBD 5000 MOVIE DATASET (incluye 
tmdb_5000_movies.csv y tmdb_5000_credits.csv). 
3. Control de Versiones: Vincular el Notebook a un repositorio  en su cuenta GitHub. 
Se evaluará el historial de "Save Versions" para verificar el progreso incremental del 
trabajo.

FASE 2: Modelado Teórico y Diseño Relacional
1. Análisis Inicial: Leer la estructura de los archivos e identificar las columnas con 
valores múltiples (JSON). 
2. Diagrama Entidad-Relación (E/R): Diseñar el modelo conceptual en draw.io. 
3. Modelo Relacional y Normalización: Traducir el E/R a un esquema lógico. Debe 
Documentar el proceso de normalización paso a paso: 
  o 1NF: Identificación de atomicidad y eliminación de grupos repetitivos (listas 
  JSON). 
  O 2NF: Eliminación de dependencias parciales (creación de tablas 
  maestras/catálogos). 
  O 3NF: Separación de atributos que no dependen directamente de la Llave 
  Primaria, sino de otra columna. (Ejemplo: Si el País depende de la Ciudad y 
  no de la Película, la ciudad y el país deben ir a su propia tabla de 
  "Ubicaciones").  
  o BCNF / 4NF: Identificar y resolver dependencias multivaluadas 
  independientes (ej. actores vs. géneros). 
4. Entrega Visual: Importar las imágenes de los diagramas (E/R y Relacional Final) 
directamente en las celdas Markdown del Notebook. 

FASE 3: Implementación Técnica (Python & SQL)
1. ETL (Extract, Transform, Load): Usando Python y Pandas, procesar los archivos 
CSV para aplicar la normalización diseñada en la Fase 2. 
2. Generación de la BD: Crear un archivo de base de datos .db (SQLite) directamente 
en el directorio de trabajo de Kaggle. 
3. Integridad: Cargar los DataFrames normalizados a tablas SQL, asegurando la 
definición correcta de Llaves Primarias (PK) y Foráneas (FK). El código debe estar 
debidamente documentado con comentarios técnicos. 

FASE 4: Consultas y Análisis de Datos 
Realizar los siguientes scripts SQL para extraer información de la base de datos creada: 
• Búsqueda por Palabra Clave: El usuario ingresa una palabra y el sistema retorna 
una tabla (máx. 15 filas) con: Título, Género, Lenguajes, Popularidad y Cast. 
• Filtro Cronológico: El usuario ingresa un año. Mostrar películas estrenadas en ese 
año o posteriores, ordenadas ascendentemente por año y luego alfabéticamente 
por título (máx. 15 filas). 
• Métricas por Género: Obtener una tabla que posea el nombre del género, el  
número de películas y el promedio de votos por género. Filtrar solo aquellos cuya 
popularidad promedio sea mayor o igual a 6, ordenados de mayor a menor 
popularidad (máx. 10 filas). 
• Métricas por Año: Realizar el mismo análisis estadístico anterior, pero agrupado 
por año de estreno.

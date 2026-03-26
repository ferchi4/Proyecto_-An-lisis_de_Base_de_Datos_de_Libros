# **Proyecto: Análisis de Base de Datos de Libros**

Este proyecto se centra en la exploración y análisis de un mercado de aplicaciones para amantes de los libros mediante consultas SQL complejas. El análisis cubre el comportamiento de usuarios, tendencias de publicación, editoriales y autores valorados. Proporciona insights estratégicos para desarrollar una propuesta de valor enfocada en mejorar la experiencia de los usuarios en la interacción con libros digitales y físicos.

**Objetivo**

El proyecto se estructura en las siguientes fases principales:

1. **Conexión a Base de Datos:** Establecer conexión segura a la base de datos PostgreSQL remota.
2. **Exploración de Estructura:** Documentar 5 tablas principales (books, authors, publishers, ratings, reviews) y sus relaciones.
3. **Análisis de Tendencias Temporales:** Identificar patrones de publicación de libros post-2000.
4. **Análisis de Interacción de Usuarios:** Evaluar calificaciones y reseñas para determinar satisfacción lectora.
5. **Identificación de Editoriales Líderes:** Reconocer editoriales con mayor actividad en publicaciones sustanciales.
6. **Análisis de Autores:** Clasificar autores por valoración y engagement de usuarios.
7. **Propuesta Estratégica:** Sintetizar hallazgos y recomendar estrategias de producto.

**🛠️ Tecnologías Utilizadas**

* **Python:** Lenguaje principal para analyses y procesamiento de datos.
* **SQL:** Lenguaje de consultas con JOINs complejos, subconsultas y agregaciones.
* **PostgreSQL:** Base de datos relacional remota (Yandex Cloud).
* **SQLAlchemy:** ORM para conexión segura a base de datos.
* **Pandas:** Manipulación y transformación de resultados SQL en DataFrames.
* **Jupyter Notebook:** Entorno interactivo para desarrollo y documentación del análisis.

**Pasos Clave**

1. **Conexión a Base de Datos:**
   - Configuración segura de credenciales y parámetros de conexión.
   - Inicialización de engine SQLAlchemy con conexión PostgreSQL.
   - Validación de acceso a todas las tablas principales.

2. **Exploración de Estructura (5 Tablas):**
   - **books:** 1,000 registros con metadatos (ID, autor, título, páginas, fecha, editorial).
   - **authors:** 636 registros con información de autores.
   - **publishers:** 340 registros con datos de editoriales.
   - **ratings:** 6,456 registros de calificaciones numéricas de usuarios.
   - **reviews:** 2,793 registros de reseñas textuales de usuarios.

3. **Consulta 1 - Libros Post-2000:**
   - Filtro de libros por fecha de publicación posterior a 2000-01-01.
   - Identificación de 819 libros en este período (81.9% del catálogo).

4. **Consulta 2 - Análisis de Reseñas y Calificaciones:**
   - Agregación de reseñas por libro usando LEFT JOINs.
   - Cálculo de calificación promedio (AVG rating) por título.
   - Evaluación de comportamiento variado entre libros en términos de interacción.

5. **Consulta 3 - Editorial Líder por Volumen:**
   - JOIN entre publishers y books filtrado por páginas > 50.
   - Identificación de "Penguin Books" como líder con 42 libros sustanciales.

6. **Consulta 4 - Autor con Mayor Calificación:**
   - Subconsulta con HAVING para filtrar libros con ≥50 calificaciones.
   - Identificación de J.K. Rowling con calificación promedio 4.28 (máxima).

7. **Consulta 5 - Usuarios Activos y Reseñas:**
   - Subconsulta anidada para identificar usuarios con >50 calificaciones.
   - Cálculo de promedio de reseñas textuales: 24.33 por usuario activo.

**Resultados**

El análisis revela que:

- **Cobertura de Datos:** Base de datos íntegra con 1,000 libros, 636 autores y 340 editoriales.
- **Modernización Editorial:** 819 libros (81.9%) publicados post-2000, indicando catálogo actualizado.
- **Interacción de Usuarios:** 6,456 calificaciones y 2,793 reseñas indican comunidad activa y comprometida.
- **Editorial Dominante:** Penguin Books lidera con 42 libros de calidad (>50 páginas).
- **Autor Destacado:** J.K. Rowling con calificación 4.28, evidenciando alta satisfacción de lectores.
- **Usuarios Muy Activos:** 24.33 reseñas promedio de usuarios que califican frecuentemente (>50 libros).
- **Variabilidad en Popularidad:** Comportamiento desigual de libros sugiere presencia de títulos bestseller y nichos especializados.

**Recomendaciones Estratégicas**

1. **Enfoque en Contenido Premium:** Priorizar promoción de libros con calificaciones >4.0 y >100 reseñas para atraer usuarios de alto valor.
2. **Alianzas Editoriales:** Establecer acuerdos con Penguin Books y similares para garantizar flujo constante de títulos sustanciales.
3. **Gamificación de Participación:** Incentivar usuarios a escribir reseñas (actualmente 2,793 de 6,456 calificadores = 43.3% escriben reseñas).
4. **Curación por Autores Top:** Crear secciones destacadas para autores como J.K. Rowling con métricas de satisfacción comprobadas.
5. **Community Management:** Integrar usuarios ultra-activos (>50 calificaciones) como embajadores o críticos editoriales.

**Cómo Ejecutar el Proyecto**

1. Clona este repositorio en tu máquina local.
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   ```
   *(Nota: Asegúrate de reemplazar la URL con la de tu repositorio real).*

2. Configura las credenciales de conexión a la base de datos:
   - Abre el archivo `ProyectoSQL.ipynb`
   - Localiza la celda de conexión y actualiza `db_config` con tus credenciales (usuario, contraseña, host, puerto)

3. Instala las dependencias necesarias:
   ```bash
   pip install pandas sqlalchemy psycopg2 jupyter
   ```

4. Ejecuta el notebook en Jupyter Notebook:
   ```bash
   jupyter notebook ProyectoSQL.ipynb
   ```

5. Ejecuta las celdas de código en orden secuencial para:
   - Conectar a la base de datos
   - Explorar la estructura de tablas
   - Ejecutar las 5 consultas SQL principales
   - Analizar y visualizar resultados

**Notas Importantes**

- La base de datos es privada y requiere conexión segura (SSL).
- Las consultas están optimizadas para manejar miles de registros de forma eficiente.
- Los resultados son reproducibles y pueden servir de base para análisis más profundos de segmentación y machine learning.

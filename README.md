# 🎮 Dashboard de ventas de videojuegos con storytelling

Cuadro de mando interactivo sobre ventas globales de videojuegos (1980–2016), diseñado para un público no técnico.  
El objetivo es transformar un dataset de Kaggle en conclusiones claras y accionables para negocio.

---

## 📌 Descripción del proyecto

- **Ámbito:** Ventas globales de videojuegos.
- **Herramientas:** Python (Pandas, Matplotlib, Seaborn) para el análisis exploratorio de datos (EDA) y **Power BI Desktop** para el dashboard final.
- **Audiencia:** Perfiles de negocio sin conocimientos técnicos de programación o análisis de datos.

El foco del proyecto está en el storytelling con datos y en la explicación ética de las limitaciones del dataset

---

## 🗂️ Dataset

- **Origen:** Dataset público de Kaggle sobre ventas históricas de videojuegos (https://www.kaggle.com/datasets/sidtwr/videogames-sales-dataset).
- **Estructura:** Aproximadamente 16.000 registros y 16 columnas, combinando:
  - Variables categóricas: `Name`, `Platform`, `Genre`, `Publisher`, `Developer`, `Rating`.
  - Variables numéricas: ventas por región (`NA_Sales`, `EU_Sales`, `JP_Sales`, `Other_Sales`), `Global_Sales`, `Critic_Score`, `User_Score`, `Critic_Count`, `User_Count`.

El archivo CSV original se guarda localmente en la carpeta `data/` y no se versiona en Git por tamaño y cuestiones de licencia.

---

## 📊 Análisis exploratorio de datos (EDA)

Todo el EDA está documentado en `notebooks/eda.ipynb`. Actualmente incluye:

- Carga del dataset, vista de las primeras filas, estructura y tipos de datos.
- Estadísticos descriptivos de las variables numéricas clave (ventas y puntuaciones).
- Serie temporal de ventas globales por año de lanzamiento.
- Ranking de plataformas por ventas globales.
- Ranking de géneros por ventas globales.
- Matriz de correlación entre ventas globales, ventas regionales y puntuaciones de usuarios y crítica.
- Conteo y porcentaje de valores nulos por columna, con comentarios sobre la calidad de los datos.

Este análisis sirve como base para definir las métricas y gráficos que se mostrarán en el dashboard de Power BI.

---

## ⚠️ Sesgos y limitaciones del dataset

En el notebook se documentan varios problemas de gobernanza y representatividad de los datos:

- Más del 50 % de los juegos no tiene información de puntuación de usuarios ni de crítica, por lo que cualquier análisis que relacione ventas y valoraciones solo refleja una parte del catálogo, probablemente los títulos más visibles.
- Una proporción importante de registros carece de `Rating` y `Developer`, lo que limita los análisis por clasificación por edades o  estudio desarrollador.
- La serie temporal indica un pico de ventas físicas entre 2005 y 2009 y una caída  a partir de 2010, lo que sugiere que el dataset está centrado en ventas físicas históricas y no representa bien el crecimiento reciente de la distribución digital.

Estas limitaciones se explicarán de forma explícita en el dashboard, en una sección dedicada a sesgos y gobernanza de datos.

---

## 📈 Dashboard (Power BI)

El dashboard interactivo se construirá en **Power BI Desktop** y se añadirá a este repositorio como archivo `.pbix`. Incluirá, como mínimo:

- Cuatro o más gráficos interactivos con filtrado cruzado.
- Filtros básicos de segmentación (por ejemplo, año, plataforma, género y región).
- Una sección específica sobre sesgos del dataset, advertencias de uso y riesgos de tomar decisiones sin tener en cuenta estas limitaciones.

Por qué Power BI
Lo he elegido porque permite construir cuadros de mando interactivos sin necesidad de escribir código, algo clave para un público de negocio sin perfil técnico. Además, facilita el filtrado cruzado y la publicación en la nube, de forma que se pueden explorar las métricas desde un enlace web sin instalar herramientas adicionales

Cuando el informe esté publicado en la nube, se añadirá aquí el enlace público para acceso vía navegador.

---

## 📁 Estructura del repositorio

- `notebooks/` – Notebook de análisis exploratorio (`eda.ipynb`).
- `data/` – Datos en bruto en local (ignorados por Git).
- `reports/` *(pendiente de crear)* – Archivo de Power BI (`.pbix`) con el dashboard final.
- `README.md` – Descripción del proyecto, del dataset, del EDA y del dashboard.
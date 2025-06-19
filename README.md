# ML1_Project

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

First Project in MLE course series.

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         ml1-project-module and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── ml1-project-module   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes ml1-project-module a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

## Problema de Machine Learning 💻.

## Diagrama de flujo del proyecto 🔀.

## Dataset 📚.

[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-blue?logo=kaggle)](https://www.kaggle.com/datasets/asaniczka/tmdb-movies-dataset-2023-930k-movies?resource=download)

### Descripción

El TMDb (The Movie Database) es una base de datos cinematográfica exhaustiva que proporciona información sobre películas, incluyendo detalles como títulos, calificaciones, fechas de estreno, recaudación, géneros y mucho más.

Este conjunto de datos contiene una colección de 1,000,000 de películas extraídas de la base de datos de TMDB.

### Diccionario de Datos: TMDB Movies Dataset

#### Campos Principales

| Nombre del Campo            | Tipo de Dato | Descripción                                                                 | Ejemplo                                  |
|-----------------------------|--------------|-----------------------------------------------------------------------------|------------------------------------------|
| `id`                        | `int`        | Identificador único de la película en TMDb.                                 | `27205` (Inception)                     |
| `title`                     | `string`     | Título oficial de la película.                                              | `"Inception"`                           |
| `vote_average`              | `float`      | Puntuación promedio (0-10) basada en votos de usuarios.                     | `8.364`                                 |
| `vote_count`                | `int`        | Número total de votos recibidos.                                            | `34495`                                 |
| `status`                    | `string`     | Estado de lanzamiento (ej: estrenada, en producción).                       | `"Released"`                            |
| `release_date`              | `date`       | Fecha de estreno (formato ISO: `YYYY-MM-DD`).                               | `"2010-07-15"`                          |
| `revenue`                   | `int`        | Recaudación global en dólares (USD).                                        | `825532764`                             |
| `runtime`                   | `int`        | Duración en minutos.                                                        | `148`                                   |
| `adult`                     | `boolean`    | Indica si es contenido para adultos (`True`/`False`).                       | `False`                                 |
| `backdrop_path`             | `string`     | Ruta relativa a la imagen de fondo (URL parcial).                           | `"/8ZTVqvKDQ8emSGUEMjsS4yHAwrp.jpg"`    |
| `budget`                    | `int`        | Presupuesto en dólares (USD).                                               | `160000000`                             |
| `homepage`                  | `string`     | URL oficial de la película.                                                 | `"https://www.warnerbros.com/movies/inception"` |
| `imdb_id`                   | `string`     | Identificador de IMDb (formato `tt + 7-8 dígitos`).                         | `"tt1375666"`                           |
| `original_language`         | `string`     | Idioma original (código ISO 639-1 de 2 letras).                             | `"en"`                                  |
| `original_title`            | `string`     | Título original (sin traducciones).                                         | `"Inception"`                           |
| `overview`                  | `string`     | Resumen de la trama.                                                        | Texto largo descriptivo.                |
| `popularity`                | `float`      | Puntuación de popularidad calculada por TMDb (métrica interna).             | `83.952`                                |
| `poster_path`               | `string`     | Ruta relativa al póster (URL parcial).                                      | `"/oYuLEt3zVCKq57qu2F8dT7NIa6f.jpg"`    |
| `tagline`                   | `string`     | Frase promocional de la película.                                           | `"Your mind is the scene of the crime."`|
| `genres`                    | `string`     | Lista de géneros separados por comas.                                       | `"Action, Science Fiction, Adventure"`  |
| `production_companies`      | `string`     | Lista de compañías productoras separadas por comas.                         | `"Legendary Pictures, Syncopy, Warner Bros. Pictures"` |
| `production_countries`      | `string`     | Lista de países de producción separados por comas.                          | `"United Kingdom, United States of America"` |
| `spoken_languages`          | `string`     | Lista de idiomas hablados separados por comas.                              | `"English, French, Japanese, Swahili"`  |
| `keywords`                  | `string`     | Palabras clave relacionadas (temas, elementos de la trama).                 | `"rescue, mission, dream, airplane"`    |

## Observaciones Adicionales
- **Campos opcionales**: Algunos campos como `homepage` o `tagline` pueden estar vacíos (`null`).
- **Normalización**: Los campos con listas (`genres`, `production_companies`) usan comas como separadores.
- **IDs externos**: `imdb_id` permite cruzar datos con IMDb.
- **Imágenes**: `backdrop_path` y `poster_path` son rutas relativas que requieren una URL base (ej: `https://image.tmdb.org/t/p/original`).

## Model Card 📄.

## Resultados 📊.

## Conclusiones 🤔.
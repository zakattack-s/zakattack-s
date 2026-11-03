# Hi, I'm Zakaria

Data analyst based in Amsterdam, moving into data engineering.

I came to data through maps rather than computer science. My MSc thesis in Regional and Environmental Economics used QGIS and Python to measure walkability across districts in Győr, Hungary and pinpoint underserved areas. Working with messy spatial data on real planning questions got me hooked, and it's why I wanted to learn how to build the pipelines behind the analysis.

I'm new to GitHub, and this profile is where I'm putting the projects I build while I gain hands-on experience. I'm looking for a junior data engineering role in the Netherlands.

## What I work with

- **Languages:** Python, SQL, PySpark
- **Data engineering:** Spark, Databricks, Delta Lake, incremental pipelines, REST APIs, Parquet, GitHub Actions
- **Cloud:** Azure
- **Analysis:** Excel, pandas, EDA, a lot of data cleaning
- **Geospatial:** QGIS, ArcGIS, GeoPandas

## Certifications

Databricks Certified Data Engineer Associate · Azure Fundamentals (AZ-900) · AI-200 · SpikeUp AI graduate

## Project: Dutch Precipitation Data Pipeline

A self-updating pipeline and interactive map of daily rainfall across the Netherlands, built to bring my geospatial background together with the data engineering skills I'm learning.

**[Live map](https://zakattack-s.github.io/Dutch-precipitation-data-pipeline/)** · **[Code](https://github.com/zakattack-s/Dutch-precipitation-data-pipeline)**

What it does:
- Collects daily precipitation from the Open-Meteo API (ECMWF IFS model, 438 grid cells of about 8 km) and stores over 600,000 rows in Parquet
- Updates incrementally: each run fetches only the missing days, re-checks the latest few for revisions, and never leaves gaps or duplicates
- Turns the grid points into Voronoi polygons with GeoPandas and exports a compact JSON for an interactive map with a day slider
- Runs on a schedule with GitHub Actions, which updates the data and redeploys the map on GitHub Pages

What I learned:
- The API only returns the nearest model cell for a coordinate and doesn't list its grid, so I queried a grid of my own and kept the cells the API returned.
- I tried KNMI's 1 km radar data but dropped it, because it comes as large zip files that would need to be downloaded again for every update. Choosing a data source meant looking at how it's delivered, not only at its resolution.
- Running the pipeline on GitHub's servers exposed problems that never showed up on my laptop, such as connection timeouts to the API, which I fixed with retries and shorter timeouts.

I used AI as a learning aid throughout and to help build the map's HTML page. The data pipeline and the geospatial processing are the parts I focused on.

Stack: Python, pandas, GeoPandas, Parquet, GitHub Actions, GitHub Pages, Leaflet.

## Project: Albert Heijn AI Data Assistant

During the SpikeUp AI course, my team built an assistant that lets you ask questions about product and sales data in plain language and get answers back from the data.

My part:
- Built the Bronze → Silver → Gold pipeline in Spark on Databricks
- Designed the Gold tables so the assistant's queries stay simple
- Helped with the agent itself: the system prompt and the SQL execution tool

The biggest lesson: the AI is only as good as the data model underneath it. Designing the Gold tables around the questions people would actually ask made SQL generation much easier, and keeping missing-value flags in the data let the assistant explain its limits instead of presenting every answer with false confidence. Reviewing the generated SQL, not just the final answer, was the only way I caught some of the problems.

## Where I'm headed

I'm focused on building my skills in data engineering, particularly pipeline design, data quality and data modelling. I want to gain experience working with real-world data systems and learn how to build reliable, maintainable pipelines.

My background in data analysis and geospatial data gives me a different perspective on working with data, which I hope to bring into my future work as a data engineer. The precipitation pipeline is one of the projects I've built to put these skills into practice.

## Get in touch

Open to junior data engineering roles in the Netherlands.
[LinkedIn](https://www.linkedin.com/in/zakaria-suleiman-82b58a250/)

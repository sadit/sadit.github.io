+++
title = "Teaching"
hascode = true
date = Date(2023, 06, 09)
tags = ["syntax", "code"]
+++

# Cursos - teaching
\toc


## Similarity Search - Nearest Neighbor Search
Tutorial introductorio a la búsqueda de vecinos cercanos y demostraciones del uso de `SimilaritySearch.jl`. Incluye visualizaciones creadas con UMAP

<https://github.com/sadit/SimilaritySearchDemos>

## Curso introductorio a Python
Curso propedeutico a la MCDI de Infotec, es un curso remedial o tutorial introductorio a Python y al uso de algunos de sus paquetes
más utiles para ciencia de datos (pandas, matplotlib, sklearn).

- <https://github.com/INGEOTEC/prope2020>

## Recuperación de información con Julia
Curso sobre recuperación de información con Julia

- <https://github.com/sadit/IR-2022/>

## Algoritmos
Curso sobre algoritmos con un enfoque para recuperación de información

- <https://github.com/sadit/CURSO-ALGO-IR>

## Tutorial sobre similarity search
Tutorial sobre algoritmos exactos y aproximados para búsqueda métrica

- <https://sadit.github.io/similarity-search-talk-2021/>

### SimilaritySearch.jl

`SimilaritySearch.jl` is a library for nearest neighbor search. In particular, it contains the implementation for SearchGraph, a fast and flexible search index using any metric function. It is designed to support multithreading in most of its functions and structures.

The package provides the following indexes:

ParallelExhaustiveSearch: A brute force search index where each query is solved using all available threads.
ExhaustiveSearch: A brute force search index, each query is solved using a single thread.
SearchGraph: An approximate search index with parallel construction.
The main set of functions are:

| type          | description |
|---------------|-------------|
| `search`      | Solves a single query.|
| `searchbatch` | Solves a set of queries.|
| `allknn`      | Computes the nearest neighbors for all elements in an index.|
| `neardup`     | Removes near-duplicates from a metric dataset.|
| `closestpair` | Computes the closest pair in a metric dataset.|
 
**Links**
- repository: <https://github.com/sadit/SimilaritySearch.jl>.
- examples and demos: <https://sadit.github.io/SimilaritySearchDemos/> 


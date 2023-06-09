+++
title = "Software"
hascode = true
date = Date(2023, 06, 09)
tags = ["syntax", "code"]
+++

# Software packages
\toc


## Similarity Search - Nearest Neighbor Search
### `SimilaritySearch.jl`

`SimilaritySearch.jl` is a library for nearest neighbor search. In particular, it contains the implementation for SearchGraph, a fast and flexible search index using any metric function. It is designed to support multithreading in most of its functions and structures.

The package provides the following indexes:

ParallelExhaustiveSearch: A brute force search index where each query is solved using all available threads.
ExhaustiveSearch: A brute force search index, each query is solved using a single thread.
SearchGraph: An approximate search index with parallel construction.
The main set of functions are:

- `search`: Solves a single query.
- `searchbatch`: Solves a set of queries.
- `allknn`: Computes the nearest neighbors for all elements in an index.
- `neardup`: Removes near-duplicates from a metric dataset.
- `closestpair`: Computes the closest pair in a metric dataset.
 
**Links**
- repository: <https://github.com/sadit/SimilaritySearch.jl>.
- examples and demos: <https://sadit.github.io/SimilaritySearchDemos/> 

### SpatialAccessTrees.jl
Spatial access trees are a family of metric trees having excellent performance on low and medium dimensional datasets.


The package supports trading accuracy and search time strategies for spatial access trees.

**Links**
- repository: <https://github.com/sadit/SpatialAccessTrees.jl>

### InvertedFiles.jl
This package implements inverted files, also known as inverted indexes, that are data structures that represents a large sparse matrix, specially organized to compute some distance functions and fetch k nearest neighbors. It is mainly used for full text search and other search tasks where data can be formulated as large sparse vectors. In particular, the package implements three types of inverted files:

- `WeightedInvertedFile`: Inverted files for sparse vectors, it can solve nearest neighbors using the normalized cosine distance, 
- `BinaryInvertedFile`: Inverted file for sparse binary data, it can solve nearest neighbors using Jaccard, Dice, and Cosine distances, and also the intersection dissimilarity measure.
- `KnrIndex`: An approximated similarity search index based on inverted files. It supports general metric spaces.

These structs integrates with the SimilaritySearch `environment`, such that you can use it as a drop-in replacement of other indexes. In particular, inverted files are well-known for its scalability when the proper setup is used.

**Links**

- repository: <https://github.com/sadit/InvertedFiles.jl>

### TextSearch.jl
`TextSearch.jl` is a package to create vector representations of text and seach them, mostly, independently of the language.
It provides the following concepts:

- `TextConfig`: Defines preprocessing pipelines.
- `Vocabulary`: Text vocabularies.
- `VectorModel`: Text vectorizers (sparse vectors) using global and local weighting schemes.
- `BM25InvertedFile`: A full text inverted files using the BM25 score. 

It is intended to be used with `SimilaritySearch.jl` and with the `InvertedFiles` package. The `BM25InvertedFile` allows searching without using other packages.

**Links**
- repository: <https://github.com/sadit/TextSearch.jl>

## Optimization
### SearchModels.jl

Provides a generic tool for minimizing model errors using stochastic search,
which is often used whenever the problem has no concept of derivative.
This kind of problems rely on large exploration of combinatorial spaces based on error function.

It is the core for auto-tuning, and optimization in discrete domains, of other packages.

**Links**
- repository: <https://github.com/sadit/SearchModels.jl>


## Text classification, search and clustering
- [EvoMSA] A Multilingual Evolutionary Approach for Sentiment Analysis.
  - <https://github.com/INGEOTEC/EvoMSA>.
- [$\mu$TC] An automated text categorization framework based on hyperparameter optimization}
  - <https://github.com/INGEOTEC/microtc>.
- [B4MSA] A Simple Approach to Multilingual Polarity Classification in Twitter.
  -  <https://github.com/INGEOTEC/b4msa>.
- [TextSearch.jl] A package for creating text models and full-text indexes for the Julia language.
  - <https://github.com/sadit/TextSearch.jl>.
- [TextClassification.jl] A package for creating text classifiers based on full model selection.
  - <https://github.com/sadit/TextClassification.jl>.
- [SnowballStemmer.jl] A wrapper for the _libstemmer_ library.
  - <https://github.com/sadit/SnowballStemmer.jl>.

## K centers problem and non-linear dimension reduction

- [KCenters.jl] A package that implements some algorithms for solving the K centers problem that integrates with `SimilaritySearch`.
  - <https://github.com/sadit/KCenters.jl>.
- [SimSearchManifoldLearning.jl] A package that implements the UMAP algorithm for computing non-linear dimensional projections. It uses the `SimilaritySearch` package for speeding up the construction of the $k$nn graph and predictions. It also implements the necessary methods to use `SimilaritySearch` with external manifold learning methods, like those defined in the `ManifoldLearning` package.
  - <https://github.com/sadit/SimSearchManifoldLearning.jl>.


+++
title = "Software"
hascode = true
date = Date(2023, 06, 09)
tags = ["syntax", "code"]
+++

# Software packages
\toc


## Similarity Search - Nearest Neighbor Search
### SimilaritySearch.jl

`SimilaritySearch.jl` is a library for nearest neighbor search. In particular, it contains the implementation for SearchGraph, a fast and flexible search index using any metric function. It is designed to support multithreading in most of its functions and structures.

The package provides the following indexes:

ParallelExhaustiveSearch: A brute force search index where each query is solved using all available threads.
ExhaustiveSearch: A brute force search index, each query is solved using a single thread.
SearchGraph: An approximate search index with parallel construction.
The main set of functions are:

| type | description |
|------|-------------|
| `search` | Solves a single query.|
| `searchbatch` | Solves a set of queries.|
| `allknn` | Computes the nearest neighbors for all elements in an index.|
| `neardup` | Removes near-duplicates from a metric dataset.|
| `closestpair` | Computes the closest pair in a metric dataset.|
 
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

| type | description |
|------|-------------|
| `WeightedInvertedFile` | Inverted files for sparse vectors, it can solve nearest neighbors using the normalized cosine distance, |
| `BinaryInvertedFile` | Inverted file for sparse binary data, it can solve nearest neighbors using Jaccard, Dice, and Cosine distances, and also the intersection dissimilarity measure.|
| `KnrIndex` | An approximated similarity search index based on inverted files. It supports general metric spaces.|

These structs integrates with the SimilaritySearch `environment`, such that you can use it as a drop-in replacement of other indexes. In particular, inverted files are well-known for its scalability when the proper setup is used.

**Links**

- repository: <https://github.com/sadit/InvertedFiles.jl>

### SlicedSearch.jl: Turbo Scan
Implements an innovative $k$-nearest neighbor search solution, Turbo Scan (TS), specifically designed to address the challenges associated with high-dimensionality data and rare workloads where building indexes cannot be effectively amortized over time. We recognize numerous scenarios where the overhead of constructing an index cannot be justified due to the limited number of queries performed on the dataset.

**Links**
- repository: <https://github.com/sadit/SlicedSearch.jl>

### TextSearch.jl
`TextSearch.jl` is a package to create vector representations of text and seach them, mostly, independently of the language.
It provides the following concepts:

| type       | description |
|------------|-------------|
| `TextConfig` | Defines preprocessing pipelines. |
| `Vocabulary` | Text vocabularies. |
| `VectorModel` | Text vectorizers (sparse vectors) using global and local weighting schemes|
| `BM25InvertedFile` | A full text inverted files using the BM25 score |

It is intended to be used with `SimilaritySearch.jl` and with the `InvertedFiles` package. The `BM25InvertedFile` allows searching without using other packages.

**Links**
- repository: <https://github.com/sadit/TextSearch.jl>


## Text classification


### EvoMSA

A Multilingual Evolutionary Approach for Sentiment Analysis.

**Links**
- repository: <https://github.com/INGEOTEC/EvoMSA>.
- documentation: <https://evomsa.readthedocs.io/en/docs/>

### MicroTC 
$\mu$TC is an automated text categorization framework based on hyperparameter optimization 

**Links**

https://github.com/INGEOTEC/microtc>.

### B4MSA
A Simple Approach to Multilingual Polarity Classification in Twitter

**Links**
- repository: <https://github.com/INGEOTEC/b4msa>
- documentation: <https://evomsa.readthedocs.io/en/docs/>

### TextClassification.jl

A Julia package for creating text classifiers based on full model selection, mostly based on MicroTC.

**Links**
- repository: <https://evomsa.readthedocs.io/en/docs/>


## Others
### SearchModels.jl (optimization)

Provides a generic tool for minimizing model errors using stochastic search,
which is often used whenever the problem has no concept of derivative.
This kind of problems rely on large exploration of combinatorial spaces based on error function.

It is the core for auto-tuning, and optimization in discrete domains, of other packages.

**Links**
- repository: <https://github.com/sadit/SearchModels.jl>

### KCenters.jl (k centers and clustering)
A package that implements some algorithms for solving the K centers problem that integrates with `SimilaritySearch`.

**Links**
- repository: <https://github.com/sadit/KCenters.jl>.

### SimSearchManifoldLearning.jl (non-linear dimensional reduction)
A package that implements the UMAP algorithm for computing non-linear dimensional projections. It uses the `SimilaritySearch` package for speeding up the construction of the $k$nn graph and predictions. It also implements the necessary methods to use `SimilaritySearch` with external manifold learning methods, like those defined in the `ManifoldLearning` package.

**Links**
- repository: <https://github.com/sadit/SimSearchManifoldLearning.jl>.

### LevelDB.jl (key-value database)
A leveldb wrapper, forked from `LevelDB.jl` package. This version has new key and value types, prefix-driven fetches, and use of newer leveldb through `LevelDB_jll` (a `BinaryBuilder`-based binary, also created with this purpose).

Submitted for merging in original `LevelDB.jl`

**Links**
- repository: <https://github.com/sadit/LevelDB.jl>

### SnowballStemmer.jl (stemmer)
A wrapper for the _libstemmer_ library, extrated from [`TextAnalysis`](https://github.com/JuliaText/TextAnalysis.jl/). _Unmantained._

**Links**
- repository: <https://github.com/sadit/SnowballStemmer.jl>.

### BILMA
Bert in Latinamerica. A set of language models (BERT-based with Keras) for regional spanish models.

**Links**
- <https://github.com/msubrayada/bilma>

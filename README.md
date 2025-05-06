# storyviz-data-sparql-lab <!-- omit from toc -->

## Notebooks analysing data storytelling practices, data visualisation, and SPARQL proficiency <!-- omit from toc -->

This repository contains a collection of Jupyter notebooks developed as part of an ongoing research project focused on data storytelling in the context of the Semantic Web. The work explores how data visualisation, narrative structures, and SPARQL querying skills intersect to support both the creation and interpretation of data-driven stories.

## Table of Contents <!-- omit from toc -->

- [Objectives](#objectives)
- [Objectives](#objectives-1)
- [Contents](#contents)
  - [`data_stories_summary.json`](#data_stories_summaryjson)
  - [`semantic_web_storytelling_analysis.ipynb`](#semantic_web_storytelling_analysisipynb)
  - [`data_stories.ipynb` (messy and old)](#data_storiesipynb-messy-and-old)
  - [`quality_correlation.ipynb`](#quality_correlationipynb)
- [Evolved Framework for Assessing Data Story Quality](#evolved-framework-for-assessing-data-story-quality)
  - [`readability.ipynb`](#readabilityipynb)
  - [`coherence.ipynb`](#coherenceipynb)
  - [`info_density.ipynb`](#info_densityipynb)
  - [`good_structure.ipynb`](#good_structureipynb)
  - [`viz_number.ipynb`](#viz_numberipynb)

## Objectives

- Analyse the structure and components of data stories created using Semantic Web technologies.
- Investigate the role of SPARQL queries in shaping visual and narrative outputs.
- Explore the potential of data storytelling as a tool for fostering data and Semantic Web literacy.


## Objectives

- Analyse the structure and components of data stories created using Semantic Web technologies.
- Investigate the role of SPARQL queries in shaping visual and narrative outputs.
- Explore the potential of data storytelling as a tool for fostering data and Semantic Web literacy.

## Contents

### `data_stories_summary.json`

A structured summary of multiple data stories created by students using SPARQL and Wikidata. Each entry includes:
- The **title** of the story  
- The **SPARQL endpoint** used (mostly Wikidata)  
- (The **authors and curators** have been exclulded for anonomity)
- The **sequence and types** of elements (e.g. text, visualisations, counts, searches)  
- The **types of visualisations** used (bar charts, doughnut charts, tables, maps, etc.)  
- The **SPARQL queries** themselves  
- The **narrative texts** associated with each story

This file serves as a foundational dataset for evaluating user approaches to query design, visualisation strategy, and narrative structuring in educational or exploratory settings.

### `semantic_web_storytelling_analysis.ipynb`

A published notebook that supports the analysis presented in a paper on Semantic Web storytelling. It includes:
- Quantitative analysis of story structure and components  
- Categorisation of SPARQL queries and their roles in narratives  
- Visualisation patterns and their narrative functions  
- Preliminary conclusions on user proficiency and storytelling strategies  

### `data_stories.ipynb` (messy and old)

An early, exploratory notebook that served as the starting point for the project. It contains:
- Initial parsing and inspection of data story components  
- Manual observations and hypothesis formation  
- Unstructured experimentation with SPARQL queries, visual elements, and JSON structure  
- Basis for more structured analyses in later notebooks

### `quality_correlation.ipynb`

A notebook exploring initial correlations between structural and technical features of data stories and their perceived quality. It includes:
- Feature extraction from each story (e.g. number and type of components, query characteristics)
- Quality assessment based on:
  1. Text ratio within a 40%–60% target range  
  2. No more than 3 consecutive chart-based components  
  3. Alignment between visualisation types and query logic  
  4. Presence of federated queries  
  5. Variety and sophistication of SPARQL features used  
- Preliminary correlation analysis to identify potential predictors of quality

*Note: the approach to assessing data story quality has evolved — see later notebooks for updates.*

## Evolved Framework for Assessing Data Story Quality

Since the initial correlation-based analysis did not yield clear results, the notion of "data story quality" has been restructured around three distinct, measurable dimensions. Each is implemented in a dedicated notebook:

### `readability.ipynb`

Assesses textual readability using the **Flesch Reading Ease** score (via the [`textstat`](https://pypi.org/project/textstat/) library). The notebook:
- Applies the readability metric to all text blocks within each story
- Aggregates scores to derive story-level readability
- Identifies overly complex or overly simplistic stories

### `coherence.ipynb`

Measures coherence using **sentence embeddings** from **SBERT (Sentence-BERT)** via the `sentence-transformers` library. The method:
- Embeds all consecutive text blocks in a story
- Computes cosine similarity between sentence pairs
- Uses the **mean pairwise similarity** to quantify narrative coherence

### `info_density.ipynb`

Evaluates how densely packed with information each story is by combining:
- **TF-IDF weighting** applied to all text content
- Both **per-token** and **per-sentence** scores
- A hybrid metric that accounts for quantity *and* concentration of informative content

This shift from binary heuristics to continuous metrics enables more nuanced, scalable evaluations of storytelling quality.

### `good_structure.ipynb`

Evaluates the structural flow of data stories based on the **alternation and variety of elements**. This notebook:
- Analyses the sequencing of component types (e.g. text, data visualisations, counts)
- Detects long uninterrupted blocks of similar types (e.g. multiple charts without explanation)
- Flags stories that lack a balanced alternation between narrative and data-driven elements
- Supports the identification of structurally engaging story formats

### `viz_number.ipynb`

Simple analysis of the **number of visualisations** used in each data story.

## License <!-- omit from toc -->

This repository is released under the MIT License. See the `LICENSE` file for details.


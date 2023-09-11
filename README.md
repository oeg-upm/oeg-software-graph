# oeg-software-graph
[![Project Status: Concept – Minimal or no implementation has been done yet, or the repository is only intended to be a limited example, demo, or proof-of-concept.](https://www.repostatus.org/badges/latest/concept.svg)](https://www.repostatus.org/#concept) [![DOI](https://zenodo.org/badge/659343054.svg)](https://zenodo.org/badge/latestdoi/659343054) [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/oeg-upm/oeg-software-graph/HEAD?labpath=notebooks%2Fkg-construction.ipynb)

## Description

This repository contains the resources used to build a knowledge graph containing the catalog of software from the oeg-upm organization in GitHub (last execution June, 2023). The source data is generated with the SOftware Metadata Extraction Framework ([SOMEF](https://github.com/KnowledgeCaptureAndDiscovery/somef)), which extracts the relevant information of a repository from README files and saves it as JSON files. Then, a knowledge graph that relies on the Software Description Ontology ([SDO](https://w3id.org/okn/o/sd)) is created using [RML-star](http://w3id.org/rml/star/spec/) mappings. The resulting knowledge graph is then queried to assess the adoption of a set of representative best practices for research software publishing.

**Disclaimer:** this repository is a demonstration, accepted at the 2023 Semantics Conference.  

<img width="928" alt="Screenshot 2023-07-04 at 18 44 15" src="https://github.com/oeg-upm/oeg-software-graph/assets/36294992/69f693f5-9aa8-4891-bdb9-8b1a2114626b">

## Structure

This repository is organized as follows:
* `data/` contains the input JSON file aggregating the metadata extracted of all repositories from the oeg-upm GitHub organisation (`somef.json`), along with the produced knowledge graph (`somef-kg.nq`)
* `mappings/` contains the RML-star mappings needed to construct the knowledge graph from the JSON file
* `notebooks/` contains two notebooks, for i) the generation of the JSON files and ii) construction and querying of the knowledge graph
* `best-practices-requirements/` describes the set of representative best practices that are assessed in the repositories represented in the knowledge graph

## Installation
This pipeline has been tested in `Python 3.9`.

In order to run the pipeline, you need to install [Jupyter Notebooks](https://jupyter.org/install):

```
pip install notebook
```

Then, install the requirements of the project. Creating two separate environments is highly recommended (one for extraction, another one for querying), since the libraries used for extracting metadata and creating the knowledge graph have varied dependencies. For installing the extraction requirements, run: 

```
pip install -r requirements_extraction.txt
```

For installing the construction and querying requirements, run 
```
pip install -r requirements.txt
```

Finally, start Jupyter notebook and run the notebooks in the `notebooks` folder. 

### Requirements: 

Our pipeline makes use of the `somef`, `yatter`, `morph-kgc` and `pyoxigraph` packages. For more information about the versions used, see the [requirements.txt](./requirements.txt) file (construction and querying) and [requirements_extraction.txt](./requirements_extraction.txt) (which will install `somef`).

If you want to play around with SPARQL queries, just run the construction and querying [notebook](./notebooks/kg-construction.ipynb), which will guide you through the KG creation and querying process.

Click in the Binder button [![Binder](https://mybinder.org/badge_logo.svg)](https://hub.ovh2.mybinder.org/user/oeg-upm-oeg-software-graph-cue4mx2q/lab/workspaces/auto-o/tree/notebooks/kg-construction.ipynb) to show a pre-loaded notebook for testing (it may take a few minutes to load).

## Citation
If you use this work, please cite our software as follows:

```bibtex
@software{ana_iglesias_2023_8114677,
  author       = {Ana Iglesias-Molina and
                  Daniel Garijo},
  title        = {oeg-upm/oeg-software-graph: v1.0.0},
  month        = jul,
  year         = 2023,
  publisher    = {Zenodo},
  version      = {v1.0.0},
  doi          = {10.5281/zenodo.8114677},
  url          = {https://doi.org/10.5281/zenodo.8114677}
}
```


## Authors
* [Ana Iglesias-Molina](https://github.com/anaigmo) ([ana.iglesiasm@upm.es](mailto:ana.iglesiasm@upm.es))
* [Daniel Garijo](https://github.com/dgarijo) ([daniel.garijo@upm.es](mailto:daniel.garijo@upm.es))

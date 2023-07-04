# oeg-software-graph
[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

## Description

This repository contain the resources to build a knowledge graph containing the catalog of software from the oeg-upm organization in GitHub. The source data is generated with the SOftware Metadata Extraction Framework ([SOMEF](https://github.com/KnowledgeCaptureAndDiscovery/somef)), which extracts the relevant information of a repository from README files and saves it as JSON files. Then, a knowledge graph that relies on the Software Description Ontology ([SDO](https://w3id.org/okn/o/sd)) is created using [RML-star](http://w3id.org/rml/star/spec/) mappings. The resulting knowledge graph is then queried to assess the adoption of a set of representative best practices for research software publishing.

<img width="928" alt="Screenshot 2023-07-04 at 18 44 15" src="https://github.com/oeg-upm/oeg-software-graph/assets/36294992/69f693f5-9aa8-4891-bdb9-8b1a2114626b">

## Structure

This repository is organized as follows:
* `data/` contains the input JSON file aggregating the metadata extracted of all repositories from the oeg-upm GitHub organisation (`somef.json`), along with the produced knowledge graph (`somef-kg.nq`)
* `mappings/` contains the RML-star mappings needed to construct the knowledge graph from the JSON file
* `notebooks/` contains two notebooks, for i) the generation of the JSON files and ii) construction and querying of the knowledge graph
* `best-practices-requirements/` describes the set of representative best practices that are assessed in the repositories represented in the knowledge graph

## Authors
* [Ana Iglesias-Molina](https://github.com/anaigmo) ([ana.iglesiasm@upm.es](mailto:ana.iglesiasm@upm.es))
* [Daniel Garijo](https://github.com/dgarijo) ([dgarijo@fi.upm.es](mailto:dgarijo@fi.upm.es))

# HIDDENdb
 
**Harnessing Intelligent Data Discovery to Explore Gene Networks**
 
HIDDENdb is a database of genetic and protein co-dependencies inferred from genome-wide loss-of-function screens. For any human gene, it reports the genes whose fitness profiles covary with it across cancer cell lines, annotated with supporting evidence from interaction, phenotype and localisation resources.
 
Genes required by the same cell lines, and dispensable in the same cell lines, frequently act together within a complex, a pathway, or a shared process. HIDDENdb quantifies this relationship for every gene pair across three independent perturbation screens.
 
**Application:** https://bofillderoslab.shinyapps.io/hiddendb/
**Documentation:** [Wiki](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki)
 
---
 
## Features
 
- Co-dependency scores for all gene pairs across the Achilles, Sanger and shRNA datasets, standardised as Z-scores
- Cross-dataset comparison for assessment of reproducibility
- Chromosome-wide visualisation of co-dependency distributions
- Interactive network exploration of first-degree neighbours and shared partners
- Annotation with BioGRID, BioGRID ORCS, GWAS Catalog, OpenCell and MitoCarta3.0
- Export of tables, plots and networks for downstream analysis
## Data sources
 
| Dataset | Release | Genes | Cell lines |
|---|---|---|---|
| Achilles CRISPR | DepMap Public 20Q4 | 18,119 | 800 |
| Sanger CRISPR | Sanger DepMap, 2021 | 17,995 | 324 |
| shRNA (DEMETER2) | DepMap RNAi, 2017 | 7,735 | 395 |
| Gene expression | DepMap Public 24Q2 | 19,193 | 1,516 |
 
Annotation and benchmarking layers: BioGRID, BioGRID ORCS, NHGRI-EBI GWAS Catalog, OpenCell, Gene Ontology, MitoCarta3.0 and AlphaFold3 interface predictions.
 
HIDDENdb is built on fixed dataset releases rather than live queries. Scores do not change when DepMap publishes new quarterly releases and may differ from values obtained from the current DepMap portal.
 
## Documentation
 
| Topic | Page |
|---|---|
| Worked example and first query | [Getting started](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Getting-started) |
| Tabs, controls and visual encodings | [Interface guide](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Interface-guide) |
| Datasets, releases and versions | [Data sources](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Data-sources) |
| Derivation of Z-scores and connectivity | [How scores are computed](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/How-scores-are-computed) |
| Confidence thresholds and known artefacts | [Interpreting results](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Interpreting-results) |
| Column and variable definitions | [Data dictionary](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Data-dictionary) |
 
## Running locally
 
The application is implemented in R using Shiny.
 
```r
# install.packages("remotes")
remotes::install_deps()
 
shiny::runApp()
```
 
Processed co-dependency tables are required at runtime and are not distributed with this repository owing to their size. See **Data availability** below.
 
## Data availability
 
Processed co-dependency matrices and the annotated feature tables are available at [DEPOSIT LOCATION]. Primary dependency data may be obtained from the DepMap portal (https://depmap.org) and the Sanger DepMap portal (https://depmap.sanger.ac.uk) under the releases listed above.
 
## Interpretation
 
A co-dependency is a statistical association between fitness profiles and does not by itself constitute evidence of physical interaction; the majority reflect pathway-level rather than direct relationships. The database retains known systematic artefacts, principally those arising from chromosomal proximity and from the coordinated regulation of mitochondrial genes. These are annotated and identifiable in the interface but are not removed. Guidance is provided in [Interpreting results](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Interpreting-results).
 
## Citation
 
If HIDDENdb contributes to published work, please cite:
 
> De Silva, I., Bandu, S.P., Kidmose, R.T., Maseras, G.T., Bataillon, T., Bofill-De Ros, X. (2026). HIDDENdb: Co-dependency database reveals a plethora of genetic and protein interactions. *arXiv* 2603.06903. https://arxiv.org/abs/2603.06903
 
Please also cite the primary data sources on which a given result depends. These are listed in [Citing and contact](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/wiki/Citing-and-contact).
 
## Contributing
 
Bug reports and feature requests may be submitted through [Issues](https://github.com/Bofill-De-Ros-Lab/HIDDENdb/issues).
 
## Funding
 
Lundbeck Foundation (R368-2021-428) and Direktør Michael Hermann Nielsens mindelegat (2024-0093141). I.D.S. was supported by the Ranganatha Rajagopal Scholarship. Computation was carried out on the EMCC cluster (https://emcc.au.dk).
 
## Licence
 
Code is released under the MIT Licence (see `LICENSE`).
 
Processed co-dependency data are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), consistent with the licence of the underlying DepMap datasets. Annotation layers derived from BioGRID, BioGRID ORCS, the GWAS Catalog, OpenCell, Gene Ontology and MitoCarta3.0 remain subject to the terms of those resources, which should be consulted before redistribution.
 
## Contact
 
Xavier Bofill-De Ros — xavier.bofill@sund.ku.dk
[RNA Metabolism and Therapeutics Lab](https://www.drug.ku.dk/RNAtx), Aarhus University and University of Copenhagen
 

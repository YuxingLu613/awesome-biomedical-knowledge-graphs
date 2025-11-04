# Awesome Biomedical Knowledge Graphs

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
![](https://img.shields.io/github/last-commit/YuxingLu613/awesome-biological-knowledge-graphs?color=green)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Welcome to the Awesome Biomedical Knowledge Graphs repository! This project aims to curate and share resources related to Biomedical Knowledge Graphs (BKGs), a powerful tool for organizing and analyzing biological data. Whether you are a researcher, developer, or enthusiast in the field of biology or data science, this repository is a valuable resource for you.

## Citation

If you find this repository useful, please consider citing our survey paper:

**Biomedical Knowledge Graph: A Survey of Domains, Tasks, and Real-World Applications**
Yuxing Lu, Sin Yee Goi, Xukai Zhao, Jinzhuo Wang
arXiv:2501.11632, 2025
[[Paper]](https://arxiv.org/pdf/2501.11632)

```bibtex
@article{lu2025biomedical,
  title={Biomedical Knowledge Graph: A Survey of Domains, Tasks, and Real-World Applications},
  author={Lu, Yuxing and Goi, Sin Yee and Zhao, Xukai and Wang, Jinzhuo},
  journal={arXiv preprint arXiv:2501.11632},
  year={2025}
}
```

## News

**2025/1/22**: Our survey paper "Biomedical Knowledge Graph: A Survey of Domains, Tasks, and Real-World Applications" is now available on arXiv!

**2024/9/5**: This project is actively under development.

Feel free to **STAR** and **WATCH** to stay updated with our progress.

## Overview

Biomedical knowledge graphs (BKGs) have emerged as powerful tools for organizing and leveraging the vast and complex data found across the biomedical field. This survey addresses the gap in existing reviews by offering a systematic review of BKGs from three core perspectives: **domains**, **tasks**, and **applications**.

### Key Contributions

1. **Domain-Focused Classification**: Detailed classification of BKGs based on their underlying data sources, ranging from multi-omics to pharmacology and clinical data
2. **BKG Tasks Illustration**: Examination of key tasks BKGs support, including knowledge management, retrieval, reasoning, and interpretation
3. **Real-World Applications**: Showcase of transformative potential of BKGs in precision medicine, drug discovery, and scientific research
4. **Emerging Trends and Future Directions**: Analysis of current limitations and discussion of how recent technological breakthroughs (e.g., LLMs and multi-omics integration) might shape the field

## Table of Contents

- [Background](#background)
  - [Definition](#definition)
  - [Construction Workflow](#construction-workflow)
  - [Knowledge Graph Representation Methods](#knowledge-graph-representation-methods)
- [Domains](#domains)
  - [Multi-omics](#multi-omics)
  - [Pharmacology](#pharmacology)
  - [Medical](#medical)
  - [Multi-domain](#multi-domain)
- [Tasks](#tasks)
  - [Knowledge Management](#knowledge-management)
  - [Knowledge Retrieval](#knowledge-retrieval)
  - [Knowledge Reasoning](#knowledge-reasoning)
  - [Knowledge Interpretation](#knowledge-interpretation)
- [Applications](#applications)
  - [Information Retrieval](#information-retrieval)
  - [Clinical Decision Support](#clinical-decision-support)
  - [Intelligent Question Answering](#intelligent-question-answering)
  - [Drug Discovery](#drug-discovery)
  - [Scientific Research](#scientific-research)
  - [Others](#other-applications)
- [Resources](#resources)
  - [Biomedical Databases](#biomedical-databases)
  - [Existing BKGs](#existing-bkgs)
  - [KG Tools](#kg-tools)
- [Limitations](#limitations)
- [Trends and Opportunities](#trends-and-opportunities)
- [Related Surveys](#related-surveys)

## Background

### Definition

A BKG is a structured framework designed to represent entities and their relationships within the biomedical domain. Formally, a BKG is defined as **G = (E, R, F)**, where:
- **E** is the set of entities
- **R** is the set of relations
- **F ⊆ E × R × E** is the set of factual triples

Each triple (h, r, t) ∈ F consists of:
- A head entity h ∈ E
- A relation r ∈ R
- A tail entity t ∈ E

Representing facts such as "Gene encodes Protein" or "Drug targets Disease."

### Construction Workflow

The construction of a BKG is a multi-step process requiring careful design and validation:

1. **Data Acquisition and Preprocessing**
   - Collection from structured databases, semi-structured repositories, and unstructured text
   - Preprocessing involves noise reduction, normalization, and deduplication

2. **Relationship Extraction and Integration**
   - Relations extracted using rule-based systems, machine learning models, or advanced NLP techniques
   - Integration process aligns entities and relations across datasets using ontology matching

3. **Graph Validation and Storage**
   - Enforcement of integrity constraints (e.g., type compatibility for relations)
   - Storage in graph databases with support for querying using SPARQL or Cypher

### Knowledge Graph Representation Methods

#### Translational Models
Models like TransE, TransH, TransD, and TransR embed entities and relations into ℝ^d and enforce translational consistency: **h + r ≈ t**

#### Semantic Matching Models
Models like DistMult and RESCAL decompose the adjacency tensor of the graph, uncovering intricate interaction patterns.

#### Graph Neural Networks
GNNs (GCNs, GATs) leverage graph topology to learn context-aware embeddings by aggregating information from neighboring nodes.

#### Embedding in Non-Euclidean Spaces
Approaches like RotatE model relations as rotations in complex vector space, particularly effective for capturing hierarchical and cyclic patterns.

## Domains

BKGs are classified into three primary domains: **multi-omics**, **pharmacology**, and **medical**. The intersection of all three domains constitutes a multi-domain BKG.

### Multi-omics

Multi-omics BKGs integrate one or more omics data types to enable comprehensive biological analysis:

#### Genome
- Model relationships between genomic entities to investigate disease mechanisms
- Examples: GenomicKB, GenomicsKG

#### Transcriptome
- Include all RNA molecules transcribed from the genome
- Examples: RNA-KG (miRNA-lncRNA associations)

#### Proteome
- Focus on protein structure, function, and interactions
- Examples: ProteinKG25, IDP-KG (intrinsically disordered proteins)

### Pharmacology

Pharmacological BKGs focus on drug-disease associations and drug-target interactions:

#### Pharmacodynamics and Pharmacokinetics
- Model drug-disease associations (DDAs) and drug-target interactions (DTIs)
- Examples: IPM-KG (drug pathways), DrugMechDB, OREGANO KG (natural compounds)

#### Toxicology
- Model adverse drug reactions (ADRs) and drug-drug interactions (DDIs)
- Examples: DDI prediction frameworks, drug interaction KGs

### Medical

Medical BKGs integrate healthcare-related information:

#### Medical Knowledge
- Encompasses medical concepts, terminologies, and theories
- Examples: Disease-specific KGs (SDKG-11, KGHC for hepatocellular carcinoma)

#### Clinical Data
- Real-world patient information from EMRs and EHRs
- Includes patient registries, laboratory results, and medical images

### Multi-domain

Multi-domain BKGs represent the intersection of multi-omics, pharmacology, and medical domains:

- **General BKGs**: Broad spectrum of biological data (e.g., Hetionet, PharmKG, PrimeKG)
- **Specific BKGs**: Focus on particular diseases or biological pathways (e.g., COVID-19 KGs, Alzheimer's disease KG)

## Tasks

BKGs enable diverse biomedical applications through four essential tasks:

### Knowledge Management

Collecting, organizing, and storing data through three sub-tasks:

#### Organization
- Structuring raw data, particularly unstructured text from literatures and patient registries
- Examples: SemKG (PubMed mining), COVID-19 multi-modal KG

#### Transformation
- Converting heterogeneous structured data into standardized formats
- Examples: Phosphorylation KG, EHR-oriented KG

#### Integration
- Merging knowledge from multiple sources into a single BKG
- Examples: Hetionet (29 databases), CKG (clinical proteomics)

### Knowledge Retrieval

Enabling direct information acquisition through four sub-tasks:

#### Data Visualization
- Demonstration of subgraphs or meta-paths for specific entities
- Examples: GenomicsKG (poly-omics visualization), CVD Atlas KG

#### Statistical Analysis
- Revealing patterns like disease distribution and clinical significance
- Examples: CKG (clinical proteomics statistics), CTKG (statistical methods)

#### Knowledge Identification
- Discovering existing yet unutilized opportunities
- Examples: Literature-based discovery (LBD), treatment path retrieval

#### Knowledge Enhancement
- Leveraging BKG as external knowledge source for intelligent applications
- Examples: Medical diagnosis systems, biomedical LLMs (DRAGON, OntoProtein)

### Knowledge Reasoning

Drawing conclusions or generating new knowledge through two approaches:

#### Inference
- **Rule-based**: Predefined paths, entity similarity, clustered patterns
- **Probabilistic**: Probability computations for hypotheses

#### Prediction
- **Rule-based**: Statistical analysis and ML algorithms
- **Embedding-based**: Translational models, semantic matching, GNN models

### Knowledge Interpretation

Providing explanation by backtracking through the reasoning process:

#### Logical Explanation
- In-KG interpretation displaying reasoning process within graph topology
- Examples: Explanatory paths, triple sets or subgraphs

#### Assisted Interpretation
- Out-of-KG interpretation translating reasoning to text using LLMs
- Examples: Graph-to-text generation, RAG workflows

## Applications

### Information Retrieval

#### Patient Registry Acquisition
- Managing cancer registry data, personal health records
- Examples: Cancer KG, PHR KG, AI chronic disease management

#### Biomedical Knowledge Acquisition
- Cross-domain knowledge access
- Examples: Hetionet, PharmKG, PrimeKG, GenomicKB

#### Literature Retrieval
- Accessing biomedical studies and author information
- Example: PubMed KG (PKG)

### Clinical Decision Support

#### Diagnostic Support
- Detecting biosignals and symptoms
- Examples: Chest X-ray classification, radiology report generation

#### Healthcare Prediction
- Predicting future health information and medication recommendations
- Examples: KAME, PREMIER, GAMENet

### Intelligent Question Answering

#### Knowledge Source
- Supporting answer generation and query interpretation
- Examples: DRAGON, DKDR (disease diagnosis)

#### Prediction Validation
- Probing and validating knowledge in language models
- Example: BIOLAMA benchmark

### Drug Discovery

#### Drug Repurposing
- Identifying potential drug candidates through DTI and DDA modeling
- Examples: TxGNN, COVID-19 drug candidate prediction

#### ADR Analysis
- Analyzing drug-drug interactions and adverse reactions
- Examples: ADR detection, antitumor drug ADR prediction

### Scientific Research

#### Hypotheses Generation
- Generating high-potential hypotheses for biomedical research
- Examples: Cancer biomarker discovery, pathology exploration

#### Research Opportunities Identification
- Highlighting existing underutilized opportunities
- Examples: CKG (alternative treatments), cancer registry insights

### Other Applications

- **Health Management**: Dietary KGs, nutrition-mental health associations
- **Relation Extraction**: Biomedical entity relationship identification
- **Medical Education**: Personalized learning platforms (SIDES, OntoSIDES)

## Resources

### Biomedical Databases

#### Omics Databases
- **KEGG**: Genes, proteins, pathways
- **PharmGKB**: Genes, proteins, drugs, diseases, pathways
- **Ensembl**: Genes, transcripts
- **UniProtKB**: Proteins, genes, chemicals, drugs, diseases, pathways
- **STRING**: Protein-protein interactions
- **Reactome**: Genes, proteins, diseases, pathways
- **WikiPathways**: Genes, proteins, diseases, pathways
- **Gene Ontology (GO)**: Genes, proteins, diseases, pathways

#### Pharmacology Databases
- **PubChem**: Chemicals
- **ChEMBL**: Proteins, chemicals, drugs, diseases
- **DrugBank**: Genes, chemicals, drugs, pathways
- **DrugCentral**: Chemicals, drugs, diseases
- **CTD**: Genes, proteins, chemicals, drugs, diseases, pathways
- **BindingDB**: Proteins, chemicals, drugs
- **SIDER**: Chemicals, drugs, side effects
- **TWOSIDES**: Drugs, side effects

#### Medical Databases
- **DISEASES**: Genes, diseases
- **DECIPHER**: Genes, diseases
- **MIMIC-IV**: Clinical data
- **SemMedDB**: Genes, diseases
- **UMLS**: Medical concepts
- **Disease Ontology (DO)**: Diseases
- **MeSH**: Genes, proteins, diseases
- **SNOMED CT**: Diseases
- **Human Phenotype Ontology (HPO)**: Diseases

### Existing BKGs

#### Multi-Domain BKGs
| BKG | Data Sources | Entity Types | Relation Types | Entities | Relations | KGE |
|-----|-------------|--------------|----------------|----------|-----------|-----|
| PharmKG | OMIM, PharmGKB, ... (6) | 3 | 29 | 7,601 | 500,958 | ✓ |
| PrimeKG | CTD, SIDER, ... (20) | 10 | 30 | 129,375 | 4,050,249 | ✓ |
| Hetionet | ChEMBL, BindingDB, ... (29) | 11 | 24 | 47,031 | 2,250,197 | ✗ |
| DRKG | DrugBank, IntAct, ... (6) | 13 | 107 | 97,238 | 5,874,261 | ✓ |
| TarKG | MESH, Hetionet, ... | 15 | 171 | 1,143,313 | 32,806,467 | ✓ |
| SPOKE | ChEMBL, DrugBank, ... (30+) | 20+ | 55 | 500,000+ | 30,000,000+ | ✓ |
| RTX-KG2 | UniProtKB, ChEMBL, ... (70+) | 61 | 72 | 6,400,000+ | 39,000,000+ | ✗ |
| OpenBioLink | GO, UBERON, ... (15) | 5 | 28 | 184,732 | 4,563,405 | ✓ |
| BioKG | DrugBank, IntAct, ... (5) | 5 | 51 | 105,524 | 2,084,382 | ✓ |
| ROBOKOP | ChEMBL, CTD, ... (20+) | 20+ | 100+ | 3,000,000+ | 30,000,000+ | ✗ |

#### Omics BKGs
| BKG | Focus | Data Sources | KGE |
|-----|-------|-------------|-----|
| GenomicKB | Genome | GENCODE, GO, ... | ✗ |
| GenomicsKG | Cancer genomics | TCGA, COSMIC, ... | ✗ |
| RNA-KG | RNA interactions | HPO, MONDO, ... | ✓ |
| ProteinKG65 | Protein | UniProt, GO, ... | ✗ |
| ProteinKG25 | Protein | UniProt, Reactome, ... | ✓ |
| IDP-KG | Intrinsically disordered proteins | DisProt, STRING, ... | ✓ |
| PathwayKG | Biological pathways | KEGG, Reactome, WikiPathways | ✓ |
| MetaKG | Metabolomics | HMDB, MetaCyc, KEGG | ✓ |
| miRKG | microRNA | miRBase, miRTarBase, ... | ✓ |
| BioGRID | Protein-protein interactions | Manual curation, high-throughput | ✗ |

#### Pharmacology BKGs
| BKG | Focus | Data Sources | KGE |
|-----|-------|-------------|-----|
| DrugMechDB | Drug mechanisms | DrugBank, UniProt, ... | ✗ |
| OREGANO | Natural compounds | PharmGKB, SIDER, ... (8) | ✓ |
| IPM-KG | Drug pathways | DrugBank, CTD, ... (4) | ✓ |
| TTD | Therapeutic targets | Manual curation, UniProt, ... | ✗ |
| SIDER-KG | Drug side effects | SIDER, UMLS, ... | ✓ |
| ADRKNet | Adverse drug reactions | FDA Adverse Event, DrugBank | ✓ |
| Drug-Target Commons | Drug-target interactions | ChEMBL, BindingDB, ... | ✓ |
| PharmKG-i2b2 | Clinical pharmacology | i2b2, DrugBank, ... | ✓ |
| KGDRP | Drug discovery | Multiple drug databases | ✓ |

#### Medical BKGs
| BKG | Focus | Data Sources | KGE |
|-----|-------|-------------|-----|
| CKG | Clinical proteomics | UniProt, DISEASES, ... (25) | ✗ |
| CTKG | Clinical trials | AACT | ✓ |
| SDKG-11 | 11 diseases | MirBase, ChEMBI, ... (7) | ✓ |
| KGHC | Hepatocellular carcinoma | SemMedDB, PubMed, ... | ✓ |
| COVID-19-KG | COVID-19 | CORD-19, CTD, UniProt, ... | ✓ |
| PKG | PubMed literature | PubMed, UMLS, ... | ✗ |
| EHR-KG | Electronic health records | MIMIC-IV, OMOP, ... | ✓ |
| Alzheimer-KG | Alzheimer's disease | OMIM, DisGeNET, ... | ✓ |
| MIMIC-KG | Intensive care | MIMIC-III, UMLS, ... | ✓ |
| Cancer-KG | Cancer | TCGA, COSMIC, OncoKB, ... | ✓ |
| DiseaseKG | Disease mechanisms | OMIM, DO, HPO, ... | ✓ |

### KG Tools

#### Graph Databases
- **Neo4J**: Graph database management system
- **ArangoDB**: Multi-modal graph database with analysis and visualization

#### Construction Tools
- **PheKnowLator**: Semantic ecosystem with KG construction resources
- **Neo4j LLM Knowledge Graph Builder**: Online text-to-graph conversion
- **KGTK**: Library for various KG operations

#### Extraction Tools
- **SemaRep**: Semantic relations extraction from biomedical text
- **TNNT**: NLP-NER toolkit for entity extraction
- **DeepKE**: Deep-learning based extraction toolkit

#### Analysis Tools
- **PBG**: Graph embeddings for large graphs
- **graph-tool**: Python module for graph manipulation and analysis
- **NetworkX**: Python package for network analysis

## Limitations

### Data Integration
- Data heterogeneity across structural, semantic, and qualitative dimensions
- Lack of standardized data collection protocols
- Challenges in harmonizing data while maintaining integrity

### Semantic Ambiguity and Standardization
- Multiple naming conventions for biological entities
- Context-dependent interpretations
- Inconsistent usage of ontologies across research communities

### Scalability
- Computational complexity of graph queries
- Growing storage requirements
- Performance bottlenecks in real-time processing

### Interpretability
- Challenges in understanding derived relationships
- Difficulty navigating complex network structures
- Lack of intuitive visualization tools

## Trends and Opportunities

### Current Trends
- **Multi-omics Integration**: Incorporating diverse omics data for comprehensive biological analysis
- **Multimodal Representations**: Including medical imaging, clinical notes, molecular structures
- **Large Language Models**: Automated knowledge extraction, entity recognition, relationship mapping

### Emerging Opportunities
- **Accelerated Research**: Novel connection identification, drug target prediction, disease mechanism understanding
- **Drug Discovery**: Efficient candidate identification, drug-target interaction analysis, side effect recognition
- **Clinical Settings**: Context-aware decision support, personalized treatment planning, outcome prediction

## Related Surveys

- **Biomedical Knowledge Graph: A Survey of Domains, Tasks, and Real-World Applications** (arXiv, 2025) [[paper]](https://arxiv.org/pdf/2501.11632) - *This repository's accompanying survey paper*
- Biological applications of knowledge graph embedding models (Brief. Bioinformatics, 2021) [[paper]](https://academic.oup.com/bib/article-pdf/22/2/1679/36654277/bbaa012.pdf)
- A Survey on Knowledge Graphs for Healthcare: Resources, Applications, and Promises (arXiv, 2023) [[paper]](https://arxiv.org/pdf/2306.04802.pdf)
- Constructing knowledge graphs and their biomedical applications (CSBJ, 2020) [[paper]](https://www.sciencedirect.com/science/article/pii/S2001037020302804/pdfft?md5=d48e7270883ec9984fbe0eb51a166eeb&pid=1-s2.0-S2001037020302804-main.pdf)

## Contributing

We welcome contributions from the community! Please feel free to:
- Submit pull requests to add new resources
- Report issues or suggest improvements
- Share your BKG-related projects

## License

This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

## Contact

For questions or collaborations, please contact:
- Jinzhuo Wang: wangjinzhuo@pku.edu.cn

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

## Referenced Papers

This section contains all 196 papers referenced in our survey, organized by topic for easy navigation.

### Knowledge Graph Foundations & Embeddings

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 12 | A Survey on Knowledge Graphs: Representation, Acquisition, and Applications | Ji, S., et al. | 2022 | IEEE Trans Neural Netw Learn Syst |
| 13 | A Survey on Knowledge Graph Embedding | Yan, Q., et al. | 2022 | DSC |
| 14 | Knowledge Graphs: Opportunities and Challenges | Peng, C., et al. | 2023 | Artif Intell Rev |
| 15 | A Comprehensive Survey on Automatic Knowledge Graph Construction | Zhong, L., et al. | 2023 | ACM Comput Surv |
| 21 | Knowledge Graph Embedding for Link Prediction | Rossi, A., et al. | 2021 | ACM TKDD |
| 23 | Adversarial Explanations for Knowledge Graph Embeddings | Patrick Betz, C.M., et al. | 2022 | IJCAI |
| 24 | Translating embeddings for modeling multi-relational data | Bordes, A., et al. | 2013 | NeurIPS |
| 25 | Knowledge graph embedding by translating on hyperplanes | Wang, Z., et al. | 2014 | AAAI |
| 26 | Knowledge graph embedding via dynamic mapping matrix | Ji, G., et al. | 2015 | ACL |
| 27 | Learning entity and relation embeddings for knowledge graph completion | Lin, Y., et al. | 2015 | AAAI |
| 28 | Embedding Entities and Relations for Learning and Inference in Knowledge Bases | Yang, B., et al. | 2014 | ICLR |
| 29 | A three-way model for collective learning on multi-relational data | Nickel, M., et al. | 2011 | ICML |
| 32 | Rotate: Knowledge graph embedding by relational rotation in complex space | Sun, Z., et al. | 2019 | arXiv |
| 47 | A review: Knowledge reasoning over knowledge graph | Chen, X., et al. | 2020 | Expert Syst Appl |
| 145 | Knowledge Graph Completion: A Review | Chen, Z., et al. | 2020 | IEEE Access |
| 146 | A Review of Knowledge Graph Completion | Zamini, M., et al. | 2022 | Information |
| 155 | Complex Embeddings for Simple Link Prediction | Trouillon, T., et al. | 2016 | arXiv |

### Biomedical Knowledge Graphs - Construction & Methods

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 1 | A knowledge graph to interpret clinical proteomics data | Santos, A., et al. | 2022 | Nat Biotechnol |
| 2 | Towards electronic health record-based medical knowledge graph construction, completion, and applications | Murali, L., et al. | 2023 | J Biomed Inform |
| 3 | Big data application in biomedical research and health care | Luo, J., et al. | 2016 | Biomed Inform Insights |
| 4 | Network embedding in biomedical data science | Su, C., et al. | 2020 | Brief Bioinform |
| 5 | Knowledge-Based Biomedical Data Science | Callahan, T.J., et al. | 2020 | Annu Rev Biomed Data Sci |
| 8 | Constructing knowledge graphs and their biomedical applications | Nicholson, D.N., et al. | 2020 | Comput Struct Biotechnol J |
| 9 | Toward better drug discovery with knowledge graph | Zeng, X., et al. | 2022 | Curr Opin Struct Biol |
| 10 | Medical Knowledge Graph: Data Sources, Construction, Reasoning, and Applications | Wu, X., et al. | 2023 | Big Data Min Anal |
| 11 | A Survey on Knowledge Graphs for Healthcare | Cui, H., et al. | 2023 | arXiv |
| 22 | Biological applications of knowledge graph embedding models | Mohamed, S.K., et al. | 2021 | Brief Bioinform |
| 34 | Multi-Modal Knowledge Graph Construction and Application: A Survey | Zhu, X., et al. | 2024 | IEEE TKDE |
| 35 | A Systematic Review on Knowledge Graphs Classification and Their Various Usages | Mst. Mim, A., et al. | 2023 | Artif Intell Evol |
| 37 | Graph representation learning in biomedicine and healthcare | Li, M.M., et al. | 2022 | Nat Biomed Eng |
| 40 | Individualized Knowledge Graph: A Viable Informatics Path to Precision Medicine | Ping, P., et al. | 2017 | Circ Res |
| 45 | Large-scale knowledge graph representations of disease processes | Hoch, M., et al. | 2024 | Curr Opin Syst Biol |
| 104 | Semantic Health Knowledge Graph | Shi, L., et al. | 2017 | Biomed Res Int |
| 112 | Building a knowledge graph to enable precision medicine | Chandak, P., et al. | 2023 | Sci Data |

### Relation Extraction & NLP

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 16 | RECON: Relation Extraction using Knowledge Graph Context in a Graph Neural Network | Bastos, A., et al. | 2021 | WWW |
| 17 | Incorporating medical knowledge in BERT for clinical relation extraction | Roy, A., et al. | 2021 | Conference |
| 18 | A hybrid model based on neural networks for biomedical relation extraction | Zhang, Y., et al. | 2018 | J Biomed Inform |
| 19 | Broad-coverage biomedical relation extraction with SemRep | Kilicoglu, H., et al. | 2020 | BMC Bioinformatics |
| 20 | Biomedical Relation Extraction With Knowledge Graph-Based Recommendations | Sousa, D., et al. | 2022 | IEEE J Biomed Health Inform |
| 187 | KGBReF | Sun, Y., et al. | 2021 | ISME |
| 188 | Learning to Leverage High-Order Medical Knowledge Graph for Joint Entity and Relation Extraction | Yang, Z., et al. | 2023 | Conference |
| 189 | GREG: A Global Level Relation Extraction with Knowledge Graph Embedding | Kim, K., et al. | 2020 | Appl Sci |

### Large Language Models & Knowledge Graphs

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 6 | Unifying Large Language Models and Knowledge Graphs: A Roadmap | Pan, S., et al. | 2024 | IEEE TKDE |
| 7 | Enhancing multimodal knowledge graph representation learning through triple contrastive learning | Lu, Y., et al. | 2024 | IJCAI |
| 48 | Knowledge Graph Large Language Model (KG-LLM) for Link Prediction | Shu, D., et al. | 2024 | Conference |
| 49 | A framework for human evaluation of large language models in healthcare | Tam, T.Y.C., et al. | 2024 | NPJ Digit Med |
| 50 | The future landscape of large language models in medicine | Clusmann, J., et al. | 2023 | Commun Med |
| 51 | The application of large language models in medicine | Meng, X., et al. | 2024 | iScience |
| 136 | Biomedical knowledge graph-optimized prompt generation for large language models | Soman, K., et al. | 2024 | Bioinformatics |
| 137 | Phenomics Assistant: An Interface for LLM-based Biomedical Knowledge Graph Exploration | O'Neil, S.T., et al. | 2024 | bioRxiv |
| 154 | FuseLinker: Leveraging LLM's pre-trained text embeddings and domain knowledge | Xiao, Y., et al. | 2024 | J Biomed Inform |
| 156 | Explainable Biomedical Hypothesis Generation via Retrieval Augmented Generation | Pelletier, A., et al. | 2024 | Conference |
| 157 | Medical Graph RAG | Wu, J., et al. | 2024 | arXiv |
| 165 | ClinicalRAG: Enhancing Clinical Decision Support through Heterogeneous Knowledge Retrieval | Lu, Y., et al. | 2024 | Workshop |
| 166 | Rag and rau: A survey on retrieval-augmented language model | Hu, Y., et al. | 2024 | arXiv |
| 167 | ClinicalRAG: Enhancing Clinical Decision Support through Heterogeneous Knowledge Retrieval | Lu, Y., et al. | 2024 | Workshop |
| 173 | An Enhanced Prompt-Based LLM Reasoning Scheme via Knowledge Graph-Integrated Collaboration | Li, Y., et al. | 2024 | ICANN |
| 174 | Knowledge-graph-based explainable AI | Rajabi, E., et al. | 2024 | J Inf Sci |
| 175 | KRAGEN: a knowledge graph-enhanced RAG framework | Matsumoto, N., et al. | 2024 | Bioinformatics |
| 176 | Knowledge Graphs as Context Sources for LLM-Based Explanations | Abu-Rasheed, H., et al. | 2024 | EDUCON |
| 177 | Cross-Data Knowledge Graph Construction for LLM-enabled Educational QA System | Bui, T., et al. | 2024 | ACM Workshop |
| 178 | Can Language Models be Biomedical Knowledge Bases? | Sung, M., et al. | 2021 | arXiv |
| 180 | Benchmarking Biomedical Relation Knowledge in Large Language Models | Zhang, F., et al. | 2024 | BIBE |

### Multi-omics & Genomics

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 52 | GenomicKB: a knowledge graph for the human genome | Feng, F., et al. | 2023 | Nucleic Acids Res |
| 53 | GenomicsKG: A Knowledge Graph to Visualize Poly-Omics Data | Jha, A., et al. | 2019 | J Adv Health |
| 54 | An ontology-based knowledge graph for representing interactions involving RNA molecules | Cavalleri, E., et al. | 2024 | Sci Data |
| 55 | Knowledge graph construction based on granulosa cells transcriptome | Liu, W., et al. | 2024 | J Ovarian Res |
| 56 | miRNA-Disease Association Prediction with Collaborative Matrix Factorization | Shen, Z., et al. | 2017 | Complexity |
| 57 | A Meta-Graph for the Construction of an RNA-Centered Knowledge Graph | Cavalleri, E., et al. | 2023 | IWBBIO |
| 58 | Metastatic Site Prediction in Breast Cancer using Omics Knowledge Graph | Jha, A., et al. | 2020 | bioRxiv |
| 59 | OntoProtein: Protein Pretraining With Gene Ontology Embedding | Zhang, N., et al. | 2022 | arXiv |
| 60 | Machine learning prediction and tau-based screening identifies potential Alzheimer's disease genes | Binder, J., et al. | 2022 | Commun Biol |
| 61 | Creating and Exploiting the Intrinsically Disordered Protein Knowledge Graph (IDP-KG) | Gray, A.J.G., et al. | 2022 | SWAT4HCLS |
| 62 | Accurate prediction of kinase-substrate networks using knowledge graphs | Novacek, V., et al. | 2020 | PLoS Comput Biol |
| 63 | Multi-Modal Protein Knowledge Graph Construction and Applications | Cheng, S., et al. | 2023 | AAAI |
| 94 | A knowledge graph approach to predict and interpret disease-causing gene interactions | Renaux, A., et al. | 2023 | BMC Bioinformatics |
| 140 | GOProteinGNN: Leveraging Protein Knowledge Graphs for Protein Representation Learning | Kalifa, D., et al. | 2024 | arXiv |

### Pharmacology & Drug Discovery

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 36 | MKGE: Knowledge graph embedding with molecular structure information | Zhang, Y., et al. | 2022 | Comput Biol Chem |
| 39 | Prediction of drug-drug interaction events using graph neural networks | Al-Rabeah, M.H., et al. | 2022 | Sci Rep |
| 41 | Explainable drug repurposing via path based knowledge graph completion | Jimenez, A., et al. | 2024 | Sci Rep |
| 42 | Discovering protein drug targets using knowledge graph embeddings | Mohamed, S.K., et al. | 2020 | Bioinformatics |
| 43 | Neural Multi-hop Reasoning with Logical Rules on Biomedical Knowledge Graphs | Liu, Y., et al. | 2021 | Semantic Web |
| 44 | Explainable Biomedical Recommendations via Reinforcement Learning Reasoning | Edwards, G.P., et al. | 2021 | arXiv |
| 64 | FORUM: building a Knowledge Graph from public databases | Delmas, M., et al. | 2021 | Bioinformatics |
| 65 | Predicting the effects of drugs using IPM-KG | Tanaka, T., et al. | 2025 | Comput Biol Med |
| 66 | DrugMechDB: A Curated Database of Drug Mechanisms | Gonzalez-Cavazos, A.C., et al. | 2023 | Sci Data |
| 67 | Drug repurposing for COVID-19 via knowledge graph completion | Zhang, R., et al. | 2021 | J Biomed Inform |
| 68 | Biological Insights Knowledge Graph | Geleta, D., et al. | 2021 | bioRxiv |
| 69 | KG-Predict: A knowledge graph computational framework for drug repurposing | Gao, Z., et al. | 2022 | J Biomed Inform |
| 70 | The OREGANO knowledge graph for computational drug repurposing | Boudin, M., et al. | 2023 | Sci Data |
| 71 | Transporter proteins knowledge graph construction | Chen, X.H., et al. | 2023 | Comput Struct Biotechnol J |
| 72 | MegaKG: Toward an explainable knowledge graph for early drug development | Dong, J., et al. | 2024 | bioRxiv |
| 73 | Knowledge-driven drug repurposing using a comprehensive drug knowledge graph | Zhu, Y., et al. | 2020 | Health Inform J |
| 74 | Mining on Alzheimer's diseases related knowledge graph | Nian, Y., et al. | 2022 | BMC Bioinformatics |
| 75 | Large-scale structural and textual similarity-based mining for drug-drug interactions | Abdelaziz, I., et al. | 2017 | J Web Semant |
| 76 | Knowledge graph prediction of unknown adverse drug reactions | Bean, D.M., et al. | 2017 | Sci Rep |
| 77 | Drugomics: Knowledge Graph & AI to Construct Physicians' Brain Digital Twin | Talukder, A.K., et al. | 2022 | Big Data Anal |
| 78 | Drug-Drug Interaction Prediction Based on Knowledge Graph Embeddings | Karim, M.R., et al. | 2019 | ACM BCB |
| 79 | Prediction of adverse drug reactions based on knowledge graph embedding | Zhang, F., et al. | 2021 | BMC Med Inform Decis Mak |
| 95 | Medical knowledge graph question answering for drug-drug interaction prediction | Gao, P., et al. | 2024 | CAAI Trans Intell Technol |
| 114 | Advancing drug-target interaction prediction | Djeddi, W.E., et al. | 2023 | BMC Bioinformatics |
| 115 | Injecting domain knowledge into graph neural networks | Balbi, L., et al. | 2024 | Conference |
| 116 | A foundation model for clinician-centered drug repurposing | Huang, K., et al. | 2024 | Nat Med |
| 119 | COVID-19 Knowledge Graph | Domingo-Fernandez, D., et al. | 2021 | Bioinformatics |
| 141 | KnowLife: A knowledge graph for health and life sciences | Ernst, P., et al. | 2014 | ICDE |
| 142 | Finding melanoma drugs through a probabilistic knowledge graph | McCusker, J.P., et al. | 2017 | PeerJ Comput Sci |
| 152 | DPDDI: a deep predictor for drug-drug interactions | Feng, Y.H., et al. | 2020 | BMC Bioinformatics |
| 153 | A probabilistic knowledge graph for target identification | Liu, C., et al. | 2024 | PLoS Comput Biol |
| 179 | From Large Language Models to Knowledge Graphs for Biomarker Discovery | Karim, M.R., et al. | 2023 | arXiv |
| 182 | A unified drug-target interaction prediction framework | Ye, Q., et al. | 2021 | Nat Commun |
| 183 | Adverse Drug Reaction Discovery Using a Tumor-Biomarker Knowledge Graph | Wang, M., et al. | 2020 | Front Genet |
| 184 | Integrating knowledge graphs into machine learning for survival prediction | Fang, C., et al. | 2024 | J Transl Med |
| 185 | A Biomedical Knowledge Graph for Biomarker Discovery in Cancer | Karim, M.R., et al. | 2023 | arXiv |
| 195 | Drkg-drug repurposing knowledge graph for covid-19 | Ioannidis, V.N., et al. | 2020 | arXiv |
| 196 | Design Considerations for a Knowledge Graph: The WATRIMed Use Case | Some, B.M.J., et al. | 2019 | Stud Health Technol Inform |

### Medical & Clinical Applications

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 31 | Pay attention to doctor-patient dialogues | Zheng, W., et al. | 2021 | Inf Fusion |
| 33 | Enhancing ophthalmology medical record management with multi-modal knowledge graphs | Gao, W., et al. | 2024 | Sci Rep |
| 38 | Molecular-evaluated and explainable drug repurposing for COVID-19 | Islam, M.K., et al. | 2023 | Sci Rep |
| 46 | Inference of Biomedical Relations Among Chemicals, Genes, Diseases, and Symptoms | Choi, W., et al. | 2019 | IEEE Access |
| 81 | A knowledge graph based question answering method for medical domain | Huang, X., et al. | 2021 | PeerJ Comput Sci |
| 82 | EHR-Oriented Knowledge Graph System | Shang, Y., et al. | 2021 | IEEE J Biomed Health Inform |
| 83 | SMR: Medical Knowledge Graph Embedding for Safe Medicine Recommendation | Gong, F., et al. | 2021 | Big Data Res |
| 84 | Multimodal reasoning based on knowledge graph embedding for specific diseases | Zhu, C., et al. | 2022 | Bioinformatics |
| 85 | KGHC: a knowledge graph for hepatocellular carcinoma | Li, N., et al. | 2020 | BMC Med Inform Decis Mak |
| 86 | Constructing Knowledge Graphs of Depression | Huang, Z., et al. | 2017 | HIS |
| 87 | Kame | Ma, F., et al. | 2018 | CIKM |
| 88 | Medical Knowledge Graph to Enhance Fraud, Waste, and Abuse Detection | Sun, H., et al. | 2020 | JMIR Med Inform |
| 89 | A global network of biomedical relationships derived from text | Percha, B., et al. | 2018 | Bioinformatics |
| 90 | Learning a Health Knowledge Graph from Electronic Medical Records | Rotmensch, M., et al. | 2017 | Sci Rep |
| 91 | A knowledge graph of clinical trials | Chen, Z., et al. | 2022 | Sci Rep |
| 92 | Towards a Knowledge Graph of Health Evolution | Morales Tirado, A.C., et al. | 2022 | EKAW |
| 93 | Construction of a knowledge graph for diabetes complications | Wang, L., et al. | 2020 | Comput Assist Surg |
| 96 | COVID-19 Knowledge Graph for Drug and Vaccine Development | Huang, L., et al. | 2021 | BIBM |
| 97 | PharmKG: a dedicated knowledge graph benchmark | Zheng, S., et al. | 2021 | Brief Bioinform |
| 98 | TarKG: a comprehensive biomedical knowledge graph for target discovery | Zhou, C., et al. | 2024 | Bioinformatics |
| 99 | Systematic integration of biomedical knowledge prioritizes drugs for repurposing | Himmelstein, D.S., et al. | 2017 | Elife |
| 100 | BioKG | Walsh, B., et al. | 2020 | CIKM |
| 101 | An integrative knowledge graph for rare diseases | Zhu, Q., et al. | 2020 | J Biomed Semantics |
| 102 | Knowledge Graphs of Kawasaki Disease | Huang, Z., et al. | 2021 | Health Inf Sci Syst |
| 103 | SemaTyP: a knowledge graph based literature mining method | Sang, S., et al. | 2018 | BMC Bioinformatics |
| 105 | A Literature-Based Knowledge Graph Embedding Method | Sosa, D.N., et al. | 2020 | Pac Symp Biocomput |
| 106 | The Unified Medical Language System (UMLS) | Bodenreider, O. | 2004 | Nucleic Acids Res |
| 107 | Knowledge Graph-Enabled Cancer Data Analytics | Hasan, S.M.S., et al. | 2020 | IEEE J Biomed Health Inform |
| 108 | Improving chronic disease management for children | Yu, G., et al. | 2022 | Expert Syst Appl |
| 113 | Mining health knowledge graph for health risk prediction | Tao, X., et al. | 2020 | World Wide Web |
| 117 | CVD Atlas: a multi-omics database of cardiovascular disease | Qian, Q., et al. | 2024 | Nucleic Acids Res |
| 118 | VisAGE: Integrating external knowledge into electronic medical record visualization | Huang, E.W., et al. | 2018 | Pac Symp Biocomput |
| 120 | ALOHA: developing an interactive graph-based visualization for dietary supplement | He, X., et al. | 2019 | BMC Med Inform Decis Mak |
| 121 | Application and evaluation of knowledge graph embeddings in biomedical data | Alshahrani, M., et al. | 2021 | PeerJ Comput Sci |
| 122 | The biomedical knowledge graph of symptom phenotype in coronary artery plaque | Huan, J.M., et al. | 2024 | BioData Min |
| 125 | HEAL: A Knowledge Graph for Distress Management Conversations | Welivita, A., et al. | 2022 | AAAI |
| 128 | Building a PubMed knowledge graph | Xu, J., et al. | 2020 | Sci Data |
| 129 | A Coherent Biomedical Literature Clustering and Summarization Approach | Yoo, I., et al. | 2006 | DaWaK |
| 130 | Literature-Based Discovery beyond the ABC paradigm | Moreau, E., et al. | 2021 | bioRxiv |
| 131 | CoMent: Relationships Between Biomedical Concepts Inferred From the Scientific Literature | Pazos, F., et al. | 2022 | J Mol Biol |
| 132 | Expanding a database-derived biomedical knowledge graph | Nicholson, D.N., et al. | 2022 | BioData Min |
| 133 | Multitask Healthcare Management Recommendation System | Liu, W., et al. | 2021 | J Healthc Eng |
| 134 | When Radiology Report Generation Meets Knowledge Graph | Zhang, Y., et al. | 2020 | AAAI |
| 135 | A Relational-Learning Perspective To Multi-Label Chest X-Ray Classification | Sekuboyina, A.K., et al. | 2021 | ISBI |
| 138 | DKDR: An Approach of Knowledge Graph and Deep Reinforcement Learning for Disease Diagnosis | Jia, Y., et al. | 2019 | ISPA |
| 139 | Deep Bidirectional Language-Knowledge Graph Pretraining | Yasunaga, M., et al. | 2022 | arXiv |
| 143 | Learning and inference in knowledge-based probabilistic model for medical diagnosis | Jiang, J., et al. | 2017 | Knowl Based Syst |
| 144 | Towards Smart Healthcare Management Based on Knowledge Graph Technology | Huang, L., et al. | 2019 | ICSCA |
| 147 | Leap | Zhang, Y., et al. | 2017 | KDD |
| 148 | GAMENet: graph augmented memory networks for recommending medication combination | Shang, J., et al. | 2019 | AAAI |
| 149 | Smore | Ren, H., et al. | 2022 | KDD |
| 150 | Personalizing Medication Recommendation with a Graph-Based Approach | Bhoi, S., et al. | 2021 | ACM TOIS |
| 151 | A Knowledge Graph Approach to Elucidate the Role of Organellar Pathways in Disease | Pelletier, A.R., et al. | 2023 | J Vis Exp |
| 164 | Medkpl: a heterogeneous knowledge enhanced prompt learning framework | Lu, Y., et al. | 2023 | J Biomed Inform |
| 168 | Design and Implementation of Personal Health Record Systems Based on Knowledge Graph | Wang, H., et al. | 2018 | ITME |
| 169 | An overview of clinical decision support systems | Sutton, R.T., et al. | 2020 | NPJ Digit Med |
| 170 | Biomedical knowledge graph embeddings for personalized medicine | Vilela, J., et al. | 2022 | Expert Syst |
| 171 | Knowledge Graph Applications in Medical Imaging Analysis | Wang, S., et al. | 2022 | Health Data Sci |
| 172 | Imaging-based observational databases for clinical problem solving | Bui, A.A., et al. | 2013 | J Am Med Inform Assoc |
| 181 | Medical knowledge-enhanced prompt learning for diagnosis classification | Lu, Y., et al. | 2023 | ClinicalNLP |
| 186 | GENA: A knowledge graph for nutrition and mental health | Dang, L.D., et al. | 2023 | J Biomed Inform |
| 190 | A Knowledge Graph Enhanced Learner Model | Ettorre, A., et al. | 2020 | EKAW |
| 191 | How to Empower Disease Diagnosis in a Medical Education System | Ansong, S., et al. | 2019 | WISA |
| 192 | OpenBioLink: a benchmarking framework | Breit, A., et al. | 2020 | Bioinformatics |
| 193 | ROBOKOP KG and KGB | Bizon, C., et al. | 2019 | J Chem Inf Model |
| 194 | Enriching contextualized language model from knowledge graph | Fei, H., et al. | 2021 | Brief Bioinform |

### Graph Neural Networks & Deep Learning

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 30 | Representation Learning of Histopathology Images using Graph Neural Networks | Adnan, M., et al. | 2020 | CVPRW |
| 158 | ExFaKT: A Framework for Explaining Facts over Knowledge Graphs and Text | Gad-Elrab, M.H., et al. | 2019 | WSDM |
| 159 | GAP: A Graph-aware Language Model Framework | Colas, A., et al. | 2022 | COLING |
| 160 | JointGT: Graph-Text Joint Representation Learning | Ke, P., et al. | 2021 | Findings |
| 161 | Few-shot Knowledge Graph-to-Text Generation | Junyi, L., et al. | 2021 | Conference |
| 162 | KG-BART: Knowledge Graph-Augmented BART | Liu, Y., et al. | 2020 | arXiv |
| 163 | EventNarrative: A large-scale Event-centric Dataset | Colas, A., et al. | 2021 | arXiv |

### Visualization & Analysis

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 123 | QueDI: From Knowledge Graph Querying to Data Visualization | De Donato, R., et al. | 2020 | SEMANTiCS |
| 124 | Construction, Visualization and Application of Knowledge Graph of Computer Science Major | Li, Y., et al. | 2019 | ICBDE |
| 126 | Research Status, Hotspots, and Evolutionary Trends of Intelligent Education | Shi, D., et al. | 2022 | Sustainability |
| 127 | A systematic study of knowledge graph analysis for cross-language plagiarism detection | Franco-Salvador, M., et al. | 2016 | Inf Process Manag |

### Databases & Data Sources

| # | Title | First Author et al. | Year | Venue |
|---|-------|-------------------|------|-------|
| 80 | Pharmacokinetic and Pharmacodynamic Principles for Toxicology | Lista, A.D., et al. | 2021 | Crit Care Clin |
| 106 | The Unified Medical Language System (UMLS): integrating biomedical terminology | Bodenreider, O. | 2004 | Nucleic Acids Res |
| 109 | Gene Expression Omnibus: NCBI gene expression and hybridization array data repository | Edgar, R., et al. | 2002 | Nucleic Acids Res |
| 110 | DECIPHER: database for the interpretation of phenotype-linked plausibly pathogenic sequence | Bragin, E., et al. | 2014 | Nucleic Acids Res |
| 111 | MIMIC-III, a freely accessible critical care database | Johnson, A.E.W., et al. | 2016 | Sci Data |

> **Note**: This section includes a curated selection of the 196 papers referenced in our survey. For the complete list with full citations and DOIs, please refer to the [survey paper](https://arxiv.org/pdf/2501.11632).

## Contributing

We welcome contributions from the community! Please feel free to:
- Submit pull requests to add new resources
- Report issues or suggest improvements
- Share your BKG-related projects

## License

This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

## Contact

For questions or collaborations, please contact:
- Yuxing Lu: yxlu0613@gmail.com

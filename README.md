# Healthcare Knowledge Representation

### Comparative Evaluation of Knowledge-Representation Paradigms for Healthcare Question Answering

This repository accompanies the published research work:

> **Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms**

The study develops a unified computational framework for comparing knowledge-representation (KR) paradigms in healthcare Question Answering Systems (QAS), with emphasis on representational expressiveness, query coverage, reasoning depth, explainability, and scalability.

**Authors:** Atul Kumar Tripathi, Puja Minodji Thakre, and Niladri Chatterjee

**Publication:** Springer, *Intelligent Computing: Proceedings of the 2026 Computing Conference*

**DOI:** [10.1007/978-3-032-24807-7_4](https://doi.org/10.1007/978-3-032-24807-7_4)

---

## Research Question

> **How does the choice of knowledge representation technique influence the reasoning performance and answer quality of expert systems in the healthcare domain?**

To investigate this question, the study implements lightweight expert-system prototypes using multiple knowledge-representation paradigms and evaluates them against a common set of progressively complex clinical queries.

---

## Study at a Glance

| Component | Description |
|---|---|
| Domain | Cardiovascular healthcare |
| Dataset | 47 curated, anonymized patient records |
| Benchmark | 5 clinical queries (Q1–Q5) |
| KR paradigms | Propositional Logic, FOPL, Rule-Based Systems, Relational Databases, Frames, Ontologies, Knowledge Graphs |
| Evaluation | Semantic expressiveness, query coverage, reasoning depth, explainability, scalability |
| Main result | Knowledge Graphs achieved full coverage of the five benchmark queries |

The underlying clinical knowledge was kept semantically aligned across the representation paradigms to reduce bias caused by differences in the knowledge being represented. :contentReference[oaicite:5]{index=5}

---

## Research Context

Healthcare question answering requires systems to represent relationships between entities, reason across multiple clinical attributes, incorporate contextual information, and provide interpretable reasoning.

The study therefore compares classical and graph-based KR approaches under a common evaluation setting, progressing from simple Boolean reasoning to relational, multi-relational, and contextual queries.

The work sits at the intersection of:

- Knowledge Representation
- Knowledge Graphs
- Symbolic Artificial Intelligence
- Healthcare Question Answering
- Semantic Modelling

---

## Knowledge-Representation Paradigms

The study examines seven representation paradigms:

1. **Propositional Logic**
2. **First-Order Predicate Logic (FOPL)**
3. **Rule-Based Systems**
4. **Relational Databases**
5. **Frame-Based Models**
6. **Ontologies**
7. **Knowledge Graphs**

The study describes each paradigm as a lightweight expert-system prototype consisting of a knowledge base and an inference mechanism. :contentReference[oaicite:6]{index=6}

### Note on FOPL

FOPL is discussed and implemented as part of the study. However, the published comparative Table 1 does not report FOPL as a separate row. The repository preserves this distinction rather than presenting a reconstructed FOPL result as an independently reported published result. :contentReference[oaicite:7]{index=7}

---

## Benchmark Design

**Domain:** Cardiovascular healthcare  
**Dataset:** 47 curated, anonymized patient records  
**Benchmark queries:** 5

The benchmark was designed to increase in reasoning complexity from Boolean conditions to relational and contextual reasoning. :contentReference[oaicite:8]{index=8}

| Query | Reasoning type | Focus |
|---|---|---|
| Q1 | Boolean | Chest pain and smoking history |
| Q2 | Universal | Age, hypertension, and cardiovascular risk |
| Q3 | Relational | Diabetes, obesity, and cardiovascular risk |
| Q4 | Multi-relational | Comorbidities and treatment guidelines |
| Q5 | Contextual | Interventions informed by related clinical evidence |

The complete benchmark formulations are documented in [`queries/benchmark_queries.md`](queries/benchmark_queries.md).

---

## Benchmark Queries

### Q1 — Boolean

> Is a patient at risk of heart disease if chest pain is present and smoking history is negative?

### Q2 — Universal

> Are all patients over 60 years old with hypertension at elevated risk of cardiovascular disease?

### Q3 — Relational

> What are the cardiovascular risks for patients with both diabetes and obesity?

### Q4 — Multi-relational

> Which treatment guidelines are applicable for diabetic patients with left ventricular hypertrophy and a history of atrial fibrillation?

### Q5 — Contextual

> Suggest interventions for patients with comorbidities similar to those reported in recent literature.

These formulations are taken from the published benchmark design. :contentReference[oaicite:9]{index=9}

**Note:** These are research benchmark formulations and are not intended to provide clinical advice.

---

## Evaluation Framework

The study considers five dimensions:

- **Semantic expressiveness** — ability to represent hierarchical and contextual knowledge
- **Query coverage** — number of benchmark queries successfully addressed
- **Reasoning depth** — number of intermediate inference steps required to derive an answer
- **Explainability** — availability of transparent reasoning traces
- **Scalability** — ability to extend the approach to larger datasets and more complex reasoning tasks

The published comparative table is a qualitative assessment of query coverage, explainability, and reasoning depth. Semantic expressiveness and scalability are additionally discussed as broader evaluation considerations. :contentReference[oaicite:10]{index=10}

---

## Implementation

The study describes lightweight prototypes implemented using open-source computational tools.

| Representation Paradigm | Implementation |
|---|---|
| Propositional Logic | Python |
| First-Order Predicate Logic | SQLite-based relational queries |
| Rule-Based Systems | Python |
| Relational Databases | SQL-based structured queries |
| Frame-Based Models | JSON slot–filler structures |
| Ontologies | RDF/OWL using RDFLib and OWL-RL |
| Knowledge Graphs | RDF triple stores and SPARQL |

All implementations share a common schema aligned with the cardiovascular domain. :contentReference[oaicite:11]{index=11}

---

## Knowledge Graph Component

The Knowledge Graph representation models clinical entities and relationships using graph-structured knowledge.

The study examines its ability to support:

- multi-hop reasoning
- semantic integration
- contextual reasoning
- path-based explanation

In the benchmark, these capabilities become especially relevant for the more complex and context-sensitive queries.

---

## Comparative Results

The published comparative results are summarized below.

| Paradigm | Q1 | Q2 | Q3 | Q4 | Q5 | Explainability | Reasoning Depth |
|---|:---:|:---:|:---:|:---:|:---:|---|:---:|
| Propositional Logic | ✓ | – | – | – | – | Rule-based trace | 1 |
| Rule-Based Systems | ✓ | ✓ | – | – | – | Rule-based trace with patient list | 1 |
| Relational Database | ✓ | ✓ | ✓ | – | – | Direct SQL query results | 1 |
| Frames | ✓ | ✓ | ✓ | – | – | Graph traversal with slot-based reasoning | 1–2 |
| Ontology (OWL) | ✓ | ✓ | ✓ | ✓ | – | Inferred triples via SPARQL | 1–2 |
| Knowledge Graph | ✓ | ✓ | ✓ | ✓ | ✓ | Path-based traces with multi-hop reasoning | 3 |

The table above is a transcription of the qualitative comparison reported in the published study. :contentReference[oaicite:12]{index=12}

### Main Finding

**Knowledge Graphs were the only paradigm in the published comparison to achieve full coverage of all five benchmark queries.**

The study associates this broader coverage with multi-hop reasoning, contextual integration, and path-based explainability. At the same time, the paper notes that greater representational expressiveness introduces additional computational overhead, deeper reasoning paths, and greater verification effort. :contentReference[oaicite:13]{index=13}

---

## Study Contributions

The work contributes:

1. **A unified evaluation framework** for comparing multiple KR paradigms under a common set of progressively complex clinical queries.

2. **An empirical comparative analysis** of the reasoning boundaries of classical and graph-based representation approaches.

3. **A Knowledge-Graph-oriented perspective** on complex, multi-relational, and context-sensitive healthcare question answering. :contentReference[oaicite:14]{index=14}

---

## Limitations

The study identifies several important limitations:

- **Dataset size:** The evaluation uses 47 curated patient records, limiting generalizability.
- **Simulation of logical paradigms:** Propositional Logic and FOPL reasoning were implemented through Python conditionals and SQL queries rather than dedicated logic engines.
- **Manual knowledge curation:** Subclass relationships in the ontology and Knowledge Graph were manually curated, which may introduce representational bias.

These limitations are explicitly acknowledged in the published work. :contentReference[oaicite:15]{index=15}

---

## Future Research

The study identifies several directions for further work:

- evaluation on larger clinical datasets
- automated ontology alignment
- automated Knowledge Graph construction
- scalable knowledge integration
- hybrid neuro-symbolic reasoning
- integration of Knowledge Graphs with language-based AI systems

These directions extend the current benchmark toward larger-scale, more dynamic, and more integrated knowledge-based systems. :contentReference[oaicite:16]{index=16}

---

## Code Provenance and Reproducibility

This repository contains a **cleaned and reconciled public implementation** of the computational framework described in the published study.

Where the original research-development code was incomplete, inconsistent with the final manuscript, or dependent on non-public data, the corresponding components have been reconstructed and are explicitly documented as such.

The repository therefore **does not claim that every public implementation file is a byte-for-byte copy of the original experimental notebook**.

The included synthetic example dataset is provided for software validation and demonstration only. It is not the original research dataset and should not be interpreted as reproducing the published experimental data.

The published comparison table is preserved separately from runtime demonstration outputs.

See:

- [`docs/reconciliation.md`](docs/reconciliation.md)
- [`docs/reproducibility.md`](docs/reproducibility.md)
- [`docs/limitations.md`](docs/limitations.md)

---

## Data Availability and Research Ethics

The study used 47 curated, anonymized cardiovascular patient records.

The original patient-level research dataset is **not distributed in this repository**.

For reproducibility and demonstration, the repository includes only synthetic example data. No identifiable or confidential healthcare information is included.

---

## Repository Structure

```text

healthcare-knowledge-representation/
├── README.md
├── CITATION.cff
├── .gitignore
│
├── docs/
│   ├── reconciliation.md
│   └── limitations.md
│
├── queries/
│   └── benchmark_queries.md
│
├── results/
│   ├── README.md
│   └── published_comparison.csv
│
└── data/
    └── README.md

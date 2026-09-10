# Healthcare Knowledge Representation

### Comparative Evaluation of Knowledge-Representation Paradigms for Healthcare Question Answering

This repository accompanies the published research work:

> **Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms**

The study presents a unified framework for comparing knowledge-representation (KR) paradigms in healthcare Question Answering Systems (QAS), with emphasis on representational expressiveness, query coverage, reasoning depth, explainability, and scalability.

**Authors:** Atul Kumar Tripathi, Puja Minodji Thakre, and Niladri Chatterjee

**Publication:** *Intelligent Computing: Proceedings of the 2026 Computing Conference*, Springer

**DOI:** [10.1007/978-3-032-24807-7_4](https://doi.org/10.1007/978-3-032-24807-7_4)

---

## Research Question

> **How does the choice of knowledge representation technique influence the reasoning performance and answer quality of expert systems in the healthcare domain?**

The study addresses this question by comparing multiple knowledge-representation paradigms under a common evaluation framework using progressively complex clinical queries.

---

## Study at a Glance

| Component | Description |
|---|---|
| Domain | Cardiovascular healthcare |
| Dataset | 47 curated, anonymized patient records |
| Benchmark | 5 clinical queries (Q1–Q5) |
| KR paradigms | Propositional Logic, First-Order Predicate Logic, Rule-Based Systems, Relational Databases, Frame-Based Models, Ontologies, Knowledge Graphs |
| Evaluation | Semantic expressiveness, query coverage, reasoning depth, explainability, scalability |
| Main finding | Knowledge Graphs achieved full coverage of all five benchmark queries in the published comparison |

The underlying clinical knowledge was semantically aligned across paradigms to reduce bias arising from differences in the representation of the same domain knowledge.

---

## Research Context

Healthcare question answering requires systems to represent relationships among clinical entities, reason across multiple attributes, incorporate contextual information, and provide interpretable answers.

The study therefore compares classical and graph-based knowledge-representation approaches under a common evaluation setting, progressing from simple Boolean reasoning to relational, multi-relational, and contextual reasoning.

The work lies at the intersection of:

- Knowledge Representation
- Knowledge Graphs
- Symbolic Artificial Intelligence
- Healthcare Question Answering
- Semantic Modelling

---

## Knowledge-Representation Paradigms

The study considers seven representation paradigms:

1. **Propositional Logic**
2. **First-Order Predicate Logic (FOPL)**
3. **Rule-Based Systems**
4. **Relational Databases**
5. **Frame-Based Models**
6. **Ontologies**
7. **Knowledge Graphs**

Each paradigm was instantiated as a lightweight expert-system prototype consisting of a knowledge base and an inference mechanism.

### Note on FOPL

First-Order Predicate Logic is included in the methodology and implementation described in the paper. However, the published comparative Table 1 does not report FOPL as a separate row. This repository preserves that distinction and does not present an additional FOPL result as part of the published comparison.

---

## Benchmark Design

**Domain:** Cardiovascular healthcare

**Dataset:** 47 curated, anonymized patient records

**Benchmark queries:** 5

The benchmark queries progressively increase in reasoning complexity, from Boolean conditions to relational and contextual reasoning.

| Query | Reasoning Type | Focus |
|---|---|---|
| Q1 | Boolean | Chest pain and smoking history |
| Q2 | Universal | Age, hypertension, and cardiovascular risk |
| Q3 | Relational | Diabetes, obesity, and cardiovascular risk |
| Q4 | Multi-relational | Comorbidities and treatment guidelines |
| Q5 | Contextual | Interventions informed by related clinical evidence |

The complete benchmark formulations are provided in [`queries/benchmark_queries.md`](queries/benchmark_queries.md).

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

These questions are research benchmark formulations and are not intended to provide clinical advice.

---

## Evaluation Framework

The study evaluates the representation paradigms across five dimensions:

- **Semantic expressiveness** — ability to represent hierarchical and contextual knowledge
- **Query coverage** — number of benchmark queries successfully addressed
- **Reasoning depth** — number of intermediate inference steps required to derive a conclusion
- **Explainability** — availability of transparent reasoning traces
- **Scalability** — ability to extend the approach to larger datasets and more complex reasoning tasks

The published comparison table specifically reports qualitative query coverage, explainability, and reasoning depth, while semantic expressiveness and scalability are discussed as broader evaluation considerations.

---

## Computational Framework

The research prototypes were implemented using lightweight, open-source computational approaches:

| Representation Paradigm | Computational Approach |
|---|---|
| Propositional Logic | Python |
| First-Order Predicate Logic | SQLite-based relational queries |
| Rule-Based Systems | Python |
| Relational Databases | SQL-based structured queries |
| Frame-Based Models | JSON slot–filler structures |
| Ontologies | RDF/OWL using RDFLib and OWL-RL |
| Knowledge Graphs | RDF triple stores and SPARQL |

All implementations used a common schema aligned with the cardiovascular domain.

---

## Knowledge Graph Component

The Knowledge Graph representation models clinical entities and relationships as interconnected graph structures.

The study investigates its ability to support:

- multi-hop reasoning
- semantic integration
- contextual reasoning
- path-based explanation

These capabilities become particularly important for queries requiring multiple interconnected relations across patient attributes, clinical conditions, guidelines, and related evidence.

---

## Comparative Results

The following table reproduces the qualitative comparative results reported in the published study.

| Paradigm | Q1 | Q2 | Q3 | Q4 | Q5 | Explainability | Reasoning Depth |
|---|:---:|:---:|:---:|:---:|:---:|---|---:|
| Propositional Logic | ✓ | – | – | – | – | Rule-based trace | 1 |
| Rule-Based Systems | ✓ | ✓ | – | – | – | Rule-based trace with patient list | 1 |
| Relational Database | ✓ | ✓ | ✓ | – | – | Direct SQL query results | 1 |
| Frames | ✓ | ✓ | ✓ | – | – | Graph traversal with slot-based reasoning | 1–2 |
| Ontology (OWL) | ✓ | ✓ | ✓ | ✓ | – | Inferred triples via SPARQL | 1–2 |
| Knowledge Graph | ✓ | ✓ | ✓ | ✓ | ✓ | Path-based traces with multi-hop reasoning | 3 |

### Main Finding

**In the published comparison, Knowledge Graphs were the only paradigm shown to achieve full coverage of all five benchmark queries.**

The study associates this broader coverage with multi-hop reasoning, contextual integration, and path-based explainability.

The results also highlight a trade-off: greater representational expressiveness can involve deeper reasoning paths, additional computational overhead, and greater effort in verifying derived answers.

---

## Research Contributions

The study contributes:

1. **A unified evaluation framework** for comparing multiple knowledge-representation paradigms under a common set of progressively complex healthcare queries.

2. **An empirical comparative analysis** of the reasoning boundaries of classical and graph-based representation approaches.

3. **A Knowledge-Graph-oriented perspective** on complex, multi-relational, and context-sensitive healthcare question answering.

---

## Limitations

The study identifies several important limitations:

- **Dataset size:** The evaluation uses 47 curated patient records, limiting the generalizability of the findings.
- **Simulation of logical paradigms:** Propositional Logic and FOPL reasoning were implemented through Python conditionals and SQL queries rather than dedicated logic engines.
- **Manual knowledge curation:** Subclass relationships in the ontology and Knowledge Graph were manually curated, which may introduce representational bias.

These limitations should be considered when interpreting the comparative findings.

---

## Future Research

The study identifies several directions for further investigation:

- evaluation on larger clinical datasets
- automated ontology alignment
- automated Knowledge Graph construction
- scalable knowledge integration
- hybrid neuro-symbolic reasoning
- integration of Knowledge Graphs with language-based AI systems

These directions extend the current framework toward larger-scale, more dynamic, and more integrated knowledge-based systems.

---

## Data Availability and Research Ethics

The study used 47 curated, anonymized cardiovascular patient records.

The original patient-level research dataset is **not distributed in this repository**.

For reproducibility and demonstration, no identifiable or confidential healthcare information is included.

---

## Code Availability

The original research-development source code is **not publicly distributed in this repository**.

This repository is intended as a research companion providing the study description, benchmark formulations, published comparative results, and supporting documentation.

The repository does not claim that it provides the complete original experimental implementation.

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
├── data/
│   └── README.md
│
└── results/
    ├── README.md
    └── published_comparison.csv

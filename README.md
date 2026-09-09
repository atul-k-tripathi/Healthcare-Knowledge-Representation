# Healthcare Knowledge Representation

### Comparative Evaluation of Knowledge-Representation Paradigms for Healthcare Question Answering

This repository accompanies the published research work:

> **Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms**

The study develops a unified computational framework for comparing knowledge-representation paradigms in healthcare Question Answering Systems (QAS), with emphasis on reasoning capability, query coverage, explainability, semantic expressiveness, and scalability.

---

## Research Question

**How does the choice of knowledge-representation technique influence the reasoning performance and answer quality of expert systems in the healthcare domain?**

The study addresses this question by implementing lightweight expert-system prototypes using semantically aligned clinical knowledge and evaluating them with benchmark queries of progressively increasing complexity.

---

## Research Context

Healthcare question answering requires systems to represent relationships between entities, reason across increasingly complex clinical conditions, integrate context, and provide interpretable evidence for their answers.

This study therefore compares classical and graph-based knowledge-representation paradigms under a common evaluation setting.

The work is situated at the intersection of:

- Knowledge Representation
- Knowledge Graphs
- Symbolic Artificial Intelligence
- Healthcare Question Answering
- Semantic Modelling

The study also motivates future work on hybrid approaches combining structured knowledge with modern AI systems.

---

## Representation Paradigms

The study examines the following representation paradigms:

1. Propositional Logic
2. First-Order Predicate Logic (FOPL)
3. Rule-Based Systems
4. Relational Databases
5. Frame-Based Models
6. Ontologies
7. Knowledge Graphs

The paradigms are evaluated using semantically aligned clinical knowledge to reduce bias arising from differences in the underlying knowledge being represented.

---

## Benchmark

**Domain:** Cardiovascular healthcare

**Dataset:** 47 curated anonymized patient records

**Benchmark queries:** 5

The five queries progressively increase in reasoning complexity:

| Query | Reasoning type | Focus |
|---|---|---|
| Q1 | Boolean | Condition-based cardiovascular risk |
| Q2 | Universal | Quantified reasoning over patients |
| Q3 | Relational | Interacting clinical attributes |
| Q4 | Multi-relational | Comorbidities and treatment guidelines |
| Q5 | Contextual | Context-aware reasoning using related clinical knowledge |

---

## Evaluation Framework

The study evaluates the representation paradigms across:

- **Semantic expressiveness**
- **Query coverage**
- **Reasoning depth**
- **Explainability**
- **Scalability**

Reasoning depth is further examined in the comparative analysis as a measure of the number of intermediate inference steps required to derive a conclusion.

---

## Implementation

The study describes lightweight expert-system prototypes using open-source computational tools.

| Representation Paradigm | Implementation |
|---|---|
| Propositional Logic | Python |
| Rule-Based Systems | Python |
| First-Order Predicate Logic | SQLite-based relational queries |
| Relational representation | SQL-based structured queries |
| Frame-Based Models | JSON slot–filler structures |
| Ontologies | RDF/OWL, RDFLib, OWL-RL |
| Knowledge Graphs | RDF triple stores and SPARQL |

All implementations share a common schema aligned with the cardiovascular domain.

> **Repository principle:** public source code should consist only of verified research code actually used in the study, or clearly labelled and verified reconstruction code. The repository should never imply that newly reconstructed code is the original experimental implementation unless this is known to be true.

---

## Knowledge Graph Component

The Knowledge Graph representation models entities and relations as a connected graph and supports RDF-based representation and SPARQL querying.

The study examines its ability to support:

- multi-hop reasoning
- contextual integration
- semantic integration
- path-based explanations

This becomes particularly relevant for questions requiring several interconnected relations across patients, conditions, treatment guidelines, and related evidence.

---

## Benchmark Queries

The five queries were designed to increase in reasoning complexity.

### Q1 — Boolean

Is a patient at risk of heart disease if chest pain is present and smoking history is negative?

### Q2 — Universal

Are all patients over 60 years old with hypertension at elevated risk of cardiovascular disease?

### Q3 — Relational

What are the cardiovascular risks for patients with both diabetes and obesity?

### Q4 — Multi-relational

Which treatment guidelines are applicable for diabetic patients with left ventricular hypertrophy and a history of atrial fibrillation?

### Q5 — Contextual

Suggest interventions for patients with comorbidities similar to those reported in recent literature.

The complete benchmark formulations are documented in [`queries/benchmark_queries.md`](queries/benchmark_queries.md).

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

### Main Finding

**Knowledge Graphs were the only evaluated paradigm to achieve full coverage of all five benchmark queries.**

The study reports that Knowledge Graphs additionally supported:

- multi-hop reasoning
- contextual integration
- path-based explainability

The results also illustrate the trade-off between greater representational expressiveness and the additional computational and verification effort required for more complex reasoning.

---

## Explainability

A central consideration of the study is that reasoning in healthcare should remain inspectable.

The comparison therefore considers explicit reasoning traces, including:

- rule-based inference traces
- relational query outputs
- inferred ontology relationships
- graph-based reasoning paths

Knowledge Graphs provide path-based explanations that expose intermediate relations contributing to an answer.

---

## Research Contributions

The work contributes three main elements:

### 1. Unified Evaluation Framework

A common framework for comparing multiple knowledge-representation paradigms under progressively complex clinical queries.

### 2. Empirical Comparison

A benchmark-based comparison that identifies the reasoning boundaries of classical and graph-based representation paradigms.

### 3. Knowledge-Graph-Centric Perspective

An empirical basis for considering Knowledge Graphs as a strong foundation for complex, context-sensitive, and explainable healthcare question answering.

---

## Limitations

The study explicitly identifies several limitations.

### Dataset Size

The benchmark contains 47 curated patient records, which limits the generalizability of the empirical findings.

### Simulation of Classical Reasoning

Propositional Logic and FOPL were simulated using Python conditionals and SQL queries rather than dedicated logic engines.

### Manual Knowledge Curation

Subclass relationships in the ontology and Knowledge Graph were manually curated, which may introduce representational bias.

These limitations are important when interpreting the comparative results and motivate further research.

---

## Future Research Directions

The paper identifies several directions for further investigation:

- larger clinical datasets
- automated ontology alignment
- automated Knowledge Graph construction
- scalable knowledge integration
- hybrid neuro-symbolic reasoning
- integration of Knowledge Graphs with language-based AI systems
- improved validation and explanation of reasoning paths

These directions motivate a broader research trajectory at the intersection of:

**Knowledge Graphs × AI/ML × Statistics × Data Science × Explainable Reasoning**

This repository presents the current work as a foundation for that broader research direction rather than claiming that these future methods have already been implemented.

---

## Data Availability and Research Ethics

The study used 47 curated anonymized cardiovascular patient records.

The original patient-level research dataset is **not distributed in this repository**.

No identifiable, confidential, restricted, or otherwise sensitive healthcare information should be committed here.

Where reproducible examples are required, use only synthetic, appropriately anonymized, or legally shareable data.

---

healthcare-knowledge-representation/
│
├── README.md
├── CITATION.cff
├── .gitignore
│
├── queries/
│   └── benchmark_queries.md
│
├── docs/
│   ├── methodology.md
│   └── limitations.md
│
└── data/
    └── README.md

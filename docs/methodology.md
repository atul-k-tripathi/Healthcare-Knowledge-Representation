# Methodology

## Overview

The study develops a unified computational framework for comparing knowledge-representation (KR) paradigms for healthcare Question Answering Systems (QAS).

To support a fair comparison, the evaluated paradigms are instantiated using semantically aligned clinical knowledge and assessed using a common set of progressively complex benchmark queries.

---

## Evaluation Setting

### Domain

The study focuses on cardiovascular healthcare.

### Dataset

The study uses a curated dataset of **47 anonymized cardiovascular patient records** containing structured clinical attributes such as age, gender, chest pain, smoking history, and selected comorbidities.

The original patient-level research dataset is not publicly distributed in this repository.

### Benchmark

Five clinical queries, **Q1–Q5**, are used to progressively increase the reasoning complexity of the benchmark.

The queries range from Boolean and universal conditions to relational, multi-relational, and contextual reasoning.

---

## Representation Paradigms

The study considers the following knowledge-representation paradigms:

- Propositional Logic
- First-Order Predicate Logic (FOPL)
- Rule-Based Systems
- Relational Databases
- Frame-Based Models
- Ontologies
- Knowledge Graphs

The paradigms are evaluated using a common clinical knowledge schema to support comparison across representation approaches.

---

## Implementation

The study describes lightweight expert-system prototypes implemented using open-source computational approaches.

| Representation | Implementation |
|---|---|
| Propositional Logic | Python |
| First-Order Predicate Logic | SQLite-based relational queries |
| Rule-Based Systems | Python |
| Relational Databases | SQL-based structured queries |
| Frame-Based Models | JSON slot–filler structures |
| Ontologies | RDF/OWL using RDFLib and OWL-RL |
| Knowledge Graphs | RDF triple stores and SPARQL |

The implementations use a common schema aligned with the cardiovascular healthcare domain. :contentReference[oaicite:1]{index=1}

### Note on FOPL

FOPL is included in the methodology and implementation described in the study. However, the published comparative table does not report FOPL as a separate row. This distinction is preserved when presenting the published results.

---

## Evaluation Dimensions

The framework evaluates the representation paradigms across four primary dimensions:

- **Semantic expressiveness** — ability to represent hierarchical, relational, and contextual knowledge
- **Query coverage** — ability to address the benchmark queries
- **Explainability** — transparency of the reasoning process and derived answers
- **Scalability** — suitability for larger datasets and increasingly complex reasoning tasks

**Reasoning depth** is additionally analyzed as a measure of inferential complexity.

The published comparison specifically reports query coverage, explainability, and reasoning depth, while semantic expressiveness and scalability are considered as broader evaluation dimensions. :contentReference[oaicite:2]{index=2}

---

## Reasoning Depth

For a query \(q\), reasoning depth is defined as the length of the shortest valid reasoning path supporting the answer.

$$
RD(q) = \min_{p \in P(q)} |p|
$$

where:

- \(P(q)\) denotes the set of valid reasoning paths supporting the answer to query \(q\).
- \(|p|\) denotes the length of a reasoning path \(p\).

A lower reasoning depth represents shallower reasoning or direct retrieval, whereas a higher reasoning depth indicates a greater number of intermediate inference steps.

For graph-based reasoning, reasoning depth corresponds to the length of the shortest valid inference path connecting the relevant entities.

For example, the path

$$
A \rightarrow B \rightarrow C \rightarrow D
$$

contains three inference links and therefore has a reasoning depth of \(3\).

---

## Comparative Evaluation

The benchmark is used to examine how the choice of representation affects:

- the complexity of queries that can be addressed,
- reasoning depth,
- explainability,
- semantic integration, and
- support for multi-relational and contextual reasoning.

The published comparison shows progressively broader query coverage across the representation paradigms, with Knowledge Graphs achieving coverage of all five benchmark queries. :contentReference[oaicite:3]{index=3}

---

## Knowledge Graph Reasoning

Knowledge Graphs represent clinical entities and relationships as interconnected graph structures.

The implementation described in the study uses RDF-based representation and SPARQL querying. The graph representation supports multi-hop reasoning, semantic integration, contextual reasoning, and path-based explanations.

These capabilities are particularly relevant to queries requiring multiple interconnected relations across patients, clinical conditions, treatment guidelines, and related evidence. :contentReference[oaicite:4]{index=4}

---

## Methodological Scope

The framework is intended as a comparative research evaluation of knowledge-representation approaches for healthcare question answering.

The findings should be interpreted within the scope of the benchmark, dataset, implementation choices, and limitations described in the published study. The evaluation does not constitute a clinical validation study or a deployment-ready clinical decision-support system.

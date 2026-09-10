# Methodology

## Overview

The study develops a unified computational framework for comparing knowledge-representation paradigms for healthcare Question Answering Systems.

To support a fair comparison, the evaluated paradigms are instantiated using semantically aligned clinical knowledge and assessed using the same progressively complex benchmark queries.

---

## Evaluation Setting

### Domain

Cardiovascular healthcare.

### Dataset

The study uses a curated dataset of 47 anonymized patient records containing structured clinical attributes such as age, gender, chest pain and selected comorbidities.

### Benchmark

Five clinical queries (Q1–Q5) are used to progressively increase reasoning complexity.

---

## Representation Paradigms

The study discusses and evaluates:

- Propositional Logic
- First-Order Predicate Logic (FOPL)
- Rule-Based Systems
- Relational Databases
- Frame-Based Models
- Ontologies
- Knowledge Graphs

---

## Implementation

The paper describes lightweight expert-system prototypes using open-source computational tools:

| Representation | Implementation |
|---|---|
| Propositional Logic | Python |
| Rule-Based Systems | Python |
| First-Order Predicate Logic | SQLite-based relational queries |
| Frame-Based Models | JSON slot–filler structures |
| Ontologies | RDF/OWL, RDFLib, OWL-RL |
| Knowledge Graphs | RDF triple stores and SPARQL |

The implementations share a common schema aligned with the cardiovascular domain.

---

## Evaluation Dimensions

The framework considers:

- Semantic expressiveness
- Query coverage
- Explainability
- Scalability

Reasoning depth is additionally analyzed as a measure of inferential complexity.

---

## Reasoning Depth

For a query \(q\), reasoning depth is defined in terms of the shortest valid reasoning path:

\[
RD(q)=\min_{p\in P(q)} |p|
\]

where:

- \(P(q)\) is the set of valid reasoning paths supporting the answer
- \(|p|\) is the length of a reasoning path

In graph-based reasoning, deeper paths correspond to more intermediate inference steps.

---

## Comparative Evaluation

The benchmark is used to identify how the representational paradigm affects:

- the complexity of queries that can be answered,
- reasoning depth,
- explainability,
- semantic integration, and
- the ability to support multi-relational and contextual reasoning.

The published results show progressively increasing query coverage from classical representations toward Knowledge Graphs, with Knowledge Graphs covering all five benchmark queries.

---

## Knowledge Graph Reasoning

Knowledge Graphs are represented using graph-structured entities and relations.

The implementation described in the paper uses RDF-based representation and SPARQL querying and supports multi-hop reasoning and path-based explanations.

---

## Reproducibility Note

This repository should contain only verified source code and research materials that were actually used in the study, or clearly labelled and independently verified reconstructions.

The repository should never imply that a newly reconstructed implementation is the original experimental implementation unless that fact has been established.

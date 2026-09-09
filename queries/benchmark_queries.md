# Benchmark Queries

This document describes the five benchmark clinical queries used in the comparative evaluation.

The queries were designed to progressively increase in reasoning complexity, from Boolean reasoning to contextual reasoning.

---

## Q1 — Boolean

**Question**

> Is a patient at risk of heart disease if chest pain is present and smoking history is negative?

**Reasoning type:** Boolean

**Purpose:** Evaluates simple condition-based reasoning.

---

## Q2 — Universal

**Question**

> Are all patients over 60 years old with hypertension at elevated risk of cardiovascular disease?

**Reasoning type:** Universal / quantified

**Purpose:** Evaluates reasoning over patient populations and quantified conditions.

---

## Q3 — Relational

**Question**

> What are the cardiovascular risks for patients with both diabetes and obesity?

**Reasoning type:** Relational

**Purpose:** Evaluates reasoning over interacting clinical attributes.

---

## Q4 — Multi-relational

**Question**

> Which treatment guidelines are applicable for diabetic patients with left ventricular hypertrophy and a history of atrial fibrillation?

**Reasoning type:** Multi-relational

**Purpose:** Evaluates reasoning across multiple clinical conditions, relationships and treatment-guideline information.

---

## Q5 — Contextual

**Question**

> Suggest interventions for patients with comorbidities similar to those reported in recent literature.

**Reasoning type:** Contextual

**Purpose:** Evaluates reasoning requiring contextual integration of patient information and related clinical knowledge.

---

## Complexity Progression

```text
Q1 → Q2 → Q3 → Q4 → Q5

Boolean
   ↓
Universal
   ↓
Relational
   ↓
Multi-relational
   ↓
Contextual

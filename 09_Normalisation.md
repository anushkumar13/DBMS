# Normalization & Functional Dependency – Detailed Explanation

---

## What is Normalization?

Normalization is a process used to optimize the database design. It involves structuring the tables in a way that reduces data redundancy (repetitive storage of the same data) and ensures data consistency (accuracy and correctness of data). This process is performed step-by-step to eliminate common problems found in database design.

---

## What is Functional Dependency (FD)?

Functional Dependency describes a relationship between attributes (columns) in a database. Generally, it relates a primary key attribute with other attributes in a relation.

If we have a relation R with attribute sets X and Y, then X → Y means:

If you know the value of X, you can uniquely determine the value of Y.

- **X** is called the *Determinant* (the attribute that defines or determines).
- **Y** is called the *Dependent* (the attribute that depends on X).

---

## Types of Functional Dependency

- **Trivial FD:** When Y is a subset of X. This means the dependent attribute(s) are already included in the determinant attribute(s). For example, an attribute depending on itself.
  
- **Non-Trivial FD:** When Y is not a subset of X. This means the dependent attribute(s) are different and not included within the determinant attribute(s).

---

## Rules of Functional Dependency (Armstrong’s Axioms)

These are fundamental rules used to understand and derive functional dependencies:

- **Reflexive Rule:** If B is a subset of A, then A → B holds true. This means if B is already contained in A, A functionally determines B.
  
- **Augmentation Rule:** If A → B holds, then for any attribute set X, AX → BX also holds. Adding extra attributes to both sides preserves the dependency.
  
- **Transitivity Rule:** If A → B and B → C hold, then A → C also holds. This means dependency can be transferred through an intermediate attribute.

---

## Why Do We Normalize?

The main reason for normalization is to avoid redundancy in data. Storing the same data multiple times wastes space and can cause data inconsistencies.

---

## Problems Caused by Redundant Data

- **Insertion Anomaly:** Difficulty in inserting certain data without other related data present.
  
- **Deletion Anomaly:** Deleting some data unintentionally causes loss of other important data.
  
- **Update Anomaly:** Updating data in one place requires updates in multiple places, leading to inconsistencies if some updates are missed.

---

## Impact of Anomalies

Due to these anomalies, database size grows unnecessarily, performance slows down, and data inconsistency issues increase.

---

## How Does Normalization Solve These Issues?

Normalization designs the database to:

- Minimize redundancy.
- Avoid insertion, update, and deletion anomalies.
- Break large tables into smaller, logical parts and establish relationships among them.

---

## Types of Normalization (Normal Forms)

- **First Normal Form (1NF):** Ensures each cell contains atomic (single) values only; no multi-valued attributes.
  
- **Second Normal Form (2NF):** Achieved when relation is in 1NF and there are no partial dependencies; non-prime attributes must depend on the whole composite key, not just a part.
  
- **Third Normal Form (3NF):** Achieved when relation is in 2NF and has no transitive dependencies; non-prime attributes should not depend on other non-prime attributes.
  
- **Boyce-Codd Normal Form (BCNF):** A stricter form of 3NF where every determinant must be a super key. Any FD whose determinant is not a super key violates BCNF.

---

## Advantages of Normalization

- Significantly reduces data redundancy.
- Results in a more organized and maintainable database structure.
- Maintains data consistency across the database.
- Improves database performance, especially for update and delete operations.

---

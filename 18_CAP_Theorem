# CAP Theorem

CAP Theorem is a fundamental concept in the world of distributed databases. If you want to design a distributed system for your business, understanding CAP Theorem is essential.

---

## What Does CAP Stand For?

CAP stands for **Consistency**, **Availability**, and **Partition Tolerance** — these are three key properties present in every distributed system. However, a distributed system cannot fully guarantee all three simultaneously.

---

## Understanding the Three Components of CAP

### Consistency (C)

Consistency means that all nodes in the system show the same data at the same time. When a read operation is performed on a consistent system, the most recent write is always returned. This means if data is updated on one node, that update is immediately replicated across all nodes, ensuring every user, regardless of which node they connect to, sees the same data.

### Availability (A)

Availability means the system is always operational. Whenever a user sends a request, the system guarantees a response. However, this does not guarantee that the data returned is the most recent; it only ensures that the system remains accessible even if some nodes fail.

### Partition Tolerance (P)

Partition tolerance means that the system continues to operate correctly even if there is a communication break or network failure between nodes. Messages or data between some nodes might get lost or delayed, but the system still maintains its functionality. To achieve partition tolerance, data is replicated across multiple nodes.

---

## What Does the CAP Theorem Say?

The CAP theorem states that a distributed system can guarantee only two of these three properties at the same time: Consistency, Availability, and Partition Tolerance.

- If you want **Consistency** and **Availability**, you have to sacrifice Partition Tolerance.  
- If you want **Consistency** and **Partition Tolerance**, Availability might be compromised.  
- If you want **Availability** and **Partition Tolerance**, Consistency will be compromised.

---

## Application of CAP Theorem in NoSQL Databases

NoSQL databases are well suited for distributed systems as they support horizontal scaling and data distribution across multiple nodes. When choosing a NoSQL database, it is important to consider which two of the CAP properties are most critical for your use case.

---

## Summary

CAP Theorem explains a fundamental tradeoff in designing distributed systems: you can only fully guarantee two out of Consistency, Availability, and Partition Tolerance.

- **Consistency:** All users get the same, most recent data immediately.  
- **Availability:** The system is always accessible and responsive.  
- **Partition Tolerance:** The system can tolerate network failures or communication issues between nodes.

These tradeoffs are reflected in the practical design of databases, especially NoSQL systems, where different databases prioritize different pairs of these properties.

---

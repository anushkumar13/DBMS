# Transaction in Databases – Detailed Explanation

## What is a Transaction?
A transaction is a logical unit of work performed on a database as a sequence of operations. It consists of one or more database operations (such as SQL statements) that are executed together. The key point is that either all operations in a transaction are completed successfully, or none of them are applied. If any operation fails, all changes made by the transaction are undone, restoring the database to its previous state. 

In other words, a transaction is atomic — it either fully succeeds or fully fails, with no partial results left in between.

---

## ACID Properties of a Transaction
To ensure reliability and maintain data integrity, transactions follow four important properties known collectively as **ACID**:

### 1. Atomicity
Atomicity means that all operations within a transaction are treated as a single, indivisible unit. Either every operation completes successfully, or if any operation fails, the entire transaction fails and no changes are made to the database. This ensures the "all or nothing" behavior.

### 2. Consistency
Consistency ensures that the database moves from one valid state to another valid state after a transaction. All integrity constraints and rules defined on the database must hold true before and after the transaction completes. This guarantees the correctness of data.

### 3. Isolation
Isolation means that when multiple transactions are running concurrently, each transaction should operate as if it is the only transaction running on the database. Intermediate changes made by one transaction must not be visible to others until the transaction is committed, thus preventing conflicts and maintaining data consistency.

### 4. Durability
Durability guarantees that once a transaction has been committed successfully, all the changes made are permanent. These changes are saved reliably even if there is a system crash or power failure immediately after the commit.

---

## Transaction States (Transaction Life Cycle)
A transaction passes through multiple states during its lifetime. Understanding these states helps track the progress and status of a transaction:

### 1. Active State
This is the initial state when a transaction starts. The transaction performs read and write operations in this state. If everything goes well, it proceeds to the next state; otherwise, it may fail.

### 2. Partially Committed State
When all operations of the transaction are executed successfully but changes are not yet permanent, the transaction enters this state. The changes are in memory but not yet saved permanently in the database.

### 3. Committed State
Once the transaction’s changes are permanently saved in the database, the transaction is in the committed state. At this point, the transaction cannot be rolled back, and the database reflects the new consistent state.

### 4. Failed State
If an error or problem occurs during transaction execution, the transaction moves to the failed state. It cannot proceed further successfully.

### 5. Aborted State
After failure, the changes made by the transaction are undone through rollback, and the database is restored to its previous state. The transaction is said to be aborted.

### 6. Terminated State
When a transaction is either committed or aborted, it enters the terminated state. This marks the end of the transaction's lifecycle.

---

## Summary
A transaction is a logical sequence of database operations executed as a single unit of work, ensuring all-or-nothing execution. The **ACID properties**—Atomicity, Consistency, Isolation, and Durability—ensure data integrity and reliability during transactions. The transaction lifecycle moves through various states that indicate its current progress and status, from active to terminated.

---
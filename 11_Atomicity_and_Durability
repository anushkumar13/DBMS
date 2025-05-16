# Implementation of Atomicity and Durability in Transactions

Atomicity and Durability are two essential properties of transactions that ensure data integrity and reliability in database systems. These properties are implemented through various mechanisms within the Database Management System (DBMS).

---

## 1. Role of Recovery Mechanism  
The DBMS includes a Recovery Mechanism designed to support Atomicity and Durability. This mechanism ensures that in the event of system crashes or failures, the database can return to a consistent state without any data loss or corruption.

---

## 2. Shadow-Copy Scheme  
The Shadow-Copy Scheme is a straightforward method to implement Atomicity and Durability.  

- A disk pointer, called the **db-pointer**, always points to the current valid copy of the database.  
- When a transaction wants to update the database, it first creates a **new copy** of the entire database. The original copy is called the **shadow copy**.  
- All transaction updates are applied to the new copy, leaving the shadow copy untouched.  
- If the transaction fails or aborts, the new copy is discarded, and the shadow copy remains intact.  
- If the transaction commits successfully, the system ensures all changes to the new copy are written to disk, and then updates the **db-pointer** to point to the new copy.  
- After the pointer update, the new copy becomes the current database, and the old shadow copy is deleted.  

---

## 3. Atomicity in Shadow-Copy Scheme  
Atomicity is guaranteed because:  

- If the transaction fails before the db-pointer update, the original shadow copy remains unchanged.  
- The transaction is either fully applied (db-pointer updated) or not applied at all (new copy discarded).  

This ensures the "all or nothing" property of Atomicity.

---

## 4. Durability in Shadow-Copy Scheme  
Durability is ensured by:  

- On system restart after a crash, the DBMS reads the db-pointer to identify the valid database copy.  
- If the crash happened before pointer update, the system uses the old copy (no changes).  
- If the crash happened after pointer update, the system uses the new copy (changes are permanent).  
- A transaction is considered committed only after the db-pointer update, so its changes are permanent despite crashes.

---

## 5. Implementation Details of Shadow-Copy Scheme  
- This scheme involves heavy disk I/O because the entire database is copied for each transaction, making it inefficient for large databases.  
- The update of the db-pointer must be atomic, meaning it happens completely or not at all, to avoid inconsistency.  
- Disk systems typically support atomic updates at the block or sector level, so the db-pointer is stored in a dedicated disk block for atomic updates.

---

## 6. Log-based Recovery Methods  
Due to the inefficiency of the shadow-copy scheme, most real-world DBMS use **log-based recovery methods**.  

- These methods record transaction operations in a **log file** stored on stable storage before applying them to the database.  
- The log keeps a sequential record of all transaction operations for recovery purposes.

---

## 7. Log-based Recovery: Two Approaches  

### a) Deferred Database Modifications  
- All changes are recorded in the log first but applied to the database only after the transaction commits.  
- If a transaction aborts or crashes before commit, the log is ignored and no changes are applied.  
- If committed, the log entries are used to update the database (deferred writes).  
- In case of failure during write, redo operations replay log entries to complete updates.

### b) Immediate Database Modifications  
- Changes are applied to the database as they occur, even before the transaction commits (uncommitted changes).  
- If the transaction aborts or a crash occurs, the log's old values are used to undo these changes.  
- If the transaction commits and a crash happens afterward, the log's new values are used to redo the changes.  
- Logs must always be written to stable storage before applying changes to the database to maintain consistency.

---

## 8. Failure Handling Using Logs  
- If a failure occurs before transaction completion, changes are undone using old values in the log.  
- If a failure occurs after commit, changes are redone using new values from the log.  

This process ensures both Atomicity and Durability in the presence of failures.

---

## Summary  
- Atomicity is implemented using recovery mechanisms such as Shadow-Copy or Log-based methods, ensuring all-or-nothing transaction execution.  
- Shadow-Copy creates a full copy of the database and switches pointers upon commit to guarantee atomicity and durability, but it is inefficient.  
- Log-based recovery records transaction operations in a log file to apply or undo changes as needed, optimizing performance.  
- Durability is ensured by writing changes permanently to disk once the transaction commits.  
- Atomic updates to critical pointers (like db-pointer) are essential to prevent inconsistencies during system failures.

---
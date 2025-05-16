# Indexing in DBMS

Indexing is a special data structure used in a Database Management System (DBMS) to speed up the retrieval of data from a database table. It works like an index in a book that helps you quickly find the location of information without scanning the entire content.

## What is Indexing?

An index contains a copy of a key attribute (such as a primary key or any search key) from the database table. It acts as a pointer to the actual data stored in the database. Using indexing, DBMS can quickly locate the data without scanning the entire table.

## Index File Structure

An index file is typically sorted and consists of two main parts:

- **Search Key:** This is the value on which searching is done. It is usually a copy of the primary key or another key attribute.
- **Data Reference:** This is a pointer indicating the location (such as a disk block) where the actual data record is stored.

This structure allows the DBMS to efficiently locate the exact position of data on the disk.

## Why Use Indexing?

Indexing improves the performance of query processing, especially for SELECT queries with WHERE clauses. It reduces the number of disk I/O operations required to find the desired data.

## Types of Indexing Methods

### 1. Primary Index (Clustering Index)

- Used when the data file is sorted sequentially based on an attribute.
- The index is built on that sorted attribute, called the search key.
- It does **not** necessarily mean the index is built on the primary key; it is a common confusion.
- **Dense vs Sparse Index:**
  - **Dense Index:** Contains an index record for every search key value in the data file.
  - **Sparse Index:** Contains index records for only some search key values, typically one per data block.
- If data is sorted by a key attribute, a sparse index is created.
- If data is sorted by a non-key attribute, a dense index is used.

### 2. Multi-level Index

- When a single-level index becomes too large, it is divided into multiple levels.
- An index is created on top of another index, enabling faster binary search.
- This reduces the time to search within the index itself.

### 3. Secondary Index (Non-Clustering Index)

- Used when the data file is unsorted.
- Can be built on a key or non-key attribute.
- Typically a dense index where every record has an entry in the index.
- Since data is not sorted, this index helps locate data without scanning the whole table.

## Advantages of Indexing

- Enables faster data retrieval and improves query performance.
- Reduces the number of disk I/O operations needed.

## Limitations of Indexing

- Requires additional storage space to maintain the index.
- Slows down INSERT, DELETE, and UPDATE operations because the index must be updated along with the data.

## Summary

Indexing is a data structure that enhances the speed of data retrieval in DBMS. Primary indexing is used when data is sorted, while secondary indexing is used for unsorted data. Dense indexes contain entries for every record, whereas sparse indexes contain fewer entries. Multi-level indexing breaks large indexes into smaller levels for faster access. Indexing improves query performance but requires extra space and adds overhead to data modification operations.

---
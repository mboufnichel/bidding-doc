# Understanding Lock Modes in Databases (Kotlin Examples)

Locking is a fundamental concept in relational databases to ensure data consistency and prevent conflicts during concurrent access. Different lock modes control how transactions interact with each other when accessing the same data. This is essential to avoid anomalies like **lost updates**, **dirty reads**, or **phantom reads**. Lock modes define how much of the database is locked during a transaction and the impact on other transactions.

## Table of Contents
- [What Are Lock Modes?](#what-are-lock-modes)
- [Overview of Lock Types](#overview-of-lock-types)
- [Lock Modes in PostgreSQL](#lock-modes-in-postgresql)
- [Lock Modes in JPA](#lock-modes-in-jpa)
- [Pessimistic Locks](#pessimistic-locks)
    - [Pessimistic Read](#pessimistic-read)
    - [Pessimistic Write](#pessimistic-write)
- [Optimistic Locks](#optimistic-locks)
    - [Optimistic Locking](#optimistic-locking)
    - [Optimistic Locking with Increment](#optimistic-locking-with-increment)
- [How Lock Modes Affect Concurrency](#how-lock-modes-affect-concurrency)
- [Choosing the Right Lock Mode](#choosing-the-right-lock-mode)

---

## What Are Lock Modes?

Lock modes define how database rows, tables, or other resources are locked during a transaction. They determine how concurrent transactions interact with the same data. In general, a **lock** prevents other transactions from making conflicting changes to the same resource.

Locks can be classified into two categories:
- **Pessimistic Locking**: Locks resources immediately to prevent conflicts.
- **Optimistic Locking**: Assumes minimal conflicts and checks for issues only when committing.

---

## Overview of Lock Types

There are several types of locks, each serving a specific purpose in ensuring data integrity during concurrent access.

1. **Row-Level Locks**: Lock individual rows in a table.
2. **Table-Level Locks**: Lock an entire table.
3. **Advisory Locks**: Application-defined locks to prevent certain transactions from conflicting with each other.
4. **Index and Tuple Locks**: Lock specific indexes or data tuples.

---

## Lock Modes in PostgreSQL

PostgreSQL provides a variety of lock modes that control how transactions interact with data at different levels.

### Shared Locks (`SHARE`)

- **Purpose**: Allows multiple transactions to read a resource concurrently but prevents any transaction from modifying it.
- **Use Case**: When you need to read data but don’t want any changes to occur.

### Exclusive Locks (`EXCLUSIVE`)

- **Purpose**: Prevents any other transaction from acquiring a lock on the resource.
- **Use Case**: When you need to ensure that no other transaction modifies or reads the data while you are working with it.

### Row-Level Locks (`FOR UPDATE`, `FOR SHARE`)

- **Purpose**: These are more fine-grained than table-level locks and allow individual rows to be locked.
- **Use Case**: Useful for handling concurrent updates to specific rows in the same table.
    - `FOR UPDATE`: Locks the selected rows for update, preventing others from updating them.
    - `FOR SHARE`: Similar to `FOR UPDATE`, but it allows others to also acquire shared locks for reading.

---

## Lock Modes in JPA

JPA provides several lock modes that correspond to database lock modes. These lock modes are used with the `@Lock` annotation and methods like `find()` or `query()` to define how data is locked when accessed.

### 1. **Pessimistic Locks**
These locks are employed to prevent conflicts by immediately acquiring a lock on data. When a transaction acquires a pessimistic lock, it prevents other transactions from modifying or reading the locked resource.

#### Pessimistic Read (`PESSIMISTIC_READ`)

- **Definition**: This lock prevents other transactions from modifying the data but allows other transactions to read it.
- **Use Case**: Use this lock when you want to allow multiple transactions to read data but not write to it.
- **Behavior**: Blocks other transactions from acquiring a `PESSIMISTIC_WRITE` lock but allows other `PESSIMISTIC_READ` locks.

#### Pessimistic Write (`PESSIMISTIC_WRITE`)

- **Definition**: This lock prevents other transactions from reading or writing the data.
- **Use Case**: Use this lock when you need to update data and ensure no one else modifies it during the transaction.
- **Behavior**: Blocks both read and write locks from other transactions.


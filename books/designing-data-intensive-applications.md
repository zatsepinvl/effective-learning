# Designing Data-Intensive Applications
by Martin Kleppmann

## Chapter 7: Transactions

### Isolation Levels

#### 1. Read Uncommitted

#### 2. Read Committed
Implemented by storing old and new versions of data in the database, and only making the new version visible for new transactions.

#### 3. Snapshot Isolation (Repeatable Read)
Implemented by MVCC (Multi-Version Concurrency Control).

#### 4. Serializable
Implemented by:
1. Real serial execution
2. Two-Phase Locking
3. Serializable Snapshot Isolation (SSI) based on optimistic locking

### Race Conditions

#### 1. Dirty Reads and Writes
Happen when a transaction reads/writes data that has been modified by another transaction but not yet committed.

Prevented by read committed isolation.

#### 2. Read Skew
Happen when a transaction reads different parts of the database at different times, and the data it reads is inconsistent.

Prevented by snapshot isolation.

#### 3. Lost Updates
Happen when two transactions modify the same data, and one of the transactions overwrites the other's changes.

Prevented by:
1. Database atomic write operations. Especially, when they are commutative (might be invoked in any order and still give the same result, e.g. incrementing counter).
2. Explicit locking (e.g. `SELECT ... FOR UPDATE` in PostgreSQL)
3. Automatically detecting and retrying lost updates by database

#### 4. Write Skew
Happen when a transaction reads something, makes a decision based on that, and then writes something else based on that decision.
However, by the time the transaction writes, the data it read has changed and the premise of the decision is no longer true.

Prevented by serializable isolation.
See also [Select for update in MongoDB](https://www.mongodb.com/blog/post/how-to-select--for-update-inside-mongodb-transactions)

#### 5. Phantom Reads
Happen when a transaction reads objects that match a certain condition. Another client makes a write that affects the result of that search.

Prevented by snapshot isolation.
However, phantoms in the context of write skew require a special treatment, such as index-range locks.
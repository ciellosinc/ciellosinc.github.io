{:toc}

# Introduction

I first heard about the possibility of using Snapshot Isolation in Dynamics NAV after the release of dynamics NAV 2018.
Let's see what has changed since then and how we can use it in Сloud.
But first some theory. 

# Transactions

[Transactions (Database Engine)](https://learn.microsoft.com/en-us/previous-versions/sql/sql-server-2008-r2/ms190612(v=sql.105))

> A **transaction** is a sequence of operations performed as a single logical unit of work. A logical unit of work must exhibit four properties, called the atomicity, consistency, isolation, and durability (ACID) properties, to qualify as a transaction. 

|**Property**|**Description**|
|:--:|:--|
|**_Atomicity_**| A transaction must be an atomic unit of work; either all of its data modifications are performed, or none of them is performed.|
|**_Consistency_**|When completed, a transaction must leave all data in a consistent state. In a relational database, all rules must be applied to the transaction's modifications to maintain all data integrity. All internal data structures, such as B-tree indexes or doubly-linked lists, must be correct at the end of the transaction.|
|**_Isolation_**|Modifications made by concurrent transactions must be isolated from the modifications made by any other concurrent transactions. A transaction either recognizes data in the state it was in before another concurrent transaction modified it, or it recognizes the data after the second transaction has completed, but it does not recognize an intermediate state. This is referred to as serializability because it results in the ability to reload the starting data and replay a series of transactions to end up with the data in the same state it was in after the original transactions were performed.|
|**_Durability_**|After a transaction has completed, its effects are permanently in place in the system. The modifications persist even in the event of a system failure.|

## Controlling Transactions (Database Engine)

[Controlling Transactions (Database Engine)](https://learn.microsoft.com/en-us/previous-versions/sql/sql-server-2008-r2/ms175523(v=sql.105))

### <u>**Starting Transactions**</u>

Using API functions and Transact-SQL statements, you can start transactions in an instance of the SQL Server Database Engine as explicit, autocommit, or implicit transactions. Under a MARS session, Transact-SQL explicit and implicit transactions become batch-scoped transactions.

- **_Explicit Transactions_**
An explicit transaction is one in which you explicitly define both the start and end of the transaction.

DB-Library applications and Transact-SQL scripts use the BEGIN TRANSACTION, COMMIT TRANSACTION, COMMIT WORK, ROLLBACK TRANSACTION, or ROLLBACK WORK Transact-SQL statements to define explicit transactions.

```sql
   BEGIN TRANSACTION
```
Marks the starting point of an explicit transaction for a connection.

```sql 
  COMMIT TRANSACTION or COMMIT WORK 
```
Used to end a transaction successfully if no errors were encountered. All data modifications made in the transaction become a permanent part of the database. Resources held by the transaction are freed.

```sql
  ROLLBACK TRANSACTION or ROLLBACK WORK
```
Used to erase a transaction in which errors are encountered. All data modified by the transaction is returned to the state it was in at the start of the transaction. Resources held by the transaction are freed.

- **Autocommit Transactions**
The default mode for the Database Engine. Each individual Transact-SQL statement is committed when it completes. You do not have to specify any statements to control transactions.

- **Implicit Transactions**
Set implicit transaction mode on through either an API function or the Transact-SQL SET IMPLICIT_TRANSACTIONS ON statement. The next statement automatically starts a new transaction. When that transaction is completed, the next Transact-SQL statement starts a new transaction.
After implicit transaction mode has been set on for a connection, the instance of the Database Engine automatically starts a transaction when it first executes any of these statements:

```sql
   ALTER TABLE
   INSERT
   CREATE
   OPEN
   DELETE
   REVOKE
   DROP
   SELECT
   FETCH
   TRUNCATE TABLE
   GRANT
   UPDATE
```
The transaction remains in effect until you issue a COMMIT or ROLLBACK statement.

- **Batch-scoped Transactions**
Applicable only to multiple active result sets (MARS), a Transact-SQL explicit or implicit transaction that starts under a MARS session becomes a batch-scoped transaction. A batch-scoped transaction that is not committed or rolled back when a batch completes is automatically rolled back by SQL Server.


Transaction modes are managed at the connection level. If one connection changes from one transaction mode to another, it has no effect on the transaction modes of any other connection.

---

## <u>**Ending Transactions**</u>
You can end transactions with either a COMMIT or ROLLBACK statement, or through an API function.

```sql
COMMIT
```
If a transaction is successful, commit it. A COMMIT statement guarantees all of the transaction's modifications are made a permanent part of the database. A COMMIT also frees resources, such as locks, used by the transaction.
```sql
ROLLBACK
```
If an error occurs in a transaction, or if the user decides to cancel the transaction, then roll the transaction back. A ROLLBACK statement backs out all modifications made in the transaction by returning the data to the state it was in at the start of the transaction. A ROLLBACK also frees resources held by the transaction.



# 08. Databases & Database Management Systems

:material-account: Rahida Asadli, Rumiyya Alili, Ismayil Shahaliyev  
:material-calendar: Dec 1 2025 :material-calendar-edit: Jan 31, 2026

In the past, many systems stored information in simple text files. For example, a file named students.txt could have lines like:

```text
1201, Rəfail, IT, 3.5
1202, Nadal, CS, 3.9
```

Each line is one student. To use this information in a program, the programmer has to open the file, read each line, and split it into parts (ID, name, major, GPA). That "splitting into parts" is what we call [parsing](https://en.wikipedia.org/wiki/Parsing): taking one long [string](https://en.wikipedia.org/wiki/String_%28computer_science%29) like `1201, Rəfail, IT, 3.5` and turning it into separate values: `1201`, `Rəfail`, `IT` , and `3.5`.

If the university also has courses, grades, payments, dorms, and so on, there may be many different text files: students.txt , courses.txt , grades.txt, etc. Every application (mobile app, website, internal admin tool) must know how each file is structured and must write its own code to read, search, and update those files.

This creates several problems (**Exercise.** Which problems?):

- If a value changes (for example, a department name), it may appear in many files. Someone has to open every file and change it everywhere. It is very easy to miss one place and end up with _inconsistent_ data.
- To find something, the program usually has to read the whole file line by line, which becomes slow as the file grows.
- If two users or two programs try to edit the same file at the same time, the file can become _corrupted_, because there is nothing to coordinate their changes.
- If the computer crashes in the middle of writing to a file, part of the data might be lost or left in a broken state.

To solve these problems, we use the _database_ approach.

## Database Approach

[Database](https://en.wikipedia.org/wiki/Database) is an organized collection of data, and a [Database Management System (DBMS)](https://en.wikipedia.org/wiki/Database#Database_management_system) is the _software_ that manages this data for us. You can think of the DBMS as a very smart program whose only job is to store, protect, and provide access to data in a safe and efficient way.

Instead of many separate text files, the DBMS _may_ store data in tables with rows and columns. You describe to the DBMS what kind of data you want to store (for example: a table Students with columns StudentID, Name, Major, GPA), and then the DBMS takes care of: _Storing_ the data on disk in an efficient way. _Checking rules_, such as "every student must have a unique ID". _Allowing many users/programs_ to read and update the data at the same time without corrupting it. _Recovering_ from crashes so your data is not lost.

The big advantage is that applications no longer need to worry about reading raw files or parsing lines manually. They simply ask the DBMS: "Give me all students from the IT major with GPA above 3.0", and the DBMS finds and returns the result.

Because the DBMS hides all the low-level details of how data is stored on disk, we can change the physical storage (for example, move to a faster disk, change indexes) without changing the applications that use the data. Applications only see the _logical structure_ (tables and columns) while the DBMS handles the physical (e.g. hardware-level) interaction.

In short: The traditional file-based approach = many text files + lots of custom code + high risk of inconsistency and corruption. The database approach = one central DBMS (just software) that stores data in tables, enforces rules, supports many users, and provides a simple and safe way to work with data.

## Database Indexing

!!! note
    Suppose a database table contains 10,000 records, each identified by a unique numeric ID, and an index exists on this ID column. A _query_ asks for the record with ID 7421. Without an index, the database would need to scan the table sequentially, potentially examining all 10,000 rows. With the index, the database starts near the middle of the index and compares against a value such as 5000. Since 7421 > 5000, it ignores the lower half. It then compares against 7500, then 7000, and continues narrowing the range. After only a small number of comparisons, the exact index entry is found, and the database follows its pointer directly to the correct row.
    
  
<figure class="w100">
  <img src="../../assets/images/lecture08/binarysearch.gif" alt="Binary Search">
  <figcaption>
    Binary search. By <a href="//commons.wikimedia.org/w/index.php?title=User:Mazen_Embaby&amp;action=edit&amp;redlink=1" class="new" title="User:Mazen Embaby (page does not exist)">Mazen Embaby</a> - <span class="int-own-work" lang="en">Own work</span>, <a href="https://creativecommons.org/licenses/by-sa/4.0" title="Creative Commons Attribution-Share Alike 4.0">CC BY-SA 4.0</a>, <a href="https://commons.wikimedia.org/w/index.php?curid=124018514">Link</a>
  </figcaption>
</figure>

When a database table contains thousands or millions of records, searching for specific information can become very slow if the system has to read every single row. This is where _database indexing_ becomes essential. A [database index](https://en.wikipedia.org/wiki/Database_index) is a [data structure](https://en.wikipedia.org/wiki/Data_structure) that improves the speed of data retrieval operations on a database table. Think of it like the index at the back of a textbook: instead of reading every page to find information about Napoleon, you look up "Napoleon" in the index, which tells you exactly which pages to read. Similarly, a database index allows the system to quickly locate data without scanning every row.

When you create an index on a table, the database manager requires you to specify an _index key field_, the column on which the index will be based. For example, if you frequently search for students by their Student ID, you would create an index on the Student ID column. The database then performs these steps:

- _Reading and Extracting._ The DBMS reads each record in the table and extracts the value from the key field along with a [pointer](https://en.wikipedia.org/wiki/Pointer_%28computer_programming%29) that indicates where that record is physically stored.
- _Sorting._ All extracted values are sorted in alphanumeric order. This sorted list becomes the index.
- _Creating a Search Structure._ The index is typically organized as a [tree structure](https://en.wikipedia.org/wiki/Tree_structure). This allows the database to search very efficiently. Instead of checking every entry, it uses a [divide and conquer](https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm) approach: it starts at the top of the tree and narrows down the search by following branches, similar to how you would search for a word in a dictionary by opening it roughly in the middle and then deciding whether to look in the first half or second half.

In practice, databases do not rely on the simple [binary search](https://en.wikipedia.org/wiki/Binary_search) described in the example above. Instead, they use structures such as [B-trees](https://en.wikipedia.org/wiki/B-tree) (or [B+ trees](https://en.wikipedia.org/wiki/B%2B_tree)) which generalize the same divide-and-conquer principle while being optimized for disk access and large datasets.

While indexes dramatically speed up searches, they come with costs. Indexes require additional disk space to store the sorted key values and pointers. When you insert, update, or delete records, the index must also be updated, which takes extra time. Indexes need to be maintained and occasionally rebuilt as the database grows. For this reason, indexes are typically created on columns that are frequently used in search queries or for sorting, such as student IDs, email addresses, or dates.

## Data Models

A database is never built "in the abstract". Database always [models](https://en.wikipedia.org/wiki/Data_modeling) something that exists in the real world. It means that every important object and every important interaction in those processes should be representable as data in the database.

[Entity-Relationship (ER) diagram](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model) is a graphical representation of the data model. ER diagram uses a small set of visual symbols to represent the structure of data. Each symbol corresponds to a key concept: _entities, attributes_, and _relationships_. ER diagram is the blueprint from which the entire database [schema](http://schema) is built.

**Entity** is something that exists independently and can be uniquely identified. It is an [abstraction](https://en.wikipedia.org/wiki/Abstraction_%28computer_science%29) that captures one distinguishable concept in the real world. The important point is that each entity must be capable of having data stored about it, and it can be uniquely distinguished from all other entities. Entities behave like nouns in language. Examples: _Employee_, _Computer_, _Song_, _Book_, _Department_.

**Attributes** describe the properties of an entity. For example, _Student_ entity may have attributes: _Name, Surname, GPA, Admission Year._ Some attributes have special roles like, [primary key](https://en.wikipedia.org/wiki/Primary_key) attributes, uniquely identifying each instance.

**Relationship** shows how two or more entities are connected. Relationships behave like verbs linking nouns (entities). For example, _Employee_ **_works in_** _Department, Artist_ **_performs_** _Song._

Each relationship has a **_cardinality_** (`1:1`, `1:N`, or `M:N`) that determines how the relationship will appear in the database schema. For example, one employee works in one department (`1:1`), one department has many employees (`1:N`), a student takes many courses and a course has many students (`M:N`).

A data model _can_ be the collection of all these entities, their attributes, and their relationships. These constraints determine how tables will be constructed in the relational model. This data model is more than just storage: if the business rule says "a student cannot enroll in the same course twice in the same semester", that rule should be reflected in the model.

!!! success "Exercise"
    Provide an example of good and bad data models.

## Relational Database Model

[Relational database model](https://en.wikipedia.org/wiki/Relational_model) is the most widely used way of organizing data today. In the relational model, all information is stored in _tables_, similar to spreadsheets. Each table has **rows**, where each row represents one item (for example, one student), and **columns**, where each column represents something we want to store about that item (such as the student's name or GPA). Every table must have a special column called a **primary key**, which uniquely identifies each row. This prevents duplicate data and helps the database keep everything organized. When one table needs to refer to a row in another table, it stores the primary key of that row. This stored value is called a **foreign key**, and it creates a link between tables.

!!! success "Exercise"
    How can an ER diagram be represented with relational database model?

!!! success "Exercise"
    Take two tables and provide examples for primary and [foreign keys](https://en.wikipedia.org/wiki/Foreign_key).

Before relational databases existed, computers used different models to store data. One of these early models was the _hierarchical model_, which stored data in a tree-like structure. Imagine a company: at the top is the company itself, underneath are departments, and underneath each department are employees. Data could only be accessed by following this fixed path. This made the system rigid: if a programmer wanted to view employees grouped in a different way &ndash; for example, sorted by project instead of department &ndash; it became a challenging task. Changing the structure of the tree often broke the programs that depended on it.

## Structured Query Language (SQL)

When comparing different data modeling options, the relational model remains dominant because it provides a balanced combination of structure, accuracy, and flexibility. Its clear table format makes the data easy to understand. Its rules, like primary keys and foreign keys, help prevent mistakes. And because relational databases were designed to be independent of physical storage, programs do not break when the database engine changes how it stores data internally. SQL makes querying relational data straightforward and powerful. For these reasons, relational databases are used in banks, universities, hospitals, e-commerce websites, government systems, and almost every field where [_consistent_](https://en.wikipedia.org/wiki/Consistency_%28database_systems%29) and _reliable_ data is essential.

[SQL](https://www.w3schools.com/sql/) is a simple query language used to communicate with the relational database. The name comes from its original form, SEQUEL (Structured English Query Language), which was developed at IBM in the 1970s. The language was designed to work with the relational model proposed by [Edgar F. Codd](https://en.wikipedia.org/wiki/Edgar_F._Codd), whose work showed that data could be represented and queried using mathematical relations rather than low-level file structures. The name was later shortened to SQL for trademark reasons, but the pronunciation "sequel" remained common.

Strictly speaking, SQL is not a single language, but a family of languages defined by international standards. Organizations such as ANSI and ISO publish SQL standards that specify core syntax and behavior. However, real database systems do not implement the standard exactly. Instead, each DBMS provides its own SQL [dialect](https://en.wikipedia.org/wiki/Programming_language#Dialects,_flavors_and_implementations), extending or modifying the standard. Common SQL implementations include _Oracle, MySQL, PostgreSQL, Microsoft SQL Server,_ and _SQLite_. While these systems share a large common subset of SQL, they differ in features, syntax extensions, and behavior.[^1]

Instead of describing how data should be accessed, SQL allows users to specify what data they want, and the database system determines the most efficient way to retrieve it. The following query will retrieve two columns from the table students.

```sql
SELECT id, name FROM students
```

A new row to the table can be added with the following query:

```sql
INSERT INTO students (id, name, gpa) VALUES (1203, 'Badambura', 2.0)
```

Or deletion can be achieved based on a certain condition:

```sql
DELETE FROM students WHERE id=1203
```

## Database Normalization

Because SQL works directly with table names and column names, the structure of the data model becomes extremely important. SQL queries depend completely on how the data model is designed. A bad data model may allow _duplication_ of information, _contradictions_, and _anomalies_ when inserting, updating, or deleting data. To avoid bad data modeling, Edgar F. Codd and his colleagues at IBM developed a whole theory, known as [normalization](https://en.wikipedia.org/wiki/Database_normalization).

**Normalization** gives us formal rules for structuring tables so that each fact is stored only once, dependencies are clear, and common update problems are avoided. Normalization helps ensure the schema is correct _before_ SQL is written. A normalized schema reduces repeated data, avoids confusing table designs, keeps SQL queries stable for many years and makes it easier to maintain and extend the system. In practice, when you design databases in your professional career, you will rely on these normalization rules to evaluate and refine your schemas.

!!! tip
    It is highly suggested for you to take at least a brief look at different normal forms, starting from the [first normal form (1NF).](https://en.wikipedia.org/wiki/First_normal_form)

A bad data model becomes a long-term problem. It forces teams to constantly rewrite SQL queries, fix broken reports, and update multiple systems when the structure changes. A good data model, built with normalization in mind, protects the entire system. It keeps SQL programs reliable, keeps data consistent, and makes the database easier to manage as the organization grows. This is why **investing time in designing the data model properly at the beginning** is one of the most important steps in database development.

## Data Manipulation

[Relational algebra](https://en.wikipedia.org/wiki/Relational_algebra) is the mathematical foundation of how relational databases operate. Although we eventually write SQL queries and may not write algebra expressions directly, SQL is built on top of these relational algebra ideas (Edgar F. Codd was a mathematician in the end. Check out his infamous [paper](https://www.seas.upenn.edu/~zives/03f/cis550/codd.pdf)). The three most important operations in relational algebra are _selection_, _projection_ and the idea of _join_. These operations describe how we retrieve information from tables, how we combine tables.

**Selection** is the operation that chooses certain _rows_ from a table based on a condition. For example, if we have a students table and want to find only the students from SITE, the database can perform a selection. In algebra, this is written as . In SQL, the same idea appears in the WHERE clause:

```sql
SELECT * FROM students WHERE school = 'SITE'
```

Selection does **not** change the columns of the table (not to confuse it with the SELECT keyword!). It only filters out the rows that do not match the rule. This operation corresponds to everyday questions such as "Which employees work in the Finance department?" or "Which orders were created today?"

**Projection** is the operation that chooses certain columns from a table and ignores the others. If we take the Students table and want only the name and gpa, projection removes the unnecessary columns. Similar to selection's , in relational algebra, projection is denoted by the Greek letter π. In SQL, this appears in the SELECT keyword:

```sql
SELECT name, gpa FROM students;
```

Projection helps keep results focused and avoids returning more data than necessary. It supports questions like "Show me only the names of students," "List only the prices of products," or "Give me the course codes without any other details."

**Joining** is one of the most important relational algebra operations because it allows us to combine information stored in different tables. Since relational databases split data into multiple simple tables, joining them back together is essential for answering real questions. For example, suppose we have a students table and a separate enrollments table. If we want to know which students are taking a particular course, the database joins the two tables by matching rows that share the same student_id. In relational algebra, this is expressed using the join operator ⋈ together with a join condition. In SQL, the equivalent is a JOIN statement:

```sql
SELECT students.name, enrollments.course_id FROM students JOIN enrollments USING (student_id);
```

Joining allows us to answer questions that cannot be answered using a single table alone, such as "Which students are in this course?", "Which customer placed this order?", or "What flights does this passenger have reservations for?"

## SQL (RDBMS) vs NoSQL (NRDBMS)

When choosing how to store data, modern systems usually rely on two major families of databases: SQL databases, also called _relational database management systems (RDBMS)_, and [NoSQL](https://en.wikipedia.org/wiki/NoSQL) databases, also called _non-relational database management systems (NRDBMS)_. Although both store and retrieve data, they are designed in different ways and are suited to different types of problems.

**SQL databases** organize data into structured tables made of rows and columns, following the relational database model. The database enforces strict rules such as unique identifiers, relationships between tables, and integrity constraints. This strong structure makes SQL databases reliable and predictable, which is why they are commonly used in systems where accuracy and correctness are essential, such as banking systems, university registration systems, airline reservations, and other applications where data relationships must always be maintained.

**NoSQL databases** take a more flexible approach. Instead of fixed tables, they store data using formats such as documents, key-value pairs, graphs, or wide columns. This flexibility allows the database to adapt easily when the structure of the data changes or when very large amounts of data must be stored and accessed quickly. As a result, NoSQL databases are often used in social networks, messaging platforms, recommendation systems, and applications that handle large volumes of unstructured or rapidly changing data.

The key difference between SQL and NoSQL lies in their priorities. SQL databases emphasize structure, well-defined relationships, and correctness. NoSQL databases emphasize flexibility, scalability, and performance at large scale. For example, a bank would typically use a SQL database because financial data must remain accurate and consistent. In contrast, a chat application or social media platform may prefer a NoSQL database because it must handle millions of messages or posts per second and adapt quickly to changing data formats.

In practice, many modern systems use both approaches together: SQL databases for core, structured data that must remain reliable, and NoSQL databases for components that require high scalability and flexibility, such as logs, messages, user activity feeds, and analytics.

## Database Transactions

A [transaction](https://en.wikipedia.org/wiki/Database_transaction) moves the database from one consistent state (State A) to another consistent state (State B) by executing a sequence of operations (Operation 1, Operation 2, Operation 3, etc.). If all operations succeed, the transaction is _committed_. Commit means that the database permanently saves all changes made during the transaction. Once committed, the changes become part of the database and cannot be automatically undone. If any operation fails (due to an error, constraint violation, or system crash), the transaction is _rolled back_. Rolling back means the database discards all changes made during the transaction and returns to the previous consistent state. It is as if the transaction never happened. This commit/rollback mechanism is what makes transactions reliable and is enforced by the ACID properties described below.

!!! note
    Consider withdrawing money from an ATM.

    1. Your balance is 100 AZN.
    2. ATM checks if cash is available.
    3. ATM dispenses 10 AZN cash.
    4. System deducts 10 AZN from your balance.
    5. Your balance is now 90 AZN.

    If all operations succeed → **COMMIT** → Your balance permanently becomes 90 AZN. If Operation 2 fails (ATM runs out of cash) → **ROLLBACK** → No money is dispensed AND your balance stays 100 AZN. The database ensures you are not charged for money you did not receive. 

## ACID Properties

[ACID](https://en.wikipedia.org/wiki/ACID) describes the four rules a transaction must follow for the database to stay correct.

**A** for **Atomicity**. A transaction must be completed fully, or not at all

!!! note "Example"
    You transfer 20 AZN from your Bank Account A to Account B. Two steps occur: 1) Subtract 20 AZN from A, 2) Add 20 AZN to B. If step 2) fails (network crash), step 1) must be undone. Atomicity ensures money does not "disappear".

**C** for **Consistency**. The database must move from one _valid_ state to another valid state

!!! note "Example"
    If a rule says "GPA must be between 0.0 and 4.0", the database should never allow a transaction that sets GPA to 7.0.

**I** for **Isolation.** Even if many users are working at the same time, each transaction should behave as if it is running alone. It is known as [concurrency control](https://en.wikipedia.org/wiki/Concurrency_control)

!!! note "Example"
    Two students should not be allowed to register for the last available seat in a class at the same time.

**D** for **Durability.** Once a transaction is completed, its result must stay, even if the computer crashes

!!! note "Example"
    If you successfully buy a ticket and the system confirms it, the reservation should not disappear because of a power outage one second later.

Traditional relational database systems were designed to manage structured data stored on a single logical database, often running on one machine or a tightly controlled cluster. In this setting, the primary challenge is to ensure that concurrent transactions behave correctly. This led to the ACID properties, which define what it means for a transaction to be reliable. ACID focuses on correctness: transactions should either fully succeed or fully fail, preserve database rules, remain isolated from one another, and survive system crashes. These guarantees are practical and achievable when the system operates under centralized control and reliable coordination.

In contrast, many NoSQL systems were designed for large-scale, [distributed environments](https://en.wikipedia.org/wiki/Distributed_computing) spread across multiple machines and data centers. In such systems, network delays and failures are unavoidable, and it is not always possible to maintain strong coordination between all nodes. For this reason, the central concern shifts from transaction correctness to system behavior under [network partitions](https://en.wikipedia.org/wiki/Network_partition). This is captured by the CAP theorem described below.

## CAP Theorem

[CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem) states that a distributed data store cannot simultaneously guarantee _Consistency, Availability,_ and _Partition tolerance_. For example, when a network partition occurs, the system must choose between remaining available or maintaining strict consistency. about distributed systems - a system cannot guarantee all three.

**C** for **Consistency.** Everyone sees the same data

!!! note "Example"
    If you "like" a photo, your friend should immediately see the updated like count.

**A** for **Availability.** The system always responds.

!!! note "Example"
    Even if the system is busy, Instagram must show _something_.

**P** for **Partition Tolerance.** System still works even when network between servers breaks

!!! note "Example"
    If some servers cannot talk to each other (network issue), the app should not fully shut down.

This leads to trade-offs. For example, WhatsApp must always deliver messages (availability + partition tolerance). But sometimes messages appear out of order → consistency is temporarily sacrificed. No distributed large-scale system can fully satisfy all three in every situation.

!!! success "Exercise"
    Provide an example of a scenario, where A or P is sacrificed.

## Additional Material
- [7 Database Paradigms](https://www.youtube.com/watch?v=W2Z7fbCLSTw)
- [Binary Search Algorithm in 100 Seconds](https://www.youtube.com/watch?v=MFhxShGxHWc)
- [SQL Explained in 100 Seconds](https://www.youtube.com/watch?v=zsjvFFKOm3c&t=26s)
- [ACID Properties in Databases With Examples](https://www.youtube.com/watch?v=GAe5oB742dw)
- [CAP Theorem Simplified](https://www.youtube.com/watch?v=BHqjEjzAicA)
- [MongoDB in 100 Seconds](https://www.youtube.com/watch?v=-bt_y4Loofg)
- [Understanding B-Trees: The Data Structure Behind Modern Databases](https://www.youtube.com/watch?v=K1a2Bk8NrYQ)
- [SQL vs NoSQL or MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)
- [PostgreSQL in 100 Seconds](https://www.youtube.com/watch?v=n2Fluyr3lbc)

[^1]: If you don't know what to choose, usually you cannot go wrong with [PostgreSQL](https://www.postgresql.org/) which also happens to be open-source. 
# database-engine
A simple key-value database engine with file persistence and basic query capabilities.
It mimics the functionalities of databases like MySQL, but in a lightweight way. Instead of running a dedicated server, it uses a simple file on disk to store and retrieve key-value pairs, implemented in any programming language.
* Concurrent Access: In traditional DBMS systems, concurrency is managed using locks (such as table locks in MyISAM or row-level locks in InnoDB) to ensure that multiple users can safely access and modify data.
In this project, concurrency is handled in a simplified way:
File Locking / Mutexes are used to prevent multiple processes or threads from writing to the data file at the same time.
A transaction-like mechanism can be introduced, where changes are first applied in memory and only written to the file on commit, ensuring consistency during concurrent operations.
This approach mimics how larger database engines manage concurrent access, but is adapted to a lightweight, file-based key-value system.
* Data Integrity: Data integrity ensures the accuracy, consistency, and validity of stored data. In enterprise databases, this is achieved through physical and logical safeguards.
In this project, data integrity is maintained through:
Atomic Writes: Data is first written to a temporary file before replacing the main file, reducing corruption risks during unexpected shutdowns.
Validation Rules: Keys and values are checked before insertion to prevent invalid or malformed entries.


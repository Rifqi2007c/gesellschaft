### database system(DBMS) vs file system

| aspect                  | database system(DBMS)                                | file system                              |
| ----------------------- | ---------------------------------------------------- | ---------------------------------------- |
| data redundancy         | reduce data redundancy through data normalization    | high redundancy due to isolated file     |
| data consistensy        | maintains consistency through data normaliztion      | difficult to maintain data consistency   |
| data access             | easy access using queries (mySQL)                    | requires custom program for data access  |
| data security           | advance security with user access control            | limited security features                |
| transaction management  | support transaction(ACID properties)                 | no built-in transaction support          |
| concurrent access       | allow multi-user access with control                 | concurrent access is hard to manage      |
| backup & recovery       | automated backup and recovery systems                | manual backup and recovery               |
| data relationship       | support relationship between data (relational model) | no concept of data relationship          |
| time & const effeciency | saves time and cost in the long run                  | maintenece is costly as the system grows |
| scalability             | easily scalable to handle large data volume          | difficult to scale effectively           |
### DMBS function
- data dictionary management
	- defines data element and their relationships
- data storage management
	- stores data and related data entry in related form, report, definition
- data tansformation and presentation
	- translates logical request into commands to physically locate and retrive the request data
- security management
	- enforces data security and data privacy within database
- multi-user control access control
	- create structure that allow multiple user to access the data
- backup and recovery management
	- provide backup and recovery data procedures
- data integrity management
	- promote and enforces integrity rule to eliminate data integrity problem
- database access languages and application programming interface
	- provide data access through query language (mySQL)
- data base comunication interface
	- allow data base to accept end-user request within a computer network enviroment

### data abstraction
- for the system to be useable, it must retrive data effeciently
- since many database user are not computer trained, developer hide the complexity from user through several level of abstraction, to simplify user inetraction with the system
	- view level (external view/schema)
		- the highest level of abstraction describes only part of the data base
		- many user of data base dont need all the information, instead they only need to access part of the database
		- exist to simplify user interaction with the system
	- logical level (conceptual view/schema)
		- describes what are the database store and what relationship exist among the data
		- describes the entire database in term of small number of relativity simple structure
	- physical level (internal view/schema)
		- describes how the data is actually stored
		- describes complex low-level data structure in detail
### DMBS language
- data definition language (DDL)

---
#UNIMEL 
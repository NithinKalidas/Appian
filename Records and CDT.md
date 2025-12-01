# Appian Process Model Interview Question

## 1. What is the difference between Records Vs CDT?

Custom Data Type (CDT)	
Used to map to a database table/view via a Data Store Entity. Can also be used as a purely in-memory data structure.
Data is queried directly from the database using functions like a!queryEntity(). No built-in caching
Relationships (e.g., one-to-many) must be explicitly defined in the CDT structure and often require careful design (nested vs. flat) and complex queries to build relationship between tables
Cannot create fields that don't exist in the database table.

Record Type
Can source data from a database, process instances, web services, or other external systems.
Can be configured with Data Sync to cache data on Appian's server for faster querying using a!queryRecordType().
Supports low-code relationships to other Record Types, allowing simple dot-notation for querying related data.
Can define Custom Record Fields (Virtual Fields) using expressions to calculate or transform data on-the-fly without changing the underlying database.

## 2. Limitation of Records and CDT?

CDT: 
No built-in join handling; you must write custom queries manually
No inherent security model—must handle manually
No calculated/virtual fields; everything must exist in DB

Records:
Sync breaks if external application changes the data in DB
4 Million Rows (per synced Record Type). (licence has to be upgraded inorder to increase the limit)
Related Record limit: 100 Related Records for queryRecordType and 250 for queryRecordByIdentifier.
Text 4000 and Extra long text 64000 character limit

## 3. How do you create CDT?
Create a Table in SQL
Create Data Store Entity 
Create Data Store
Create Constant for Data store entity

## 4.Difference between Sync vs Non Sync Records?
Synced Records store data in Appian memory 
Non Synced Records is data queried and fetched from DB

## 5. How many types of relationship are in Records?
| **Relationship Type** | **Description**                                                         | **Example**                               |
| --------------------- | ----------------------------------------------------------------------- | ----------------------------------------- |
| **1. One-to-One**     | One record in a source relates to exactly one record in another source. | One employee → One employee detail record |
| **2. One-to-Many**    | One record relates to multiple records in another source.               | One customer → Many orders                |
| **3. Many-to-One**    | Many records relate back to one record in another source.               | Many students → One class                 |


## 6. How do you achieve many to many relationship?
For Many-to-Many: Not directly supported as a single relationship type. 
Create an intermediate record type (e.g., Student -> Enrollment -> Class) to bridge them.

## 7. What is the difference between Record Action Vs Related Action?
| Feature                    | Record Action             | Related Action                          |
| -------------------------- | ------------------------- | --------------------------------------- |
| **Use case**               | Create a new record       | Update or Delete an existing record     |
| **Example**                | Add New Employee          | Update Selected Employee                |

## 8. What are the types of Backed Record Type? (NR)
Entity Backed
Process Backed
Expression Backed

## 9. What is data fabric?

## 10. What are the different ways to sync a record?
Manual sync
Sync on Create/Update/Delete (CUD events)
Sync after Record Actions
Sync via Process Model write operations
Sync using a!syncRecords() Smart service
Sync via Refresh Interval / Polling
Using ICF - Force sync to true when deployed to higher environment

(or)

External System-Initiated (Real-Time Webhook)
Web API with a!syncRecords(): The external system calls an Appian Web API (acting as a webhook) upon a data change, triggering an immediate sync of the specific record(s) using their identifiers.
Sync Records Smart Service: An Appian process (often triggered by an integration or the Web API above) explicitly calls this smart service, passing a list of record identifiers (primary keys) to be synced.

Scheduled or Manual Syncs (Bulk/Consistency)

Scheduled Full Sync: Appian fetches all data from the source and replaces the entire synced cache on a daily schedule.
Scheduled Incremental Sync: Appian checks a designated "Last Modified" timestamp in the source and fetches only the changed or new records on a customizable, frequent schedule (e.g., every 15 minutes).
Manual Full Sync: An administrator manually triggers a complete refresh of all records via the "Start Full Sync" button in the Record Type settings.

## 11. What are the different ways to use a record (Table, web service , PM)
 * Database
 * Process
 * Web Service
 * Sales Force
 * Create From Scratch

## 13. How do you increase query Performance?
Use selection to limit the number of columns to be returned.
Use filters wherever possible.
Use a limited batch size rather than -1.
Set fetchTotalCount to false.


## 15. If i write more than 5000 Character using record, where there is no issues in varchar limit, will it write the date or truncate? and how much data will get back when i query the data? (firts 4000 or last 4000)

## 16. What approach you use to delete In-Active Records?
In Same Process model, at end before it completes we can create a stored procedure 

## 17. How do you optimise your records having more than 4 millions of data? (OR) How do you sync more than 4 Millions rows of records?

## 18. How many ways we can query a data from record?
1. a!queryRecordType() : is a function used to fetch multiple records (rows) from a Record Type based on filters, paging, and sorting.
2. a!queryRecordByIdentifier() : The Record Type Identifier is the unique primary identifier (key) of each record in a Record Type.

## 19. What is ther return type of query entity and query record?
Query Record: List of Dictionary 
Query Entity: DataSubset

## 20. How do you cofigure securities to records?

## 21. Difference between Record level security and field level security?
Record level security : Determine who can see the records by adding security rules (NR)

## 22. What is view and action security?

## 23. What are the sync methods available in records?
Schedule Full Sync
Schedule incremental syncs
In Monitoring, under Record sync status -> Start Full Sync

## 25.  What are record level datasource?

## 26. What are the different types of records created in Appian?
Entity Backed Records
Service/Expression Backed Records
Process Backed Records

## 27. What is a data sync and when should I use it?
When data sync is enabled, you are caching your source data in Appian. With a cache of your data, this means Appian will only have to execute queries from the cached data instead of the external source whenever you view or interact with the record data. Refer here on when to use data sync.

## 28. When should default filters and user filters be used?
Default Filters: Used when the filter has to be applied to the source while retrieving the data for the record type.
User Filters: Applied by the user once the record type list is displayed.

## 29. How many additional views can be added to a record type?
Total 20 along with Summary view

## 30. What is the difference between an action and a related action?
Action: Creates new data in the system.
Related Action: Performs some action related to the existing data.

## 31. What are the different ways to create a CDT?
From Scratch
Duplicating the existing datatype
From database view or table
From XSD
From Web Services

## 32. What are the different ways to fetch details from a database?
Query DB smart service
Query Entity
Query rule (Deprecated)

## 33. What is the purpose of fetchTotalCount and provide a scenario where fetchTotalCount has to be true?
fetchTotalCount returns the total number of rows in a table based on the applied filters. This is usually set to false (i.e., when batch size is not -1) as it takes extra time to retrieve the total. Set to true when used in a Read-Only grid to calculate the total number of pages required.

## 34. What is the range of filtered record list for which the "Export to Excel" button is disabled?
The button is enabled to export up to 100,000 records from the list, including rich text, images, and links.

## 35. Source Type to get data into appian records
Database
Process
WebService
Salesforce

## 36. Long Text vs text in Record?
64000 characters for long text 
4000 character for text

## 37. Best practice for querying data?
Query fetch totalcount to false (using it only when required)
Querying only the record field that is required
Query only in Parent interface and avoid querying in child interface, to reduce the no of query if reusable is needed

## 38. Difference between query record type and record type identifier?
 | queryrecordtype()                  | recordType.identifier             |
| ---------------------------------- | --------------------------------- |
| Queries **data**                   | Locates **a single record**       |
| Can return **multiple records**    | Points to **one record**          |
| Used in reports / lists            | Used in links / write actions     |
| Heavy operation (executes a query) | Lightweight (just passes ID)      |
| Accepts filters, sorting, paging   | No filtering options — just an ID |




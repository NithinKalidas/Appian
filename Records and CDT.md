# Appian Process Model Interview Question

## 1. What is the difference between Records Vs CDT?
| Feature | Custom Data Type (CDT) | Record Type |
|--------|------------------------|-------------|
| Primary Purpose | Maps to a database table/view via Data Store Entity and can be used as an in-memory data structure | Represents data from DB, process instances, APIs, or external systems |
| Data Retrieval | Queried directly from the database via `a!queryEntity()` | Queried using `a!queryRecordType()`,`a!queryRecordByIdentifier()`,`a!recordData()` (Grid)|
| Caching | No built-in caching | Supports **Data Sync** to cache data for faster performance |
| Relationships | Must be explicitly designed in CDT (nested/flat structures) and often require complex queries | Supports Data Fabric for relationship using **dot notation** |
| Virtual / Custom Fields | Cannot create fields that do not exist in the DB table | Supports **Custom Record Fields** (Virtual Fields) calculated via expressions without altering DB |
| Flexibility in Data Source | Only database tables/views | Database, process models, APIs, web services, or other systems |

## 2. Limitation of Records and CDT?

CDT: 
 * No built-in join handling; you must write custom queries manually
 * No inherent security model—must handle manually
 * No calculated/virtual fields; everything must exist in DB

Records:
 * Sync breaks if external application changes the data in DB
 * 4 Million Rows (per synced Record Type). (licence has to be upgraded inorder to increase the limit)
 * Related Record limit: 100 Related Records for queryRecordType and 250 for queryRecordByIdentifier.
 * Text 4000 and Extra long text 64000 character limit

## 3. How do you create CDT?
 * Create a Table in SQL
 * Create Data Store Entity 
 * Create Data Store
 * Create Constant for Data store entity

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
Many-to-Many Relationship: Not directly supported as a single relationship type. 
Create an intermediate record type (Eg: Student -> Enrollment -> Class) to bridge them.

## 7. What is the difference between Record Action Vs Related Action?
| Feature                    | Record Action             | Related Action                          |
| -------------------------- | ------------------------- | --------------------------------------- |
| **Use case**               | Create a new record       | Update or Delete an existing record     |
| **Example**                | Add New Employee          | Update Selected Employee                |

## 8. What are the types of Backed Record Type?
 * Database Table Backed Records
 * Service Backed Records
 * Process Backed Records

## 9. What is data fabric?
Data Fabric in Appian allows applications to access and manage data from multiple sources through records in a unified, secure, and real-time manner.

## 10. What are the different ways to sync a record?
 * Manual Full sync (via the "Start Full Sync" button)
 * Sync on Create/Update/Delete (CUD events)
 * Sync after Record Actions
 * Sync using a!syncRecords() Smart service in interface 
 * Sync Records Smart Service (passing a list of record identifiers (PK) to be synced)
 * Sync via Process Model write operations
 * Schedule Full Sync
 * Schedule incremental syncs
 * Using ICF - Force sync to true when deployed to higher environment

## 11. 

## 12. How do you increase query Performance?
 * Use selection to limit the number of columns to be returned.
 * Use filters wherever possible.
 * Use a limited batch size rather than -1.
 * Set fetchTotalCount to false.

## 13. If i write more than 5000 Character using record, where there is no issues in varchar limit, will it write the date or truncate? and how much data will get back when i query the data? (firts 4000 or last 4000)
5000 character will be written and only 4000 character will be retrieved back.

## 14. What approach you use to delete In-Active Records?
In Same Process model, at end before it completes we can create a stored procedure 

## 15. How many ways we can query a data from record?
1. a!queryRecordType() : is a function used to fetch multiple records (rows) from a Record Type based on filters, paging, and sorting.
2. a!queryRecordByIdentifier() : The Record Type Identifier is the unique primary identifier (key) of each record in a Record Type.

## 16. What is ther return type of query entity and query record?
 * Query Record: List of Dictionary 
 * Query Entity: DataSubset

## 17. How do you cofigure securities to records?
 * Record Type Object Security: Set up the role map (Viewer, Editor, Administrator) on the record type so users can access the record type and see data.
 * Record-Level Security: Enable record-level security (for synced record types) and create security rules or a security expression to control which records each user can see.
 * Record View Security:For each additional record view, configure security rules or security expressions to determine who can see that view and under what conditions.
 * Record Action Security:Secure related actions by adding security rules so only authorized users (with appropriate group/role and process initiator rights) can start or view record actions.

## 18. Difference between Record level security and field level security?
 * Record-Level Security: Controls who can see which records (rows) in a record type. It limits visibility of entire records based on security rules or expressions (e.g., only assigned users see certain records).
 * Field-Level Security: Controls who can see specific fields (columns) within a record. It hides or nullifies sensitive field values for unauthorized users, while still allowing access to the rest of the record.

## 19. Delete related record action, how not to show error page and redirect? 
Delete action outside the related action using Process model call Outside the view page

## 20. Record Smart Search? 
Record Smart Search is an AI-powered semantic search feature that you can enable on a synced record type so users can search using natural language or concepts rather than exact keywords

## 21. 

## 22. What is a data sync and when should I use it?
When data sync is enabled, you are caching your source data in Appian. With a cache of your data, this means Appian will only have to execute queries from the cached data instead of the external source whenever you view or interact with the record data. Refer here on when to use data sync.

## 23. When should default filters and user filters be used?
Default Filters: Used when the filter has to be applied to the source while retrieving the data for the record type.
User Filters: Applied by the user once the record type list is displayed.

## 24. How many additional views can be added to a record type?
Total 20 along with Summary view

## 25.


## 26. What are the different ways to create a CDT?
 * From Scratch
 * Duplicating the existing datatype
 * From database view or table
 * From XSD
 * From Web Services

## 27. What are the different ways to fetch details from a database? (Nr)
 * Query DB smart service
 * Query Entity
 * Query rule (Deprecated)

## 28. What is the purpose of fetchTotalCount and provide a scenario where fetchTotalCount has to be true?
FetchTotalCount returns the total number of rows in a table based on the applied filters. This is usually set to false (i.e., when batch size is not -1) as it takes extra time to retrieve the total. Set to true when used in a Read-Only grid to calculate the total number of pages required.

## 29. What is the range of filtered record list for which the "Export to Excel" button is disabled?
The button is enabled to export up to 100,000 records from the list, including rich text, images, and links.

## 30. Difference between Extra Long Text, Long Text and text in Record?
 * 64000 characters for Extra long text 
 * 4000 character for Long text
 * 255 character for text

## 31. Best practice for querying data?
 * Query fetch totalcount to false (using it only when required)
 * Querying only the record field that is required
 * Query only in Parent interface and avoid querying in child interface, to reduce the no of query if reusable is needed

## 32. Difference between query record type and record type identifier?
| queryrecordtype()                  | recordTypebyIdentifier            |
| ---------------------------------- | --------------------------------- |
| Queries **data**                   | Locates **a single record**       |
| Can return **multiple records**    | Points to **one record**          |
| Used in reports / lists            | Used in links / write actions     |
| Heavy operation (executes a query) | Lightweight (just passes ID)      |
| Accepts filters, sorting, paging   | No filtering options — just an ID |








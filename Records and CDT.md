# Appian Process Model Interview Question

## 1. What is the difference between Records Vs CDT?

## 2. Limitation of Records and CDT?

## 3. How do you create CDT?

## 4.Difference between Sync vs Non Sync Records?

## 5. How many types of relationship are in Records?

## 6. How do you achieve many to many relationship?

## 7. What is the difference between Record Action Vs Related Action?

## 8. What are the types of Backed Record Type?

## 9. What is data fabric?

## 10. What are the different ways to sync a record?

## 11. What are the different ways to use a record (Table, web service , PM)

## 12. Limitations of CDT?

## 13. How do you increase query Performance?

## 14. webservice/Database/salesforce?

## 15. If i write more than 5000 Character using record, where there is no issues in varchar limit, will it write the date or truncate? and how much data will get back when i query the data? (firts 4000 or last 4000)

## 16. What approach you use to delete In-Active Records?

## 17. How do you optimise your records having more than 4 millions of data? (OR) How do you sync more than 4 Millions rows of records?

## 18. How many ways we can query a data from record?

## 19. What is ther return type of query entity and query record?

## 20. How do you cofigure securities to records?

## 21. What are the sync methods available in records?

## 22. Record Type security vs record level security?

## 23.  What are record level datasource?

## 24. ##  . What are the different types of records created in Appian?
Entity Backed Records
Service/Expression Backed Records
Process Backed Records

##  . What is a data sync and when should I use it?
When data sync is enabled, you are caching your source data in Appian. With a cache of your data, this means Appian will only have to execute queries from the cached data instead of the external source whenever you view or interact with the record data. Refer here on when to use data sync.

##  . When should default filters and user filters be used?
Default Filters: Used when the filter has to be applied to the source while retrieving the data for the record type.
User Filters: Applied by the user once the record type list is displayed.

##  . How many additional views can be added to a record type?
Total 20 along with Summary view

##  . What is the difference between an action and a related action?
Action: Creates new data in the system.
Related Action: Performs some action related to the existing data.

##  . What are the different ways to create a CDT?
From Scratch
Duplicating the existing datatype
From database view or table
From XSD
From Web Services

##  . What are the different ways to fetch details from a database?
Query DB smart service
Query Entity
Query rule (Deprecated)

##  . What is the purpose of fetchTotalCount and provide a scenario where fetchTotalCount has to be true?
fetchTotalCount returns the total number of rows in a table based on the applied filters. This is usually set to false (i.e., when batch size is not -1) as it takes extra time to retrieve the total. Set to true when used in a Read-Only grid to calculate the total number of pages required.

##  . Provide the ways to optimize the results of a query entity
Use selection to limit the number of columns to be returned.
Use filters wherever possible.
Use a limited batch size rather than -1.
Set fetchTotalCount to false.

##  . What is the range of filtered record list for which the "Export to Excel" button is disabled?
The button is enabled to export up to 100,000 records from the list, including rich text, images, and links.


## 25.

## 26.

## 27.

## 28.

## 29.

## 30.

## 31.

## 32.

## 33.

## 34.

## 35.

## 36.

## 37.

## 38.

## 39.

## 40.

## 41.

## 42.

## 43.

## 44.

## 45.

## 46.

## 47.

## 48. 


## 1. What is the architecture of Appian?
Appian uses a 3-tier architecture where the UI is rendered with SAIL, business logic runs in Appian’s engines, and data is stored in Appian/external databases via the unified Data Fabric.
 * Process Execution Engine – Runs workflows
 * Content Engine – Documents & folders
 * Analytics Engine – Reports and metrics
 * Collaboration Engine – Tasks, news, discussions
 * Search Server – Full text search
 * Rules Engine – Evaluates expressions & SAIL
 * Data Fabric – Single virtual data layer
 * Personalization - Stores users, group membership & group types. 

## 2. How many engines are present in appian default?
A default Appian installation has 15 engines: 3 process execution engines, 3 process analytics engines, 6 other individual engines, and 3 to support legacy portal. 
An initial Appian installation installs three execution engines and three analytics engines.
It is possible to add up to a total of 32 execution and 32 analytics engines by defining them in appian-topology.xml. 

     <engine name="forums"/>
     <engine name="notify"/>
     <engine name="notify-email"/>
     <engine name="channels"/>
     <engine name="content"/>
     <engine name="collaboration-statistics"/>
     <engine name="personalization"/>
     <engine name="portal"/>
     <engine name="process-design"/>
     <engine name="process-analytics0"/>
     <engine name="process-analytics1"/>
     <engine name="process-analytics2"/>
     <engine name="process-execution0"/>
     <engine name="process-execution1"/>
     <engine name="process-execution2"/>

## 3. Which Appian objects Permission level or Securities Inheritance?

| Always Inherit Security From Parent | Always Inherit Security IF Parent Specified | Inherit Security From Parent By Default (Editable) | Never Inherit Security | Don't Have Security |
|------------------------------------|---------------------------------------------|----------------------------------------------------|------------------------|----------------------|
| Documents                          | Groups                                      | Constants                                          | AI Skill               | Custom Data Types    |
| Process reports                    | Knowledge centers                           | Decisions                                          | Applications           | Group Types          |
|                                    |                                             | Document folders                                   | Connected systems      |                      |
|                                    |                                             | Expression rules                                   | Data stores            |                      |
|                                    |                                             | Integrations                                       | Dashboards             |                      |
|                                    |                                             | Interfaces                                         | Feeds                  |                      |
|                                    |                                             | Rule folders                                       | Process model folders  |                      |
|                                    |                                             |                                                    | Process models         |                      |
|                                    |                                             |                                                    | Record types           |                      |
|                                    |                                             |                                                    | Reports                |                      |
|                                    |                                             |                                                    | Robot pool             |                      |
|                                    |                                             |                                                    | Robotic tasks          |                      |
|                                    |                                             |                                                    | Sites                  |                      |
|                                    |                                             |                                                    | Tempo reports          |                      |
|                                    |                                             |                                                    | Translation sets       |                      |
|                                    |                                             |                                                    | Web APIs               |                      |


## 4. how do you modify the securities for 1000 appian objects?
Using security summary (under gear symbol) it can cofigure

## 5. What are the stages appian recommend to use in Project ?
 * Dev (Development)
 * SIT (System Integration Testing)
 * UAT (User Acceptance Testing)
 * Pre Production
 * Production

## 6. How 2 environment can we configured for compare and deploy method for development?
In Appian Admin console -> Devops -> Infrastructure -> Add new Environment

## 7. What are necessary checks for pre deployement and post deployment?
PreDeployment :
 * Create all necessary DB scripts and organise to one script
 * Checking Missing Precedents
 * Scheduler Process Model check
 * Security Summary
 * Proper exporting of all objects
 * Inspecting all objects and fixing issues if any
 * Force Sync (in custom properties, sync enable)
 * Object Version conflicts 
 * Deployment Fails Due to Locked Objects.
 * Circular Dependencies Between Objects.
 * Import Customisation File ICF Not Applied or Misconfigured.

Post Deployment :
 * Security Checks
 * Error in Logs
 * Change in Constant for Post scheduler Process

## 8. How to deploy groups/users/service account to higher environment? Will Group Id Changes when we deploy to higher environment? 
Users and Service account need to configured manually. Groups can be moved to next environment but not the users. 

## 9. How to create 50 users to next environment? (NR)
using create user smart service we can create but how 50 data's are populated?

## 10. Why can users not be deleted or moved to another environment in Appian?
The license cost is based on the number of users per environment, and Appian maintains metadata based on users. Hence, users cannot be moved or deleted.

## 11. Different Types of prod Issues you have encounter?
PV Variable was mis configured, due to which calculation went missing, using report we took the process instances, getexternalPv or setexternalPv

## 12. What is use case of Customisation file and what is environment constant / (connected System)? 
The customization file is used to provide values to the environmental constant and connected systems when deploying to another environment so that the value changed isn't missed.

## 13. What are the limitations for business user?
In Appian, a Business User (usually someone from the business team who reviews tasks and data but does not design/develop applications) has limited access and capabilities compared to Designers / Administrators.

## 14. What is hot fix?
Hot fix is an bug of appian, which appian provide to fix those bugs.

## 15. How do you force deploy to next environment?
By Removing UUID / Customisation File (NR)

## 16. What are Production bugs? How did you fix them?
Reproduce the Production bugs in lower environment and fix those bugs, once fixed move the fixes to the next next environments.

## 17. How to download a document when it is unplublished?
From Appian 25.3 we can able to download the document by using a!documentDownloadLink() passing the doc Id, for Lower Version Environment through process model you need to write in DB and then download the Documents.

## 18. How much document size appian can send to external document?
Request Body : Can't exceed 5 mb
Base 64 : Combined size of file 75 mb
Binary files : 250 Mb

## 19. How do you check if document exist or not in your application?
getcontentobjectdetailsbyid()

## 20. How do you delete the document which is older than 2 years, when your unaware of document Id?
Using "Delete Documents Created Before Date" smart service in the Process model, Under Input enter our desired date on "Delete Before Date".

## 21. How to move document without changing its ID to next environment?
Can't be done, Documet Id varies for different environment

## 22. how to configure Single click document download?
Contruct the excel sheet or document and pass it in document download link

## 23. What is Portal and how does sign in and sign out works?
Business user who does not have login credential in appian but able to access
Eg: Complaince related to water shortage, Electricity shortage 

## 24. If any request is submitted through an user by portal, how can we find them?
By creating a request id which can be configured through email id or phone number using unique set of constraints

## 25. How do you handle errors in Portal? 
Portals do NOT support out-of-the-box Appian error dialogs. Portals run outside the Appian environment
Errors must be handled manually in the interface and integrations
check dependents and navigate (It will show which precedents caused issue)
Published with no error message (Open interface, comment child interface and check one by one which causing the error)
Error will be emaailed to admin

## 26. What is the purpose of user start page?
When configured, this allows the user to directly log in to the given site rather than the Tempo page.

## 27. Suppose we need to Insert 100000 rows of data on daily basis in a week how can we do that or what is the optimised way to prevet without affecting the Performance? (NR)
 * Batch-wise insertion (off business hours): Split data into smaller batches (e.g., 5k–10k rows) and run during non-business hours to avoid user impact.
 * Use wait timer between batches: Adding a small wait time prevents continuous heavy DB writes and reduces load spikes.

## 28. Suppose we have 1000 entries in excel file and how can i dumb to 5 different database?
Read excel smart service and segreagate the DB, Write to data store entity for each data write as schema might differ.

## 29. Huge amount of data in external system, how will you use in appian application?
 * CDT based approach -> Integration Object -> Call data in batch and use integration object in PM and store in DB and use the data
 * Record Type: Create record with web service menthod, inside webservice need to create integration (before creating integration, connected system need to configure data source as well). sync also can be enabled and will be achieved through batching

## 30. In PM, 10 Approvers need to approve then only we need to proceed to next step? how to define them? (NR)
By Creating separate individual sub process in sync for each approvers (In sync method Parent process instance will wait for child process to complete)
For DB driven, query the data in script task and once all completed, proceed with next steps

## 31. why do we split tabel in Database? why can't we store all in single DB?
Split tabel because it would create major performance, storage, consistency, scalability, and maintainability issues.
Databases follow Normalization, where data is split into related tables to avoid duplication and ensure efficiency.

## 32. What are the different licenses available and for what components are they provided?
 * k3.lic for engines
 * k4.lic for the data server

## 33. what is health chekup and use case?
check metrics and performance log critical fix, high fix, medium,  low (check if fix)

## 34. What is monitoring and use case? 
 * Health Dashboard: Overall system health view showing performance, errors, and resource usage.
 * Process Activity: Monitors running, completed, and failed process instances.
 * Process Model Metrics: Shows performance metrics like execution count and average completion time of process models.
 * Record Response Times: Tracks how fast record data is loaded for end users.
 * Record Sync Status: Monitors the status and failures of record data synchronization jobs.
 * Query Performance: Analyzes database query execution time to identify slow or inefficient queries.

## 35. What is difference between equal to and like operator?
 * Equal: The value must be exactly equal to the column value. Faster (can use index directly)
 * Like: Used for pattern-based match. LIKE is slower, especially if value starts with %
   
## 36. Differnce between optimising Performance through admin console and through interface objects?
| Admin Console                          | Interface Object                          |
|----------------------------------------|-------------------------------------------|
| Rule execution monitoring              | Monitor query calls                       |
| Monitor resource allocation            | Optimizing rule inputs & local variables  |
| Complete environment monitoring        | Specific object monitoring                |

## 37. How do you implement Optimistic locking in appian?
In CDT Based approch, we can add a new column Version and default set to zero, In XSD package add @Version and import and then using trigerrs we can create those versions.

## 38. difference between tomcot logs and performance logs?
| Tomcot Logs                           | Performance Logs                         |
|---------------------------------------|------------------------------------------|
| Server startup/shutdown details       | Use request response Times               |
| Application deployment errors         | Process/rules execution time             |
| Java exception stack traces           | Database query performance               |

## 39. What is decision table and say some use case scenario?
A Decision Table in Appian is a rule-based grid used to evaluate multiple conditions and return results without complex nested if() or case() logic.
It provides a tabular visual framework to make business decisions clear, maintainable, and reusable.
| Columns        | Purpose                                                               |
| -------------- | --------------------------------------------------------------------- |
| Input Columns  | Conditions to evaluate (state, amount, age, score, etc.)              |
| Rule Rows      | Each row represents a rule set                                        |
| Output Columns | Result when a rule is matched                                         |
| Hit Policy     | Defines whether to return first match, all matches, or collect values |

## 40. Tempo vs Site?
| Tempoo                  | Site                                                   |
|-------------------------|--------------------------------------------------------|
| Default by appian       | Can configure based on business need                   |
| View/See all tasks      | Security acess can be modified (View/Modify)           |
| Can't add logo          | Can Add Logo                                           |
| No changes can be done  | Changes can be Done to site based on requirement       |


## 41. Difference between DB driven and Process driven based approach?
 * DB Drivern : A DB-driven approach means data drives the state of the application instead of workflows.
 * Process models are minimized; most operations happen via records, smart services, write to data store, and interfaces.
Process Driven: A process-driven approach means the workflow (process model) is the center of the application.
All business logic, task assignments, and data updates are managed inside process models.

## 42. What is task log?
A Task Log in Appian is a system-generated audit log that records every action performed on a task during its lifecycle. It helps you track who did what, when, and what changed on a task.

## 43. what is charts and what are its types in appian?
Chart are used to diagramatically represent the value
 * Bar Chart
 * Column Chart
 * Pie Chart
 * Line Chart
 * Area Chart
 * Scatter Chart

## 44. What is UUID and does it change for different environment?
UUID is an Universally Unique Identifier - remains stable acrosss different environment

## 45. If a user belongs to multiple groups that have different start pages configured, his start page will be the highest one in the grid that corresponds to a group that he belongs to.
TRUE

## 46. What are the different types of Appian installations and state their differences?
On-Premise: The physical hardware is with us and maintenance is also done by us.
On-Cloud: The physical hardware is with Appian, and Appian handles the maintenance. The URL will have "appiancloud" in it.
Hybrid: A combination of On-Premise and On-Cloud. For example, a training environment where the hardware is with Appian but maintenance is done by us.

## 47. What are the different datatypes available in Appian? Give examples for each.
Primitive: Int, Text, Date, DateTime
Appian Object: Application, Process Model
Complex: PagingInfo, DataSubset
Custom Data Type

## 48. What are the benefits of modular coding?
Reusability of objects
Easy change management
Easy debugging
Reduced number of lines per interface

## 49. how do you build an Application
Get Clear Requirements
Analyse the requirement and flow process
Create Data Model
Create DB and Record Type (or) CDt and Data Store
Create required constants and Interface
Create PM
Create Reports
Do multiple Testing
Create Site and Configure

## 50. What are new appian features or new release (25.4)?
 * AI-Powered Reporting: Users can create reports instantly using AI Copilot.
 * Increased Sync Limits: You can now sync up to 50 million rows per record type, significantly increasing data capacity.
 * Transparent Data Encryption (TDE) for synced data — Enterprises can now protect their synced data at rest with built-in encryption, with no changes required at the application level.
 * More resilient sync behavior — If a smart-service sync fails, you can now skip the failure and continue with the last good data, improving application availability.
 * Appian Composer is now Generally Available — An AI-powered planning and design tool. You can upload requirements (DOC, PDF, etc.), and Composer helps generate business rules, workflows/process models, and a high-level application plan
 * Appian Composer is now Generally Available — An AI-powered planning and design tool. You can upload requirements (DOC, PDF, etc.), and Composer helps generate business rules, workflows/process models, and a high-level application plan.
 * Agent Studio — Build AI Agents for your processes. Agents can read unstructured data (e.g., emails), make decisions, and automatically route tasks or trigger process actions — embedding intelligent automation right into workflows.
 * Expanded AI model support & flexibility — You can now pick which generative AI model (e.g., newer ones) each AI Skill uses, via inference profiles, providing more control over performance, compliance and governance.
 * Long-running AI Skill execution — New option to execute generative-AI tasks in “Long Running” mode (for large inputs/responses) so you don’t hit timeout issues.
 * New a!genAiModels() function — Helps you dynamically get the list of available AI models and lets you build more flexible AI-enabled solutions.

## 51. What is AI skill types and use cases?
Prompt - Text, EML File, PDF, Jpeg, TIFF, PNG
IDP - PDF, Jpeg, TIFF, PNG
ML - PDF, EML

## 52. Types of AI Skill ?
Document Classification
Document Extraction
Email Classification

## 53. What are the AI Components, What AI Model does Appian Use?
Anthropic AI is earlier used, Now In Appian we can able to use
{"Claude 3 Haiku", "Claude 3.5 Sonnet", "Claude 3.7 Sonnet", "Claude Sonnet 4", "Claude Sonnet 4.5", "Claude Haiku 4.5"}

## 54. What is Agile\Waterfall method?
 * Agile: Agile is an iterative and incremental development methodology. Work is delivered in small cycles (Sprints) with continuous feedback.
 * Waterfall: Waterfall is a linear and sequential project development model. Each phase must be completed fully before moving to the next.

## 55. What is Sprint duration and Sprint velocity?
 * Sprint Duration: A Sprint is a fixed time period in Agile (mainly Scrum) during which the team works to complete a set of user stories.
 * Sprint Velocity: Sprint Velocity is the measure of work done by a team in a sprint.

## 56. How to create new schema for appian what permission would require for that? 
When connected with database schema, We can select the database




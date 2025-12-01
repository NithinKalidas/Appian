## 1. How to download a document when it is unplublished?
from Appian 25.3 we can able to download the document by using a!documentDownloadLink(), for Lower environment through process model you need to write in DB and then download the Documents

## 2.What is the architecture of Appian?
Appian uses a 3-tier architecture where the UI is rendered with SAIL, business logic runs in Appian’s engines, and data is stored in Appian/external databases via the unified Data Fabric.
Process Execution Engine – Runs workflows
Content Engine – Documents & folders
Analytics Engine – Reports and metrics
Collaboration Engine – Tasks, news, discussions
Search Server – Full text search
Rules Engine – Evaluates expressions & SAIL
Data Fabric – Single virtual data layer

## 3. How many engines are present in appian default?
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


## 5. What are the deployment challenges you have faced?
Precedents missing
Common Packages missing

## 6. What are necessary checks for pre deployement and post deployment?
PreDeployment :
Create all necessary DB scripts and organise to one script
Checking Missing Precedents
Scheduler Process Model check
Security Summary
Proper exporting of all objects
Inspecting all objects and fixing issues if any
Importing the objects
Force Sync (in custom properties, sync enable)
Object Version conflicts
Deployment Fails Due to Locked Objects.
Circular Dependencies Between Objects.
Import Customisation File ICF Not Applied or Misconfigured.


Post Deployment :
Security Checks
Error in Logs
Change in Constant for Post scheduler Process

## 7. How do you check is document exist or not in your application?
getcontentobjectdetailsbyid()

## 8. How do you delete the document which is older than 2 years, when your unaware of document Id?
Using "Delete Documents Created Before Date" smart service in the PRocess model, by chosing the 

## 9. What are the stages appian recommend to use in Project ?
Dev (Development)
SIT (System Integration Testing)
UAT (User Acceptance Testing)
Pre Production
Production

## 10. What is Portal and how does sign in and sign out works?
Business user who does not have login credential in appian but able to access
Eg: Complaince related to water shortage, Electricity shortage

## 11.How do you implement Optimistic locking in appian?
In CDT Based approch, we can add a new column Version and default set to zero, In XSD package add @Version and import and then using trigerrs we can create those versions.

## 12. how to configure Single click document download?


## 13. Suppose we need to update 1000 rows of data on daily basis in a week how can we do that or what is the optimised way to prevet without affecting the Performance?
update using batch wise in non business hours

## 14. Suppose we have 1000 entries in excel file and how can i dumb to 5 different database?
Read excel smart service and segreagate the DB, Write to data store entity for each data write as schema might differ.

## 15. Different Types of prod Issues you have encounter?
PV Variable was mis configured, due to which calculation went missing, using report we took the process instances 

## 16. Which Appian objects Permission level or Securities Inheritance?

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


## 17. how do you modify the securities for 1000 appian objects?
Using security summary (under gear symbol) we can cofigure

## 18. Differnce between optimising Performance through admin console and through interface objects?
| Admin Console                          | Interface Object                          |
|----------------------------------------|-------------------------------------------|
| Rule execution monitoring              | Monitor query calls                       |
| Monitor resource allocation            | Optimizing rule inputs & local variables  |
| Complete environment monitoring        | Specific object monitoring                |


## 19. How 2 environment can we configured for compare and deploy method for development?
In Appian Admin console -> Devops -> Infrastructure -> Add new Environment

## 20. difference between tomcot logs and performance logs?
Tomcot logs: 
Server startup/shutdown details
Application deployment errors
Java exception stack traces

Performance Logs: 
Use request response Times
Process/rules execution time
Database query performance

## 21. Huge amount of data in external system, how will you use in appian application?
 * CDT based approach -> Integration Object -> Call data and use integration object in PM and store in DB and use the data
 * Record Type: Create record with web service menthod, inside webservice need to create integration (before creating integration, connected system and you need to configure data source as well). sync aslo can be enabled and will be achieved through batching

## 22. What are new appian features or new release (25.4)?
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

## 23. What is AI skill types and use cases?

## 24. What is decision table and say some use case scenario?
A Decision Table in Appian is a rule-based grid used to evaluate multiple conditions and return results without complex nested if() or case() logic.
It provides a tabular visual framework to make business decisions clear, maintainable, and reusable.
| Columns        | Purpose                                                               |
| -------------- | --------------------------------------------------------------------- |
| Input Columns  | Conditions to evaluate (state, amount, age, score, etc.)              |
| Rule Rows      | Each row represents a rule set                                        |
| Output Columns | Result when a rule is matched                                         |
| Hit Policy     | Defines whether to return first match, all matches, or collect values |

## 25. How do you handle errors in Portal?
Portals do NOT support out-of-the-box Appian error dialogs. Portals run outside the Appian environment
Errors must be handled manually in the interface and integrations

## 26. If any request is submitted through an user by portal, how can we find them?
By creating a request id which can be configured through email id or phone number using unique set of constraints

## 27. What is the difference between text, long text and extra long text

## 28. what is health chekup and use case?

## 29. What is monitoring and use case?

## 30. What is Use case of Customisation file and what is environment constant / (connected System)?

## 31. How to deploy group to higher environment? Will Group Id Changes when we deploy to higher environment?
Groups/Users need to configured manually, (NR)

## 33. How to deploy service account to higher environment to higher environment?

## 34. What are the limitations for business user?
In Appian, a Business User (usually someone from the business team who reviews tasks and data but does not design/develop applications) has limited access and capabilities compared to Designers / Administrators.

## 35. What is hot fix?
Hot fix is an bug of appian (NR)

## 36. What is difference between equal to and like operator?
Equal: The value must be exactly equal to the column value. Faster (can use index directly)
Like: Used for pattern-based match. LIKE is slower, especially if value starts with %

## 37. Delete related record action, how not to show error page and redirect? 

## 38. How to create new service Account?
Under Admin Console, In WEB Api Authentication we ccan create service account and authentication key as well

## 39. What are the AI Components, what AI Model does Appian Use?
Anthropic is used, Now In Appian we can able to use
{"Claude 3 Haiku", "Claude 3.5 Sonnet", "Claude 3.7 Sonnet", "Claude Sonnet 4", "Claude Sonnet 4.5", "Claude Haiku 4.5"}

## 40. How do you force deploy to next environment?
By Removing UUID/ Customisation File (NR)

## 43. What is Agile\Waterfall method?
Agile: Agile is an iterative and incremental development methodology. Work is delivered in small cycles (Sprints) with continuous feedback.
Waterfall: Waterfall is a linear and sequential project development model. Each phase must be completed fully before moving to the next.

## 44. What is Sprint duration and Sprint velocity?
Sprint Duration: A Sprint is a fixed time period in Agile (mainly Scrum) during which the team works to complete a set of user stories.
Sprint Velocity: Sprint Velocity is the measure of work done by a team in a sprint.

## 45. how to move document without changing its ID to next environment?
Can't be done, Documet Id is varies for different environment

## 46. How to create new schema for appian what permission would require for that?

## 47. What are Production bugs? How did you fix them?

## 49. How do you resolve write to records got errored out because of unique constraints ID?

## 50. An external Integration in experiencing timout when sending a large volume of data? How do you resolve?

## 51. how can you ensure that updating reccord creates a new entry instead of modifying the existing one

## 52. How do you handle the data after integration? How would you clean data from API response?

## 53. What is task log?

## 54. what is charts and what are its types in appian?
Chart are used to diagramatically represent the value
BAR CHART
COLUMN CHART
PIE CHART
LINE CHART
AREA CHART
SCATTER CHART

## 55. What is T24 and have you used in your application?
T24 (Temenos T24) is a core banking software developed by Temenos.
Customer onboarding
Account management
Loans & deposits
Payments & transactions
Interest & charges
Regulatory and financial reporting

## 57. DB driven vs process driven based approach?
 * Db Drivern : A DB-driven approach means data drives the state of the application instead of workflows.
 * Process models are minimized; most operations happen via records, smart services, write to data store, and interfaces.
Process Driven: A process-driven approach means the workflow (process model) is the center of the application.
All business logic, task assignments, and data updates are managed inside process models.

## 58. Process HQ?
In Appian, Process HQ (Process Headquarters) is a centralized monitoring and analytics capability used to get real-time visibility into business processes running in the system.

## 59. How do you create WEB API in REST?


## 61. 10 Approvers need to approve then only we need to proceed to next step? how to define them?
We can keep a script task and check is all completed through task status

## 62. Process is errored out? how do you check them?

## 63. why do we split tabel? why can't we store all in single DB?
Split tabel because it would create major performance, storage, consistency, scalability, and maintainability issues.
Databases follow Normalization, where data is split into related tables to avoid duplication and ensure efficiency.

## 64. What are the different licenses available and for what components are they provided?
k3.lic for engines
k4.lic for the data server

## 65. What are the different types of Appian installations and state their differences?
On-Premise: The physical hardware is with us and maintenance is also done by us.
On-Cloud: The physical hardware is with Appian, and Appian handles the maintenance. The URL will have "appiancloud" in it.
Hybrid: A combination of On-Premise and On-Cloud. For example, a training environment where the hardware is with Appian but maintenance is done by us.

## 66. What is the purpose of content, personalization, execution, and analytic engines?
Process Execution: Manages process execution and data for associated process models. Also referred to as exec, PX.
Process Analytics: Stores information relevant for reports on a process. Also referred to as analytics, PA.
Content: Stores metadata and security settings for documents and their organizational structures (communities, knowledge centers, and folders). The actual document content is stored on the file system. Also referred to as collaboration, collab, CO.
Personalization: Stores information about users, groups, group membership, and group types. Also referred to as groups, PE.

## 67. Why can users not be deleted or moved to another environment in Appian?
The license cost is based on the number of users per environment, and Appian maintains metadata based on users. Hence, users cannot be moved or deleted.


## 68.  Is an archived or deleted process available in the Process report?
No, Deleted process are removed permanently can't be undone, for archival process we can unarchive the process and we can able to get it report (NR, how to unarchieve, within how many days we can archieve)

## 69.  Will hidden variable data be displayed in the process report?
No.

## 70. What is the purpose of user start page?
When configured, this allows the user to directly log in to the given site rather than the Tempo page.

##  . If a user belongs to multiple groups that have different start pages configured, his start page will be the highest one in the grid that corresponds to a group that he belongs to.
TRUE

##  . What are the different datatypes available in Appian? Give examples for each.
Primitive: Int, Text, Date, DateTime
Appian Object: Application, Process Model
Complex: PagingInfo, DataSubset
Custom Data Type

##  . What are the benefits of modular coding?
Reusability of objects
Easy change management
Easy debugging
Reduced number of lines per interface

##  . What is a customization file?
The customization file is used to provide values to the environmental constant and connected systems when deploying to another environment so that the value changed isn't missed.

## . Tempo vs Site?

Default by appian
View/See all tasks
Can't add logo
No changes can be done

Site:
Can configure based on business need
Security acess can be modified (user access views can be designed)
Can Add Logo
Changes can be Done to the site based on requirement


## . Types of AI Skill ?
Document Classification
Document Extraction
Email Classification

## . How much doc size appian can send to external document?
Request Body : Can't exceed 5 mb
Base 64 : Combined size of file 75 mb
Binary files : 250 Mb

## What is UUID and does it change for different environment?
UUID is an Universally Unique Identifier - remains stable acrosss different environment








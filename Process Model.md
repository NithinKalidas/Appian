# Appian Interview Question

## 1. Difference Between Start Process and Sub Process? Explain with real time example?
Start Process: The started process is load-balanced and may run on a different execution engine.
Sub Process: Runs on the same execution engine as the parent.

## 2. Production Issues you came across in PM and how did you handle them?

## 3. Best Practice In PM?
 * Deleting Inactive Records: Remove the Soft deleted data
 * Using 30 Nodes Per Process and trying to use in Asynchronous, so that process might execute in different engine.
 * Using Activity chaining on necessary parts only (as Activity chaining pushes the CPU to act very faastly with no delays) (If querying can be set outside activity chaining we need to use in that)
 * Handling Security, Alerts and Data management(archival and delete based on user interaction or system interaction)
 * Always take data from DSE or Records to get the primary key or what it writes
 * usage of quick task for Confirmation screen and hidden variables to reduce the data load in reports
 * setting up up unique name for process display name and process instance name (what is process display)
 * Setting up timer to user interaction node
 * Lane Assignments for user Input task and system task and Proper Annotation
 * Short lived Process model
 * Usage of terminate node rather than end node

## 4. Difference Between Start Process Asyncronous and Sub Process Asyncronous?

## 4. Difference Between  Asyncronous and syncronous Process?
Sync: Parent Process will wait for its child process to complete. Eg: used for sequential steps, business calculation logic, confirmation screen 
ASync: Parent Process trigerrs the child process and runs in parallel. Eg: Sending email 

## 5. What is MNI and where do you use them?

## 6. What is quick task and how do you configure?

## 7. what is hidden variable? How to get its report?

## 8. What are the ways to start a Process Model?
Using Actions
Using Sites
Records (Action & Related Action)
Start Process
Sub process
Start Process Link
Start Form
Timer (Daily or nightly process)
Using Email
Using Web API
Using End/Terminate Node
Debugging Mode

## 9. What are gates and its type? Explain with real time use case?
| Gateway Type                           | Description / Behavior                                                                                                                                | Real-Time Use Case / Example                                                                                                                                     |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **XOR (Exclusive Decision / Merge)**   | Diverging: Only **one outgoing path** is taken based on condition. <br> Merging: Only **one incoming flow** continues.                                | **Leave Request Process:** If leave ≤ 2 days → Auto-approve; else → Send to manager for approval. Only one path is followed.                                     |
| **OR (Inclusive Decision / Merge)**    | Diverging: **One or more outgoing paths** can be taken if their conditions are true. <br> Merging: Accepts **all incoming flows** that meet criteria. | **Insurance Claim:** If damage > 50% → Approve claim **and** notify legal team; if damage < 50% → Approve claim only. Multiple paths may execute simultaneously. |
| **AND (Parallel Fork / Join)**         | Diverging: Starts **all outgoing paths simultaneously**. <br> Merging: Waits for **all incoming paths** before continuing.                            | **Employee Onboarding:** After hiring approval → Create IT account, assign mentor, send welcome kit **all at the same time**.                                    |
| **COMPLEX (Complex Decision / Merge)** | Advanced control: You can define **custom rules** for outgoing and incoming flows (e.g., accept N out of M incoming flows).                           | **Multi-Reviewer Approval:** 4 reviewers evaluate a document; process continues once **any 3 approve**. Complex conditions determine the flow.                   |

## 10. What is Activity Chaining and What are its limitations?
Limitation: Performance reduce when the execution of node takes more time and sometimes it might break as well which impact in user experience

## 11. Your Process has a long activity chaining how do you resolve them?
Avoid query data if it is non essentials (NR)

## 12. What is exception and esclation ? real time use case?
Exception: An exception occurs when a process node fails, encounters an error,
Eg: In Employee Onboarding Process, A node writes employee data to the database, The DB connection fails or required fields are missing →
Exception triggers: Notification to admin, Error logging, Retry mechanism

Esclation: An escalation occurs when a task is not completed within a specified time (SLA breach)
A loan approval task is assigned to a manager and SLA set for 24 hours. If the manager doesn’t act within 24 hours.
Escalation occurs automatically:
Reassigns the task to Senior Manager
Sends reminder emails
Triggers escalation process

## 13. why to use process start form rather than user input task?
Starts the process model when button action trigerred
Reduces the utilisation of Appian Memory unit/Resource of appian engine (NR)

## 14. Limitations of Process start form? when can we use user input task?
When used in MNI user input task need to be used
When quering the data inside the process model before the user interaction starts (Not required , NR)

## 15. How do you convert a word to document?
using docx to pdf converter through process model

## 16. how do you send document to external system?
Using integration we can send through either base 64 or binary 
Using a smart service send document to external system (NR)

## 17. what is task log?
Task Log is a handling the task through DB Driven rather than Appian default assignment 
Which Decrease the RAM memory and increase in Performance as all the task are handled through storages in DB

## 18. How do you use task log in DB instead of task management?
Everytime we can query the data and showcase to the dependent user and for any change it can be easily reset through DB

## 19. You have multiple start and sub process need to be used, what is the approach you use? (top to bottom or bottom or top)
 
## 20. Third Part want to trigger an Stores Procedure? how do you implement them?
Create WebAPI of start process type and implement SP

## 21. How to schedule a PM at specifi time?
In start Process by scheduling the time and interval of run (NR)

## 22. How to optimise the PM having 200 Nodes?
Need to create reusable process model and call the process model again
using sub process asynchronous to reduce the load the engine as it may execute in different engine

## 23. How to bring back unarchival Process?

## 24. While calling a Sub process what is the difference between passing a variable as reference and a value?

## 25. Does activity chaining decrease the Process, if yes how do you overcome?

## 26. When to use short lived process and long lived Process?

## 27. What is the limitaion of MNI?

## 28. There is a 1000 Instances on the Production and you want to edit the variable value, how can we achieve it instad of manual approach?
Get data of active process instances through report and using setexternalpv we can modify the process variable value and we can restart the process instance using (NR)

## 29. Usage of Lane in PM?
For Eas readability to separate between User input task and system acted task

## 30. How will you deploy a scheduler PM?
Create an Environment constant in boolean to act as a switch and Set up as False and handle in XOR Gate and after deployment change the environmental constant to true

## 31. What is quick task? How to query the data in PM, when quick task is enabled? where is quick task used?
It is an on-demand Task, which does not appear in task tab and only performed when activity is chained.
We can't (check NR)
Eg: Confirmation screen to display the request number

## 32. How do you handle retry machanism in PM for integration?
Setting Up retry after failed attempt after (mostly when statuc code is failed with 500) few minutes and also write the log for the integration when ever hits for analysis.

## 33.What is the difference between End Node vs terminate Node?

## 34. Long activity chains - greater than 5 seconds between attended activities - are strongly discouraged because they have both an adverse effect on the performance of the system at scale and the experience of the user. True or False?
TRUE

## 35.What is a quick task?
A quick task is an on-demand task. The task does not appear in the task tab and can only be performed when activity is chained. If the task is closed without any action taken, it cannot be retrieved. The quick task stays ACTIVE when not performed. When quick task is enabled, a tilde (~) will be visible in the user input task.

14. What is the difference between escalation and exception?
Escalation: Used to take an alternate approach/report it to others when a task isn't performed by the assignees after a certain time.
Exception: Used to kill the task and proceed with the flow when the task isn't performed by the assignee after a certain time.

16. What is the difference between User Input Task and Process Start Form? When should one use Process Start Form?
Process Start Form: Starts the instance only when a button with the submit attribute set to true is clicked. It avoids unnecessary instances and should be used when the user has the choice to submit the form, as it does not appear as a task in the task queue.
User Input Task: Used when the task needs to be assigned to specific users.

## 36.When should XOR and OR gateways be used?
XOR: Used when only the first true path should be executed based on the given conditions.
OR: Used when all the true paths should be executed based on the given conditions.

## 37. What is the purpose of lane assignments?
Lane assignments provide assignments for unattended nodes (nodes with no user interaction). The assignment is given to "Whoever designed the process" because not all unattended nodes can be performed by the basic user. Designers have all privileges, so assignments are made in that manner.

## 38. Why should we build short-lived processes?
Short-lived processes are recommended because longer processes accumulate in the execution engine, taking up RAM space. Longer active processes use more engine space, which can lower system performance. Short-lived processes split various steps (initiation, approvals, etc.) into different models and are called using Start Process/asynchronous subprocesses, making the processes independent and not waiting for the child processes.

## 39. What is the difference between asynchronous subprocess and Start Process?
Asynchronous Subprocess: The parent does not wait for the child to complete. Both the parent and child processes run in the same engine.
Start Process: The parent does not wait for the child to complete. The parent and child processes run in the same or different engines based on the load (Appian has 3 execution engines by default).

## 40. What is the difference between process model and process?
Process Model: The model is the object where the flow can be defined/designed.
Process: Process/Instance is the implementation of the design.

## 41. What is the purpose of alerts in Process model?
Alerts in the model are used to notify the defined users about errors in the instance. The target users are the admins of the app as they are responsible for maintaining the app. This can be defined using a constant so that change management can be easier.

## 41. Why do we need the data management? When should one select the delete option in data management?
Data Management is used to clear the instances stored in the execution engine. The instance can either be archived or deleted. When there is no user interaction in a process, that process can be deleted. Data management happens only for completed or canceled instances.

## 41. What is the difference between end and terminate node? When to use End node?
End Node: Completes only the path that hits it while all the other paths are active. This is used when the whole process is to be completed when all the other paths are completed.
Terminate Node: Completes all the paths once it is hit. Even in a single flow, the terminate node is recommended as even the errored instances of the node are completed when the terminate node is hit.

## 42. What is the purpose of process report?
It provides information about the process models, process instances, or active tasks and other activities. This is mainly used for analysis purposes.

## 43. What are the different types of process report?
Process models
Process instances
Active tasks

## 44. What is the function used to get the results from process report?
a!queryProcessAnalytics()

## 45. What is the purpose of activity chaining? What is the maximum limit?
Activity chaining is used between more than one task performed by the same user so that the user can act upon the tasks without any delay. The maximum limit is default 50 and max 100 unattended nodes between two attended nodes.

## 46. When a process with an active task is paused, will the task be available to the user to perform?
No. An error will be shown to the user when the task is opened.

## 47. Will timer node execute when the instance is paused?
Yes

## 48. What is a MNI and its best practices?
Multiple Node Instance (MNI) is used to create multiple instances of a node. This is done when the functionality of the node is to be repeated for various inputs. The best practice is to do a null check of the variable before the MNI and if the variable has more than 1000 values, it is recommended to do batch

## 49. What are Gateways and their purpose?
Gateway nodes allow you to evaluate different criteria to make decisions on which path(s) your workflow should follow – as well as how many instances are allowed to follow each optional path. Click here to know about various gateways.

## 50. The triggers that can be added to a start event are:
Receive Message
Timer

## 51 . What is the difference between Task Assignee and Task Owner?
Task Assignees: The people for whom the task is being assigned.
Task Owner: The person who accepts a group task.

## 52. What should be the reassignment privilege for basic users?
The reassignment privilege should be No privilege as basic users should not have the ability to reassign the task to anyone in the system, and if reassignment is enabled, the tracking of it becomes difficult. This can be set in the Assignment tab of User input task under "Set Reassignment Privilege".

## 53. Can the default task assignment mail be disabled?
Yes, under the assignment tab the option can be unchecked.

## 54. Scenario where record type over a tradition CDT Method?
Records -> Speed of development is higher as foreign key mapping are easily configured by inbuilt relationship
Usage of views, creation of record summary and able to configure custom field for aggregate function (NR)

## 54. What is the maximum number of nodes and variables allowed per process model?
30 Nodes and 50 Variables

## 55. If task delayed for 24 hrs it shouuld assign to hire manager (NR/Ls Interview Ques)

## 62. When Process is errored out? how do you check them?

## 58. Process HQ?
In Appian, Process HQ (Process Headquarters) is a centralized monitoring and analytics capability used to get real-time visibility into business processes running in the system.

## 69.  Will hidden variable data be displayed in the process report/History?
No.

## 68.  Is an archived or deleted process available in the Process report?
No, Deleted process are removed permanently can't be undone, for archival process we can unarchive the process and we can able to get it report (NR, how to unarchieve, within how many days we can archieve)

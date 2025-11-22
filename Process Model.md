# Appian Interview Question

## 1. Difference Between Start Process and Sub Process? Explain with real time example?


## 2. Production Issues you came across in PM and how did you handle them?

## 3. Best Practice In PM?


## 4. Difference Between Start Process Asyncronous and Sub Process Asyncronous?

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

## 10. What is Activity Chaining and What are its limitations?

## 11. Your Process has a long activity chaining how do you resolve them?

## 12. What is exception and esclation ? real time use case?

## 13. why to use process start form rather than user input task?

## 14. Limitations of Process start form?

## 15. How do you convert a word to document

## 16. how do you send document to external system

## 17. what is task log?

## 18. How do you use task log in DB instead of task management

## 19. You have multiple start and sub process need to be used, what is the approach you use? (top to bottom or bottom or top)
 
## 20. Third Part want to trigger an Stores Procedure? how do you implement them?

## 21. How to schedule a PM at specifi time?

## 22. How to optimise the PM having 200 Nodes?

## 23. How to bring back unarchival Process?

## 24. While calling a Sub process what is the difference between passing a variable as reference and a value?

## 25. Does activity chaining decrease the Process, if yes how do you overcome?

## 26. When to use short lived process and long lived Process?

## 27. What is the limitaion of MNI?

## 28. There is a 1000 Instances on the Production and you want to edit the variable value, how can we achieve it instad of manual approach?

## 29. Usage of Lane in PM?

## 30. How will you deploy a scheduler PM?

## 31. What is quick task? How to query the data in PM, when quick task is enabled?

## 32. How do you handle retry machanism in PM for integration?

## 33.What is the difference between End Node vs terminate Node?

## 34.12. Long activity chains - greater than 5 seconds between attended activities - are strongly discouraged because they have both an adverse effect on the performance of the system at scale and the experience of the user. True or False?
TRUE

## 35.What is a quick task?
A quick task is an on-demand task. The task does not appear in the task tab and can only be performed when activity is chained. If the task is closed without any action taken, it cannot be retrieved. The quick task stays ACTIVE when not performed. When quick task is enabled, a tilde (~) will be visible in the user input task.

14. What is the difference between escalation and exception?
Escalation: Used to take an alternate approach/report it to others when a task isn't performed by the assignees after a certain time.
Exception: Used to kill the task and proceed with the flow when the task isn't performed by the assignee after a certain time.
15. What is the difference between User Input Task and Process Start Form? When should one use Process Start Form?
Process Start Form: Starts the instance only when a button with the submit attribute set to true is clicked. It avoids unnecessary instances and should be used when the user has the choice to submit the form, as it does not appear as a task in the task queue.
User Input Task: Used when the task needs to be assigned to specific users.

## 36.When should XOR and OR gateways be used?
XOR: Used when only the first true path should be executed based on the given conditions.
OR: Used when all the true paths should be executed based on the given conditions.

## 37. What is the purpose of lane assignments?
Lane assignments provide assignments for unattended nodes (nodes with no user interaction). The assignment is given to "Whoever designed the process" because not all unattended nodes can be performed by the basic user. Designers have all privileges, so assignments are made in that manner.

22. Why should we build short-lived processes?
Short-lived processes are recommended because longer processes accumulate in the execution engine, taking up RAM space. Longer active processes use more engine space, which can lower system performance. Short-lived processes split various steps (initiation, approvals, etc.) into different models and are called using Start Process/asynchronous subprocesses, making the processes independent and not waiting for the child processes.

23. What is the difference between asynchronous subprocess and Start Process?
Asynchronous Subprocess: The parent does not wait for the child to complete. Both the parent and child processes run in the same engine.
Start Process: The parent does not wait for the child to complete. The parent and child processes run in the same or different engines based on the load (Appian has 3 execution engines by default).

##  . What is the difference between process model and process?
Process Model: The model is the object where the flow can be defined/designed.
Process: Process/Instance is the implementation of the design.

##  . What is the purpose of alerts in Process model?
Alerts in the model are used to notify the defined users about errors in the instance. The target users are the admins of the app as they are responsible for maintaining the app. This can be defined using a constant so that change management can be easier.

##  . Why do we need the data management? When should one select the delete option in data management?
Data Management is used to clear the instances stored in the execution engine. The instance can either be archived or deleted. When there is no user interaction in a process, that process can be deleted. Data management happens only for completed or canceled instances.

##  . What is the difference between end and terminate node? When to use End node?
End Node: Completes only the path that hits it while all the other paths are active. This is used when the whole process is to be completed when all the other paths are completed.
Terminate Node: Completes all the paths once it is hit. Even in a single flow, the terminate node is recommended as even the errored instances of the node are completed when the terminate node is hit.

##  . What is the purpose of process report?
It provides information about the process models, process instances, or active tasks and other activities. This is mainly used for analysis purposes.

##  . What are the different types of process report?
Process models
Process instances
Active tasks

##  . What is the function used to get the results from process report?
a!queryProcessAnalytics()

##  . What is the purpose of activity chaining? What is the maximum limit?
Activity chaining is used between more than one task performed by the same user so that the user can act upon the tasks without any delay. The maximum limit is default 50 and max 100 unattended nodes between two attended nodes.

##  . When a process with an active task is paused, will the task be available to the user to perform?
No. An error will be shown to the user when the task is opened.

##  . Will timer node execute when the instance is paused?
Yes

##  . What is a MNI and its best practices?
Multiple Node Instance (MNI) is used to create multiple instances of a node. This is done when the functionality of the node is to be repeated for various inputs. The best practice is to do a null check of the variable before the MNI and if the variable has more than 1000 values, it is recommended to do batch

##  . What are Gateways and their purpose?
Gateway nodes allow you to evaluate different criteria to make decisions on which path(s) your workflow should follow – as well as how many instances are allowed to follow each optional path. Click here to know about various gateways.

##  . The triggers that can be added to a start event are:
Receive Message
Timer

##  . What is the difference between Task Assignee and Task Owner?
Task Assignees: The people for whom the task is being assigned.
Task Owner: The person who accepts a group task.

##  . What should be the reassignment privilege for basic users?
The reassignment privilege should be No privilege as basic users should not have the ability to reassign the task to anyone in the system, and if reassignment is enabled, the tracking of it becomes difficult. This can be set in the Assignment tab of User input task under "Set Reassignment Privilege".

##  . Can the default task assignment mail be disabled?
Yes, under the assignment tab the option can be unchecked.

##  . What is the maximum number of nodes and variables allowed per process model?
30 Nodes and 50 Variables

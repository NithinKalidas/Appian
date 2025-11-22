# Appian Interview Question

## 1. Difference Between Start Process Sub Process? Explain with real time example?


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

## 38.

## 39.

## 40.


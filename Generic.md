## 1. How to download a document when it is unplublished?

## 2.What is the architecture of Appian?

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

## 4. How do you deploy to higher environment? When your doing for the first time?

## 5. What are the deployment challenges you have faced?

## 6. What are necessary checks for pre deployement and post deployment?

## 7. How do you check is document exist or not in your application?

## 8. How do you delete the document which is older than 2 years, when your unaware of document  Id?

## 9. What are the stages appian recommend to use in Project ?

## 10. What is Portal and how does sign in and sign out works?

## 11.How do you implement triggers in appian?

## 12. how to configure Single click document download 

## 13. suppose we need to update 1000 rows of data on daily basis in a week how can we do that or what is the optimised way to prevet without affecting the Performance

## 14. Suppose we have 1000 entries in excel file and how can i dumb to 5 different database?

## 15. Different Types of prod Issues you have encounter?

## 16. Which Appian objects does not have Permission level or securities?

## 17. how do you modify the securities for 1000 appian objects

## 18. Differnce between optimising Performance through admin console and through interface objects?

## 19. How 2 environment can we configured for compare and deploy method for development?

## 20. difference between tomcot logs and performance logs?

## 21. Huge amount of data in external system, how will you use in appian application

## 22. What are new appian featuresor new release?

## 23. What is AI skill types and use cases?

## 24. What is decision table and say some use case scenario?

## 25. How do you handle errors in Portal?

## 26. If any request is submitted through an user by portal, how can we find them?

## 27. What is the difference between text, long text and extra long text

## 28. what is health chekup and use case?

## 29. What is monitoring and use case?

## 30. What is Use case of Customisation file what is environment constant?

## 31. How to deploy and group to higher environment? Will Group Id Changes when we deploy to higher environment?

## 32. How will you send document to external systems?

## 33. How to deploy service account to higher environment to higher environment?

## 34. What are the limitations for business user?

## 35. What is hot fix?

## 36. What is difference between equal to and like operator?

## 37. Delete related record action, how not to show error page and redirect? 

## 38. How to create new service Account?

## 39. What are the AI Components, what AI Model does Appian Use?

## 40. How do you force deploy to next environment?

## 41. What are record level securities?

## 42. What are the sutomisation file and how many things can be modified?

## 43. What is Agile\Waterfall method?

## 44. What is Sprint duration and Sprint velocity?

## 45. how to move document without changing its ID to next environment?

## 46. How to create new schema for appian what permission would require for that?

## 47. What are Production bugs? How did you fix them?

## 48. How do you approach Pessimistic locking in appain?

## 49. How do you resolve write to records got errored out because of unique constraints ID?

## 50. An external Integration in experiencing timout when sending a large volume of data? How do you resolve?

## 51. how can you ensure that updating reccord creates a new entry instead of modifying the existing one

## 52. How do you handle the data after integration? How would you clean data from API response?

## 53. What is task log?

## 54. what is charts and what are its types in appian?

## 55. What is T24 and have you used in your application?

## 56. Where do you use refresh variable and what are its constraints?

## 57. DB driven vs process driven based approach?

## 58. Process HQ?

## 59. How do you create WEB API in REST?

## 60. Difference between query record type and record type identifier?

## 61. 10 Approvers need to approve then only we need to proceed to next step? how to define them?

## 62. Process is errored out? how do you check them?

## 63. why do we split tabel? why can't we store all in single DB?

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
No.

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

##  . What are the things to be checked during deployment?
Missing Precedents
Security Summary
Proper exporting of all objects
Inspecting all objects and fixing issues if any
Importing the objects

##  . What is a customization file?
The customization file is used to provide values to the environmental constant and connected systems when deploying to another environment so that the value changed isn't missed.


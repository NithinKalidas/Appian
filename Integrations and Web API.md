# Integrations and WEB API

## 1. What is Web API, Integration and Connected system?
WEB API: Data/Resource sharing to external System
Integration: Ecternal system used by appian
Connected system: To store the credentials for integration (basic, WebApi Key, Oauth client grand 2.0)

## 2. Best Practices in Integration?
Handling the integration with status code
Using retry machanism for server unavailable and logging the details

## 3. Issues you faced in Web API or Integration and how did you overcome?

## 4. Authentication types and explain them?
Basic
Web API Key based
OAuth client Grand 2.0

## 5. In Web API how many smart service we can use as function?

## 6. How do you implement more than one web API smart service as function

## 7. In a!save how many smart service we can use 

## 8. Web API is called in button action, how do you prevent from multiple clicks for same web API call

## 9. Web API is called in button action, how do you distinguise it is calling the same request or different request when multiple clicks are happened?

## 10. In Integration Explain header, query parameters and request body and provide the sue case as well

## 11. How do you create service account to secure an API?

## 12. How do you create a OAuth service account?

## 13. What is the difference between SAML and LDAP?

## 14. What is difference between REST API vs SOAP API?

## 15. How to handle pagination and filtering in Web API Responses?

## 16. What is the difference between In Bound and Out Bound Authentication?

## 17. What authentication method does Appian support for integration?

## 18. How to get data of employee where age is between 20-25 and salary is greatter than 1,00,000 integration?

## 19. Can we deploy service account to higher environment? If yes, Hoe? If No how to overcome?

## 20. How to construct custom error message in integration?

## 21. Minimun level of Permission to execute web API? 

## 22. What is http and its methods?

## 23. Can we use get method to execute smart service?

## 24. Does get accept query parameter, if no what methods accept query parameter?

## 25. You want to query data using query paramter what method you use to query the data?

## 26. What are all information required for OAUTH 2.0 client grand requires to implement?

## 27. What are all information required for API Key authentication requires to implement?

## 28. How much size appian can send data to external system?

## 29. what is single sign on?

## 30. When should Web API, Integration/Web service be used?
Web API: Should be used when Appian's data is to be exposed to the external system.
Integration/Web Service: Used when external system's data is consumed by Appian.

## 31. When to use Web service and Integration?
Integration: Used when the data returned by the external system is in REST structure.
Web Service: Used when the data returned by the external system is in SOAP structure.

## 32. What is connected systems?
Connected Systems is an object to store the connection credentials used in integrations when connecting to an external system.

## 33. Third part want to trigger your DB/SP
By creating a WEB API in process model using the execute SP smart service we can achieve (NR)

## 34. Inbound Integration vs Outbound Integration?
Inbound: External system initiating call to pull data from appian or push data
Outbound: When Appian initiate the connection to external system


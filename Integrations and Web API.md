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

## 5. In Web API/ a!save how many smart service we can use as function?
Only one, To configure multiple we can provide the another smart services either in On success or on error

## 6. How do you implement more than one web API smart service as function

## 7. What are method of API types?
Put post patch delete get

## 8. How do you handle integration error ?
400
500

## 8. Web API is called in button action, how do you prevent from multiple clicks for same web API call?

## 9. Web API is called in button action, how do you distinguise it is calling the same request or different request when multiple clicks are happened?

## 10. In Integration Explain header, query parameters and request body and provide the use case as well?

## 11. How do you create service account?
In Admin console, under web API authentication we can create service account

## 13. What is the difference between SAML and LDAP?
| Feature                | **SAML**                    | **LDAP**                                   |
| ---------------------- | --------------------------- | ------------------------------------------ |
| Type                   | SSO Authentication Protocol | Directory Authentication Protocol          |
| Works where            | Web / Cloud apps            | Internal network / Organization            |
| Users authenticate via | Identity Provider (IdP)     | LDAP server (e.g., Active Directory)       |
| Shares                 | Authentication assertion    | Username & password validation             |
| Stores credentials     | No                          | Yes                                        |
| Setup                  | More complex                | Relatively simpler                         |
| Ideal for              | SSO across multiple apps    | Centralized authentication within intranet |
| Appian usage           | Appian SSO login via IdP    | Appian user authentication via AD          |


## 14. What is difference between REST API vs SOAP API?
| Feature                  | **REST API**                                                       | **SOAP API**                                                                      |
| ------------------------ | ------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| **Full Form**            | Representational State Transfer                                    | Simple Object Access Protocol                                                     |
| **Architecture Style**   | Architectural style                                                | Protocol                                                                          |
| **Communication Format** | JSON, XML, HTML, plain text                                        | Strictly XML                                                                      |
| **Transport Protocol**   | Works over HTTP/HTTPS (also FTP etc.)                              | Works over multiple protocols (HTTP/HTTPS, SMTP, etc.) but mainly HTTP            |
| **Message Format**       | Lightweight, human-readable                                        | Heavy, verbose XML messages                                                       |
| **Performance**          | Fast due to less overhead                                          | Slower due to large XML and strict rules                                          |
| **Security**             | Relies on HTTPS + custom security                                  | Very high — WS-Security, built-in standards                                       |
| **State Management**     | Stateless (default), can be stateful                               | Stateful by nature                                                                |
| **Caching**              | Supported (improves performance)                                   | Not supported                                                                     |
| **Use Case Style**       | Highly flexible — CRUD operations                                  | Strict — enterprise-level operations                                              |
| **Learning Curve**       | Easy                                                               | Complex                                                                           |
| **Best Uses**            | Public APIs, mobile apps, microservices, lightweight communication | Financial, banking, telecom, government where high security + compliance required |


## 15. How to handle pagination and filtering in Web API Responses?

## 16. What is the difference between In Bound and Out Bound Authentication?

## 17. What authentication method does Appian support for integration?
| Authentication Type                                            | Description / Usage                                                                                                                           |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **None**                                                       | No authentication required (public APIs).                                                                                                     |
| **Basic Authentication**                                       | Username + password encoded in Base64.                                                                                                        |
| **API Key Based Authentication**                               | Token or API key passed in header or query parameter.                                                                                         |
| **OAuth 2.0**                                                  | Recommended for secure enterprise integrations. Appian supports OAuth grant types: Authorization Code, Client Credentials, and Refresh Token. |
| **JWT Token / JSON Web Token**                                 | Token generated using private key (often used with Google APIs / Identity Providers).                                                         |
| **SAML (for SSO login, not for integration calls)**            | Used for user authentication into Appian, not for outbound integration.                                                                       |
| **Client Certificate Authentication (Mutual TLS / 2-way SSL)** | Appian sends a certificate to authenticate with the external service.                                                                         |
| **AWS Signature v4**                                           | Used to connect securely with AWS services (S3, Lambda, etc.).                                                                                |
| **Preconfigured Connected System Authentication**              | Reusable credential objects that manage authentication securely.                                                                              |

## 18. How to get data of employee where age is between 20-25 and salary is greatter than 1,00,000 integration?

## 19. Can we deploy service account to higher environment? If yes, Hoe? If No how to overcome?

## 20. How to construct custom error message in integration?
In Response, under Error Handling 
turn on "OverRide and define all error conditions"
We can set up success criteria and error message based on the status code

## 21. Minimun level of Permission to execute web API? 
Viewer Access but Can't able to upload document(NR)

## 22. What are the http methods supported in appian?
| HTTP Method | Usage in Appian                                                   | Typical Use Case                             |
| ----------- | ----------------------------------------------------------------- | -------------------------------------------- |
| **GET**     | Retrieve data from an external system or return data in a Web API | Get record / fetch list / search details     |
| **POST**    | Create new resource or send data to external system               | Create user / submit form / upload file      |
| **PUT**     | Update a resource by replacing the full dataset                   | Update full customer record                  |
| **PATCH**   | Update only specific fields of a resource                         | Update only email / status / phone number    |
| **DELETE**  | Remove a resource from external system                            | Delete record / cancel request / remove user |
 
## 23. Can we use get method to execute smart service?
No, To execute any smart service we need Post/Put/Patch

## 24. Does get accept query parameter, if no what methods accept query parameter?
GET is the standard method for query parameters.
Other methods (POST, PUT, PATCH, DELETE) typically use request body to send data, not query parameters.

## 25. You want to query data using query parameter what method you use to query the data?
If you are querying an external system, use the GET HTTP method. You pass query parameters in the URL: by adding "\" or "?"

## 26. What are all information required for OAUTH 2.0 client grand requires to implement?
| Required Information                                     | Purpose                                                                               |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Token URL (Authorization Server / Identity Provider)** | URL where Appian will request an access token                                         |
| **Client ID**                                            | Application identifier issued by the authorization server                             |
| **Client Secret**                                        | Password associated with the Client ID (kept securely)                                |
| **Grant Type**                                           | Must be **Client Credentials**                                                        |
| **Scope (if required)**                                  | Permission levels requested for the access token                                      |
| **Resource URL (optional, depending on provider)**       | Protecting resource ID to include in token request (used by Azure AD / AWS sometimes) |
| **API / Endpoint URL (target API)**                      | The actual service endpoint Appian will call using the token                          |
| **Token Type**                                           | Bearer token (typically) to include in Authorization header                           |


## 27. What are all information required for API Key authentication requires to implement?
| Required Information                  | Purpose                                                                                        |
| ------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **API Key / Token**                   | The secret key used to authorize the request                                                   |
| **Location to send the key**          | Where the API key must be included (usually Header, sometimes Query parameter or Request body) |
| **Header / Param Name**               | Exact field name expected by API provider (e.g., `Authorization`, `x-api-key`, `apiKey`)       |
| **Endpoint URL**                      | API URL you will connect to                                                                    |
| **HTTP Method**                       | GET / POST / PUT / PATCH / DELETE                                                              |
| **Request Body format (if required)** | JSON / XML / form-data / none                                                                  |
| **Expected Response Format**          | JSON / XML (used for parsing in Appian)                                                        |


## 28. How much size appian can send data to external system?
 * Request Body : Can't exceed 5 MB
 * Base 64 : Combined size of File 75 MB
 * Binary Files : 250 Mb

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

## 35. How Do you Handle Versioning in Web API?
Include the version number in the API endpoint path.
When creating the Web API, name the endpoint with the version prefix:
vl_getEmployeeDetails
v2_getEmployeeDetails

## 36. Can we import third-party data into Appian
without a Connected System?
Yes, You can connect to a third-party API without using a Connected System if:
The API is not secured (e.g., public/open API)
or
It uses Basic Authentication, where you
manually include credentials in the request.

## 50. An external Integration in experiencing timout when sending a large volume of data? How do you resolve?

## 52. How do you handle the data after integration? How would you clean data from API response?

## 59. How do you create WEB API in REST?

## 38. How to create new service Account?
Under Admin Console, In WEB Api Authentication we can create service account and authentication key as well



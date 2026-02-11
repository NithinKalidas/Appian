# Integrations and WEB API

## 1. What is Web API, Integration and Connected system?
WEB API: Data/Resource sharing to external System
Integration: Ecternal system used by appian
Connected system: To store the credentials for integration (basic, WebApi Key, Oauth client grand 2.0)

## 2. Best Practices in Integration?
Handling the integration with status code
Using retry machanism for server unavailable and logging the details

## 3. Issues you faced in Web API or Integration and how did you overcome?
 * Timeout and network issues (Implemented retry logic for safe APIs)
 * Duplicate API calls due to multiple button clicks (Multiple clicks triggered duplicate API calls, leading to repeated transactions)
 * Data mapping and type mismatch (Integration failures due to incorrect data types (text vs number, date formats))

## 4. Authentication types and explain them?
 * Basic
 * Web API Key based
 * OAuth client Grand 2.0

## 5. In Web API/ a!save how many smart service we can use as function?
Only one, To configure multiple we can provide the another smart services either in On success or on error

## 6. How do you handle integration error?
| Code Type | Reason        |
| --------- | ------------- |
| 1xx       | Informational |
| 2xx       | Success       |
| 3xx       | Redirection   |
| 4xx       | Client issue  |
| 5xx       | Server issue  |

## 7. What are method of API types and methods supported in appian?
| Method | Operation        | Idempotent | Use Case       | Usage in Appian                                                   | Typical Use Case                             |
| ------ | ---------------- | ---------- | -------------- | ----------------------------------------------------------------- | -------------------------------------------- |
| GET    | Read             | Yes        | Fetch data     | Retrieve data from an external system or return data in a Web API | Get record / fetch list / search details     |
| POST   | Create           | No         | New record     | Create new resource or send data to external system               | Create user / submit form / upload file      |
| PUT    | Update (full)    | Yes        | Replace record | Update a resource by replacing the full dataset                   | Update full customer record                  |
| PATCH  | Update (partial) | No         | Modify fields  | Update only specific fields of a resource                         | Update only email / status / phone number    |
| DELETE | Remove           | Yes        | Delete record  | Remove a resource from external system                            | Delete record / cancel request / remove user |

## 8. Web API is called in button action, how do you prevent from multiple clicks for same web API call?
In critical flows like payments or submissions, we handle this at both UI and API levels. The UI disables the button after the first click, and the backend ensures idempotency using unique transaction identifiers to avoid duplicate processing.

## 9. Web API is called in button action, how do you distinguise it is calling the same request or different request when multiple clicks are happened?
We distinguish between the same request and a different request by using a unique request identifier (idempotency key) and validating it on the backend. If multiple clicks send the same identifier, the backend treats them as the same request; if the identifier is different, it is processed as a new request.
Additionally, a timestamp-based threshold is applied—if the same payload is received within a short time window (for example, 2–3 seconds), it is identified as a duplicate request and ignored.”

## 10. In Integration Explain header, query parameters and request body and provide the use case as well?
Headers carry metadata and authentication, 
Query parameters control how data is fetched
Request body contains the business data sent to the API.

## 11. How do you create service account?
In Admin console, under web API authentication we can create service account

## 12. What is the difference between SAML and LDAP?
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

## 13. What is difference between REST API vs SOAP API?
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

## 14. How to handle pagination and filtering in Web API Responses?
use start index and batch size for pagination and use query parameter for filters

## 15. What authentication method does Appian support for integration?
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

## 16. How to get data of employee where age is between 20-25 and salary is greatter than 1,00,000 integration?
 * GET /employees?minAge=20&maxAge=25&minSalary=100000
 * Query Parameters:
minAge=20 → lower age limit, maxAge=25 → upper age limit , minSalary=100000 → salary filter

## 17. Can we deploy service account to higher environment? If yes, How? If No how to overcome?
No, Need to create new and add into the group

## 18. How to construct custom error message in integration?
In Response, under Error Handling, turn on "OverRide and define all error conditions", We can configure success criteria and error message based on the status code

## 19. Minimun level of Permission to execute web API? (NR)
Viewer Access but Can't able to upload document

## 20. How to create new service Account?
Under Admin Console, In WEB Api Authentication we can create service account and authentication key as well
 
## 21. Can we use get method to execute smart service?
No, To execute any smart service we need Post/Put/Patch

## 22. Does GET accept query parameter, if no what methods accept query parameter?
GET is the standard method for query parameters.
Other methods (POST, PUT, PATCH, DELETE) typically use request body to send data, not query parameters.

## 23. You want to query data using query parameter what method you use to query the data?
If you are querying an external system, use the GET HTTP method. You pass query parameters in the URL: by adding "\" or "?"

## 24. What are all information required for OAUTH 2.0 client grand requires to implement?
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

## 25. What are all information required for API Key authentication requires to implement?
| Required Information                  | Purpose                                                                                        |
| ------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **API Key / Token**                   | The secret key used to authorize the request                                                   |
| **Location to send the key**          | Where the API key must be included (usually Header, sometimes Query parameter or Request body) |
| **Header / Param Name**               | Exact field name expected by API provider (e.g., `Authorization`, `x-api-key`, `apiKey`)       |
| **Endpoint URL**                      | API URL you will connect to                                                                    |
| **HTTP Method**                       | GET / POST / PUT / PATCH / DELETE                                                              |
| **Request Body format (if required)** | JSON / XML / form-data / none                                                                  |
| **Expected Response Format**          | JSON / XML (used for parsing in Appian)                                                        |

## 26. How much size appian can send data to external system?
 * Request Body : Can't exceed 5 MB
 * Base 64 : Combined size of File 75 MB
 * Binary Files : 250 Mb

## 27. What is single sign on?
SSO is a login mechanism where you sign in once and Securely access multiple applications using token-based authentication

## 28. When should Web API, Integration/Web service be used?
Web API: Should be used when Appian's data is to be exposed to the external system.
Integration/Web Service: Used when external system's data is consumed by Appian.

## 29. When to use Web service and Integration?
Integration: Used when the data returned by the external system is in REST structure.
Web Service: Used when the data returned by the external system is in SOAP structure.

## 30. What is connected systems?
Connected Systems is an object to store the connection credentials used in integrations when connecting to an external system.

## 31. Third part want to trigger your DB/SP?
By creating a WEB API in process model using the execute SP smart service we can achieve (NR)

## 32. Inbound Integration vs Outbound Integration?
Inbound: External system initiating call to pull data from appian or push data
Outbound: When Appian initiate the connection to external system

## 33. How Do you Handle Versioning in Web API?
When creating the Web API, Include the version number in the API endpoint path, with the version prefix or suffix:
Eg: vl_getEmployeeDetails, v2_getEmployeeDetails

## 34. Can we import third-party data into Appian without a Connected System?
Yes, You can connect to a third-party API without using a Connected System if the API is not secured or uses Basic Authentication, where you manually include credentials in the request.

## 35. An external Integration in experiencing timout when sending a large volume of data? How do you resolve?
Use batching or asynchronous processing (split the payload into smaller chunks and process via background/queued integrations) to avoid timeout while handling large data volumes.

## 36. How do you create WEB API in SOAP?
Create process model and keep that as a service, need to configure in legacy web service (NR) 

## 37. What is T24 and have you used in your application?
T24 (Temenos T24) is a core banking software developed by Temenos.
 * Customer onboarding
 * Account management
 * Loans & deposits
 * Payments & transactions
 * Interest & charges
 * Regulatory and financial reporting

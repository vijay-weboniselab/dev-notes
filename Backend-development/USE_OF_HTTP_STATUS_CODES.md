### HTTP Status Codes Checklist with Methods

#### **1. 2xx - Success**
These status codes indicate that the client's request was successfully processed by the server.

| **Status Code** | **Meaning** | **Common HTTP Methods** | **When to Use** |
|-----------------|-------------|-------------------------|-----------------|
| **200 OK**      | Request succeeded and the server returned the requested data. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the operation is successfully completed. |
| **201 Created** | A new resource has been successfully created. | `POST` | Use when a new resource is created (e.g., creating a new user, adding an item). |
| **202 Accepted** | The request has been accepted for processing, but the processing is not complete. | `POST`, `PUT`, `PATCH` | Use when a request is accepted but is processed asynchronously. |
| **204 No Content** | The request was successful, but there is no content to return. | `DELETE`, `PUT`, `PATCH` | Use when a resource has been deleted or updated without returning a response body. |

---

#### **2. 3xx - Redirection**
These status codes indicate that the client must take additional action to complete the request.

| **Status Code** | **Meaning** | **Common HTTP Methods** | **When to Use** |
|-----------------|-------------|-------------------------|-----------------|
| **301 Moved Permanently** | The resource has permanently moved to a new URL. | `GET`, `POST` | Use when the URL of the resource has permanently changed. |
| **302 Found** | The resource has temporarily moved to a new URL. | `GET`, `POST` | Use when the resource has temporarily moved. |
| **304 Not Modified** | The resource has not been modified since the last request. | `GET` | Use when the client has the latest copy of the resource and no new data is available. |
| **307 Temporary Redirect** | The resource has temporarily moved, and the client should repeat the request to the new URL with the same HTTP method. | `GET`, `POST`, `PUT`, `DELETE` | Use when the server wants to redirect the client to a temporary location but keep the HTTP method intact. |
| **308 Permanent Redirect** | The resource has permanently moved, and the client should use the new URL for future requests. | `GET`, `POST`, `PUT`, `DELETE` | Use when the URL has permanently changed, and the client should update its request URL. |

---

#### **3. 4xx - Client Errors**
These status codes indicate that the client sent an invalid request.

| **Status Code** | **Meaning** | **Common HTTP Methods** | **When to Use** |
|-----------------|-------------|-------------------------|-----------------|
| **400 Bad Request** | The server could not understand the request due to invalid syntax. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the client sends invalid or malformed data (e.g., incorrect JSON). |
| **401 Unauthorized** | The request lacks proper authentication credentials. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when authentication is required, but the client has not provided credentials. |
| **403 Forbidden** | The client does not have permission to access the resource. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the client is authenticated but not authorized to perform the action. |
| **404 Not Found** | The requested resource does not exist. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the resource cannot be found (invalid endpoint or missing data). |
| **405 Method Not Allowed** | The method used in the request is not allowed for the resource. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the client tries to use an unsupported HTTP method (e.g., `POST` on a `GET` only endpoint). |
| **406 Not Acceptable** | The server cannot generate a response that is acceptable according to the request's `Accept` headers. | `GET` | Use when the client requests an unsupported response format (e.g., requesting `XML` when only `JSON` is available). |
| **408 Request Timeout** | The server timed out waiting for the request from the client. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the client took too long to send the request. |
| **409 Conflict** | The request could not be completed due to a conflict with the current state of the resource. | `POST`, `PUT`, `PATCH` | Use when there is a conflict with the resource state (e.g., attempting to update a resource with conflicting data). |
| **410 Gone** | The resource is no longer available and will never be available again. | `GET` | Use when a resource has been permanently deleted and is no longer available. |
| **422 Unprocessable Entity** | The request is well-formed but contains semantic errors, such as failed validation. | `POST`, `PUT` | Use when the request is valid, but the data cannot be processed (e.g., validation errors). |

---

#### **4. 5xx - Server Errors**
These status codes indicate that the server failed to fulfill a valid request.

| **Status Code** | **Meaning** | **Common HTTP Methods** | **When to Use** |
|-----------------|-------------|-------------------------|-----------------|
| **500 Internal Server Error** | The server encountered an unexpected condition. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the server encounters an unexpected error (e.g., uncaught exception or server misconfiguration). |
| **501 Not Implemented** | The server does not support the functionality required to fulfill the request. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the server cannot handle the request (e.g., unsupported HTTP method or feature). |
| **502 Bad Gateway** | The server, acting as a gateway or proxy, received an invalid response from the upstream server. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when there is an issue with an upstream server (e.g., third-party API is down). |
| **503 Service Unavailable** | The server is temporarily unable to handle the request due to maintenance or overload. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the server is temporarily down for maintenance or overloaded. |
| **504 Gateway Timeout** | The server did not receive a timely response from an upstream server. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when there is a timeout while waiting for an upstream server (e.g., database timeout). |
| **505 HTTP Version Not Supported** | The server does not support the HTTP version used in the request. | `GET`, `POST`, `PUT`, `PATCH`, `DELETE` | Use when the server cannot handle the HTTP version requested (e.g., outdated client version). |

---

### Summary of Common HTTP Methods

| **HTTP Method** | **Used for** | **Common Status Codes** |
|-----------------|--------------|-------------------------|
| **GET**         | Retrieve data or resource. | `200 OK`, `304 Not Modified`, `404 Not Found` |
| **POST**        | Create new resource or perform an action. | `200 OK`, `201 Created`, `400 Bad Request`, `409 Conflict` |
| **PUT**         | Update an existing resource. | `200 OK`, `204 No Content`, `400 Bad Request`, `404 Not Found` |
| **PATCH**       | Partially update an existing resource. | `200 OK`, `204 No Content`, `400 Bad Request`, `404 Not Found` |
| **DELETE**      | Delete a resource. | `200 OK`, `204 No Content`, `404 Not Found` |

---


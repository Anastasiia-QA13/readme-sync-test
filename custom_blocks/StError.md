---
name: StError
---
<br />

### ⚠️ Standard Error Responses

| HTTP | Code              | Meaning                         |
| ---: | ----------------- | ------------------------------- |
|  400 | VALIDATION_ERROR  | Body/params are invalid         |
|  401 | UNAUTHORIZED      | Missing/invalid token           |
|  403 | FORBIDDEN         | Not enough permissions          |
|  404 | NOT_FOUND         | Resource doesn’t exist          |
|  409 | CONFLICT          | State conflict / already exists |
|  429 | TOO_MANY_REQUESTS | Rate limit exceeded             |
|  500 | SERVER_ERROR      | Unexpected error on our side    |

> Tip: include the `requestId` when contacting support.

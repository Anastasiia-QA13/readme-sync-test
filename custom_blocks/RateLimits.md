---
name: RateLimits
---
<br />

### 🚦 Rate Limits

* **100 requests/minute per API key**
* Bursting allowed up to 200 in a 10-second window
* On limit: HTTP `429` + `Retry-After` header (seconds)

**Best practices**

* Exponential backoff (e.g., 1s, 2s, 4s…)
* Prefer bulk endpoints where available

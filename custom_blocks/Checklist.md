---
name: Checklist
---
<br />

### 🧪 Troubleshooting

* [ ] Token present in `Authorization` header?
* [ ] Base URL correct (prod vs sandbox)?
* [ ] Request body matches schema (types, required fields)?
* [ ] Time synced (JWT exp, clock skew)?
* [ ] Retries/backoff implemented for 429/5xx?
  If still stuck, include `requestId` from response headers when contacting support.

---
description: Basic information for NordBanking developers
---

# Getting Started

## Authentication

All requests to the NordBanking API must include a `Bearer` token in the HTTP `Authorization` header:

```bash
Authentication: Bearer np_secret_test_123456789
```

## Environments

* Sandbox
  * [https://sandbox.api.nordbanking.io/v1](https://sandbox.api.nordbanking.io/v1)
* Production
  * [https://api.nordbanking.io/v1](https://api.nordbanking.io/v1)



## HTTP Status Codes

<table><thead><tr><th width="131">Status Code</th><th width="203">Name</th><th>Explanation</th></tr></thead><tbody><tr><td>200 </td><td>OK</td><td>The request succeeded.</td></tr><tr><td>400 </td><td>Bad Request</td><td>The request body or parameters are missing or malformed.</td></tr><tr><td>401 </td><td>Unauthorized</td><td>The API key is missing or invalid.</td></tr><tr><td>422 </td><td>Unprocessable Entity</td><td>The request was well-formed, but semantic validation failed.</td></tr></tbody></table>


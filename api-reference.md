# API Reference

```yaml
openapi: 3.0.3
info:
  title: NordBanking API
  description: API for creating and processing digital payments in Nordic Countries (Norway, Sweden, Denmark and Finland).
  version: 1.0.0
servers:
  - url: https://sandbox.api.nordbanking.io/v1
    description: Sandbox Environment
paths:
  /payments:
    post:
      summary: Create a new payment
      description: Initiate a payment transaction for a customer.
      operationId: createPayment
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required:
                - amount
                - currency
                - recipient_id
              properties:
                amount:
                  type: integer
                  example: 25000
                  description: Amount in the smallest payment unit (e.g. øre/cents. 25000 = 250.00 NOK).
                currency:
                  type: string
                  example: NOK
                  enum: [NOK, SEK, DKK, EUR]
                recipient_id:
                  type: string
                  example: "rec_987654321"
      responses:
        '201':
          description: Payment successful.
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: string
                    example: "pay_123456789"
                  status:
                    type: string
                    example: "pending"
                  created_at:
                    type: string
                    example: "2026-08-24T16:00:00Z"
        '400':
          description: Invalid request (missing fields or incorrect currency).
```

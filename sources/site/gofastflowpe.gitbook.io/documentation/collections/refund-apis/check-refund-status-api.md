# Source: https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/check-refund-status-api

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/check-refund-status-api.md).

### Endpoint Details

- **Method:** `POST`

- **Payload:** `JSON`

- **Endpoint:** `https://api.fastflowpe.com/merchant/payin/refund/status`

---

## Headers

Header

Value

`x-api-key`

`<Your x-api-key here>`

`Content-Type`

`application/json`

---

## Request Payload

Copy

```
{
  "transaction_id": "<Refund Transaction ID here>"
}
```

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payin/refund/status' \
--header 'x-api-key: <your-api-key>' \
--header 'Content-Type: application/json' \
--data '{
    "transaction_id": "636724e7-80d1-4cfd-8db3-ace0bec0616a"
}'
```

Success

Failed Refund

Failure (4xx)

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Refund status retrieved successfully",
  "detail": null,
  "data": {
    "transaction_id": "<Refund Transaction UUID>",
    "original_transaction_id": "<Original Transaction UUID>",
    "status": "SUCCESS",
    "amount": "<Refunded amount>",
    "utr": "<Unique Transaction Reference>"
  },
  "meta": null
}
```

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Refund status retrieved successfully",
  "detail": null,
  "data": {
    "transaction_id": "<Refund Transaction UUID>",
    "original_transaction_id": "<Original Transaction UUID>",
    "status": "FAILED",
    "amount": "<Refunded amount>",
    "utr": null
  },
  "meta": null
}
```

Copy

```
{
  "status": "error",
  "status_code": "4xx",
  "message": "<reason for failure>",
  "detail": "<additional detail or null>",
  "data": null,
  "meta": null
}
```

#### Webhook Payload

Success

Failure

Copy

```
{
  "transaction": {
    "id": "<Transaction UUID>",
    "amount": "<Transaction amount>",
    "payment_type": "<Payment mode>",
    "utr": "<Unique Transaction Reference>",
    "status": "SUCCESS",
    "transaction_details": "<Customer info object>"
  }
}
```

Copy

```
{
  "transaction": {
    "id": "<Transaction UUID>",
    "amount": "<Transaction amount>",
    "payment_type": "<Payment mode>",
    "utr": null,
    "status": "FAILED",
    "transaction_details": "<Customer info object>"
  }
}
```

[PreviousInitiate Refund API](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/initiate-refund-api) [NextCreate Beneficiary API](https://gofastflowpe.gitbook.io/documentation/fund-transfer/create-beneficiary-api)

Last updated 8 days ago
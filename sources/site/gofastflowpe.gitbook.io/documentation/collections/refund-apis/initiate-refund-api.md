# Source: https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/initiate-refund-api

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/initiate-refund-api.md).

### Endpoint Details

- **Method:** `POST`

- **Payload:** `JSON`

- **Endpoint:** `https://api.fastflowpe.com/merchant/payin/refund/initiate`

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
  "transaction_id": "<Transaction ID here>",
  "amount": 10
}
```

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payin/refund/initiate' \
--header 'x-api-key: <your-api-key>' \
--header 'Content-Type: application/json' \
--data '{
    "transaction_id": "a6aac4a4-9516-4076-9b01-e28c3c57aa80",
    "amount": 10
}'
```

Success

Failure

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Refund Initiated Successfully",
  "detail": null,
  "data": {
    "transaction_id": "<Refund Transaction ID>",
    "original_transaction_id": "<Original Transaction UUID>",
    "status": "INITIATED",
    "original_amount": "<Original transaction amount>",
    "already_refunded": "<Amount already refunded>",
    "remaining_refundable": "<Remaining refundable amount>"
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
  "detail": null,
  "data": {
    "original_amount": "<Original transaction amount>",
    "already_refunded": "<Amount already refunded>",
    "remaining_refundable": "<Remaining refundable amount>"
  },
  "meta": null
}
```

[PreviousRefund APIs](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis) [NextCheck Refund Status API](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/check-refund-status-api)

Last updated 8 days ago
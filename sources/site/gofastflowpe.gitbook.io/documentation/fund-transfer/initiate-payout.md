# Source: https://gofastflowpe.gitbook.io/documentation/fund-transfer/initiate-payout

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/fund-transfer/initiate-payout.md).

The Payout API allows you to initiate fund transfers from your merchant account to a beneficiary's bank account. This API supports multiple payment modes such as IMPS, NEFT, and RTGS, enabling real-time or scheduled payouts depending on the selected method.

**Method** : **POST**

**Payload** : **JSON**

**Endpoint :** [**https://api.fastflowpe.com/merchant/api/v2/payout/initialize**](https://api.fastflowpe.com/merchant/api/v2/payout/initialize%27)

**Headers :** `x-api-key : <Your x-api-key here>`

**Request Body Parameters:**

Field

Type

Required

Description

`payment_type`

`string`

✅

Mode of payment, e.g., `IMPS`, `NEFT`, `RTGS`.

`amount`

`float`

✅

Amount to be transferred

`contact_id`

`string`

❌

Reference ID for stored contact bank details.

merchant\_ref\_id

string

Reference ID.

va\_id

string

✅

VA\_ID (it will be shared by the team / you can get it via dashboard)

**Payload:**

Copy

```
{
  "payment_type": "IMPS",
  "amount": 1000,
  "contact_id": <your-contact-id>,  
  "merchant_ref_id": <your-ref-id>,
  "va_id":"SVA-123456"
}
```

**Sample cURL:**

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/api/v2/payout/initialize' \
--header 'x-api-key: <your x-api-key>' \
--data '{
    "payment_type": "IMPS",
    "amount": 501,
    "contact_id": "0d39ff01-eebe-4d7c-9e89-f4ae657605f4",
    "merchant_ref_id": <your-ref-id>,
}'
```

**Response :** **JSON**

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Payout Initiation Success",
  "detail": null,
  "data": {
    "message": "Payout Initiation Success",
    "transaction_id": "your-transaction-id-here",
    "reason": "Message String Here"
  }
}
                                                                  
```

[PreviousCreate Beneficiary API](https://gofastflowpe.gitbook.io/documentation/fund-transfer/create-beneficiary-api) [NextCheck Status API](https://gofastflowpe.gitbook.io/documentation/fund-transfer/check-status-api)

Last updated 8 days ago
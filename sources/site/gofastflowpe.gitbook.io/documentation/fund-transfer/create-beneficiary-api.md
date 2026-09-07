# Source: https://gofastflowpe.gitbook.io/documentation/fund-transfer/create-beneficiary-api

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/fund-transfer/create-beneficiary-api.md).

This API allows you to create contacts for your beneficiaries which can then be used to consume PayOut.

**Method** : **POST**

**Payload** : **JSON**

**Endpoint :** [**https://api.fastflowpe.com/merchant/api/v1/verification/create-beneficiary**](https://api.fastflowpe.com/merchant/api/v1/verification/create-beneficiary)

**Headers :** `x-api-key : <Your x-api-key here>`

**Request Body Parameters:**

Field

Type

Required

Description

`name`

`string`

✅

Name of benficiary

`email`

`float`

✅

Email

`bank_details`

`JSON`

✅

Details of beneficiary

`phone`

string

✅

Phone number

`pan_number`

string

❌

PAN Number

`verification_type`

string

✅

PENNY\_DROP

**Payload:**

Copy

```
{
    "name": "name",
    "email": "name@gmail.com",
    "bank_details": {
        "bank_account_number":"xxxxxxxxxxxxxx",
        "ifsc":"IDFBxxxxxxx",
        "account_type":"SAVINGS" // or CURRENT
    },
    "phone":"xxxxxxxxxx",
    "pan_number": "", 
    "verification_type":"PENNY_DROP" // or PENNY_LESS
}
```

**Sample cURL:**

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/api/v1/verification/create-beneficiary' \
--header 'x-api-key: <your x-api-key>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "name",
        "email": "name@gmail.com",
        "bank_details": {
            "bank_account_number":"xxxxxxxxxxxxxx",
            "ifsc":"IDFBxxxxxxx",
            "account_type":"SAVINGS" // or CURRENT
        },
        "phone":"xxxxxxxxxx",
        "pan_number": "", 
        "verification_type":"PENNY_DROP" // or PENNY_LESS
}'
```

**Response :** **JSON**

Copy

```
{
    "status": "success",
    "status_code": 200,
    "message": "Beneficiary processed successfully",
    "detail": null,
    "data": {
        "is_new_beneficiary": false, // boolean
        "contact_id": "61f4d33d-274a-40e7-b239-c1c28de80e19",
        "verification": {
            "status": "FAILED",
            "verification_type": "PENNY_DROP",
            "verified_at": "2026-02-11T15:22:16.986350+05:30",
            "failure_reason": null,
            "account_number": "xxxxxxxxxx",
            "ifsc": "xxxxxxxxxxxx",
            "expiry_date": "2026-08-10T15:22:27.614446+05:30"
        }
    },
```

[PreviousCheck Refund Status API](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/check-refund-status-api) [NextInitiate Payout](https://gofastflowpe.gitbook.io/documentation/fund-transfer/initiate-payout)

Last updated 8 days ago
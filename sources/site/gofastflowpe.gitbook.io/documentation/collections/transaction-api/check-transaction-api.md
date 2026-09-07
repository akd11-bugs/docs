# Source: https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/check-transaction-api

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/check-transaction-api.md).

**Method** : **POST**

**Payload** : **JSON**

**Endpoint : https://api.fastflowpe.com/merchant/payin/status**

**Headers :** `x-api-key : <Your x-api-key here>`

**Sample cURL :**

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payin/status' \
--header 'Accept: */*' \
--header 'User-Agent: Thunder Client (https://www.thunderclient.com)' \
--header 'x-api-key: eyJhbGciOiaWF0IjoxNzY1OTcyODkyLCJleHAiOjE3NjU5NzQ2OTJ9.GIkze0VpYBqL2Fc6jMyuQN1eJWFVE8Eg4g7pTfzhcOOf3osB9STNgo8H9S3Jxkj0i_ABBEV-lTdqrsWvClugbS3_wXfo3S0_5BZt5Q3-zoHHm9zNxw_c85wh44AWCkPJBOI_HTXWg9284ca-O_vg0GWLS_NgQWC3WkvEnoD5prGGrRBRZLQJ7X3YDUm7jqm-zQKhVTOEw4k38QrkaFCtw5oEe6Wk-FhrOAvGgG9YLDxVghP6KSuoHxnbr_hpStp3XNUw_bZ1EqWJXCjhWx2sbhNlEV4-VKJqZsQwuO2wtNAWTiruC16CsTjSZ2xgIq7h1mev6B2NfrFXsU0phCz_JA' \
--header 'Content-Type: application/json' \
--data '{
  "transaction_id":"e7a1c22d-52cb-419b-af0c-122c16c5b613"

}'
```

**Payload :**

Copy

```
{

  "transaction_id":"<Transaction ID here>"

}
```

Success

Failed Transaction

Failure (4xx)

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Transaction status retrieved successfully",
  "detail": "Status check completed successfully",
  "data": {
    "transaction_id": "<Transaction UUID>",
    "status": "SUCCESS",
    "utr": "<Unique Transaction Reference>",
    "payment_details": "<Payment details object>",
    "amount": "<Transaction amount in float>",
    "payment_type": "<Payment type>",
    "merchant_ref_id": "<Merchant reference ID>"
  },
  "meta": null
}
```

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Transaction status retrieved successfully",
  "detail": "Status check completed successfully",
  "data": {
    "transaction_id": "<Transaction UUID>",
    "status": "FAILED",
    "utr": null,
    "payment_details": "<Payment details object>",
    "amount": "<Transaction amount in float>",
    "payment_type": "<Payment type>",
    "merchant_ref_id": "<Merchant reference ID>"
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

[PreviousInitiate Payin API](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/initiate-payin-api) [NextRefund APIs](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis)

Last updated 8 days ago
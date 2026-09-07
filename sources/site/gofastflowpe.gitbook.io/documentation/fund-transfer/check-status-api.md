# Source: https://gofastflowpe.gitbook.io/documentation/fund-transfer/check-status-api

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/fund-transfer/check-status-api.md).

### 1\. Check Transaction Status API for PayOut

**Note:** This API is protected by an active rate limiter.

The **Check Transaction Status API** is used to **query the status of a previously initiated payout**. By providing the **transaction\_id**, you can **retrieve the current status of the payout**.

**Method :** **POST**

**Payload** : **JSON**

**Endpoint : https://api.fastflowpe.com/merchant/payout/status**

**Headers :**

`x-api-key : <Your x-api-key here>`

**Sample cURL :**

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payout/status' \
--header 'Content-Type: application/json' \
--header 'x-api-key: <your x-api-token here>' \
--data '{
  "merchant_ref_id": "your ref id"
  // or use "transaction_id": "your transaction id here"
}'
```

**Payload :**

Copy

```
{
  "merchant_ref_id":"your ref id"
  "transaction_id": "transaction_id",
}
```

**Response :** **JSON**

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Transaction status retrieved successfully",
  "detail": "Status check completed successfully",
  "data": {
    "status": "SUCCESS"
  }
}
```

### 2\. Balance API for PayOut

The Balance **API** is used to **query the status of current balance.**

**Method :** **GET**

**Payload** : **JSON**

**Endpoint :** [**https://api.fastflowpe.com/merchant/payout/api/merchant/balance**](https://api.fastflowpe.com/merchant/payout/api/merchant/balance)

**Query Params :** va\_id

**Headers :**

`x-api-key : <Your x-api-key here>`

**Sample cURL :**

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payout/api/merchant/balance?va_id={{va_id}}' \
--header 'x-api-key: <>'
```

**Response :** **JSON**

Copy

```
{
    "status": "success",
    "status_code": 200,
    "message": "Balance fetched successfully",
    "detail": null,
    "data": {
        "merchant_id": "<Your merchant id>",
        "balance": 500.0
    },
    "meta": null
}
```

---

## Webhook Payload

We send a post request to the configured callback url with the below payload.

Copy

```
"transaction": {
          "id": "5314e23a-4931-400f-b499-c4347ad0c7f3",
          "amount": "500.00",
          "payment_type": "IMPS",
          "utr": "92834823745",
          "status": "SUCCESS", // or 'FAILED'
          "beneficiary_details": {
            "beneficiary_ifsc": "ICIC0009999",
            "beneficiary_name": "Jhon Doe",
            "beneficiary_email": jhondoe@gmail.com,
            "beneficiary_mobile": "8105800389",
            "beneficiary_acc_number": "109909023553"
          },
          "merchant_ref_id": "TRX_2020202"
        }
```

[PreviousInitiate Payout](https://gofastflowpe.gitbook.io/documentation/fund-transfer/initiate-payout) [NextCallback Configuration](https://gofastflowpe.gitbook.io/documentation/callback-configuration-1)

Last updated 8 days ago
# Source: https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/initiate-payin-api

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/initiate-payin-api.md).

**Method** : **POST**

**Payload** : **JSON**

**Minimum Amount : 200 Rs.**

**Endpoint : https://api.fastflowpe.com/merchant/payin/initialize**

**Headers :** `x-api-key : <Your x-api-key here>`

**Request Body Parameters:**

## Authentication & Headers

All API requests must include the following headers for authentication, device tracking, and request validation.

Header

Type

Required

Description

`x-api-key`

string

Yes

Merchant API key provided by FastFlowPE

`Content-Type`

string

Yes

Must be `application/json`

`user-agent`

string

Yes

Browser/device user agent information

`x-browser-fingerprint`

string

Yes

Base64 encoded browser/device fingerprint

`x-source-channel`

string

Yes

Source platform (`web`, `mobile`, `app`)

`x-source-channel-version`

string

Yes

Client application version (e.g. `10`)

---

## Example Headers

Copy

```
{
  "x-api-key": "your_api_key",
  "Content-Type": "application/json",
  "user-agent": "Mozilla/5.0",
  "x-browser-fingerprint": "ZGI4YzQ2Y2EtYzI1Mi00Y2M5LTk0NjEtY2Q1N2Y0Y2E4YmQx"
  "x-source-channel": "web",
  "x-source-channel-version": "10"
}
```

## Body Parameters

Field

Type

Required

Description / Allowed Values

`payment_type`

string

Yes

`QR`, `INTENT`, `CREDIT_CARD`, `DEBIT_CARD`, `NETBANKING`, `EMI`, `PAYLATER`

`amount`

float

Yes

Minimum amount: 200

`customer_info`

object

Yes

Customer information object

`customer_info.name`

string

Yes

Customer full name

`customer_info.email`

string

Yes

Customer email address

`customer_info.phone_number`

string

Yes

10-digit mobile number

`upi_id`

string

Optional

Customer UPI ID

`order_id`

string

Yes

Unique merchant order ID

`device_os`

string

Required for `INTENT` & `QR`

`IOS`, `ANDROID`

`target_app`

string

Required for `INTENT` and `QR`. Omit this field when requesting a generic Intent URL (Android only).

`PHONEPE`, `GPAY`, `PAYTM`, `CRED`, `BHIM`, `AMAZON`

`productinfo`

string

Yes

Product or transaction description. Minimum length: 8 characters.

---

## Example Request Body

Copy

```
{
  "amount": 200.0,
  "payment_type": "DEBIT_CARD",
  "order_id": "eoo36",
  "device_os": "IOS",
  "target_app": "CRED",
  "productinfo": "hello",
  "customer_info": {
    "name": "jonsnow",
    "email": "jonsnow@gmail.com",
    "phone_number": "9999999999"
  }
}
```

**Sample cURL :**

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payin/initialize' \
--header 'x-api-key: <your-api-key>' \
--header 'Content-Type: application/json' \
--header 'user-agent: Mozilla/5.0 (iPhone; CPU iPhone OS 18_5 like Mac OS X) AppleWebKit/605.1.15' \
--header 'x-browser-fingerprint: TW96aWxsYS81LjAgKE1hY2lud' \
--header 'x-source-channel: web' \
--header 'x-source-channel-version: 10' \
--data-raw '{
    "order_id": "ORD123456789",
    "amount": 500,
    "payment_type": "INTENT",
    "device_os": "IOS",
    "target_app": "PHONEPE",
    "productinfo": "Premium Subscription",
    "customer_info": {
        "name": "<NAME>",
        "email": "<EMAIL>",
        "phone_number": "<PHONE_NO>"
    }
}'
```

Success

Failure

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Payin Initiated Successfully",
  "detail": null,
  "data": {
    "transaction_id": "1be74773-88ca-48db-afa6-243d26e29375",
    "checkout_url": "https://checkout.fastflowpe.com/pay/tx_8fj39dk29slx7ab"
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

[PreviousTransaction API](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api) [NextCheck Transaction API](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/check-transaction-api)

Last updated 8 days ago
# Source: https://gofastflowpe.gitbook.io/documentation/collections/payment-links/create-payment-link

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/create-payment-link.md).

**Create Payment Link** Endpoint:

Copy

```
POST https://api.fastflowpe.com/merchant/payment-links/create
```

Headers:

Copy

```
Content-Type: application/json
x-api-key: <merchant_x_api_key>
```

Body Parameters:

Field

Type

Required

Description / Allowed Values

`order_id`

string

Yes

Unique merchant order ID

`amount`

float

Yes

Minimum amount: 200

`description`

string

Yes

Product or transaction description.

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

`psp_provider_id`

UUID

Optional

PSP Provider ID

Request:

Copy

```
{
  "order_id": "payment_12345",
  "amount": 100,
  "description": "Test Collection",
  "psp_provider_id":"xxxxxxxxxxxxxx",    //Optional
  "customer_info": {
    "name": "xxxxxx",
    "email": "xxxxxxxxx",
    "phone": "xxxxxxxxxxxxxxxx"
  }
}
```

Sample cURL:

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payment-links/create' \
--header 'x-api-key: <x-api-key> \
--header 'Content-Type: application/json' \
--data-raw '{
    "order_id": "ORD_4421",
    "amount" : 100,
    "description":"sample product",
    "customer_info" :{
        "name": "Customer",
        "email": "customer@gofastflowpe.com",
        "phone": "8989898989"
    },
    "expiry": "2026-08-29T12:12:09.823481+05:30"
}'
```

Response:

Success

Failure

[PreviousPayment Links](https://gofastflowpe.gitbook.io/documentation/collections/payment-links) [NextCheck Payment Link Status](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/check-payment-link-status)

Last updated 8 days ago
# Source: https://gofastflowpe.gitbook.io/documentation/collections/payment-links/check-payment-link-status

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/check-payment-link-status.md).

EndPoint:

Copy

```
GET https://api.fastflowpe.com/merchant/payment-links/v3/check-payment-status?slug=<slug>
```

Headers:

Copy

```
x-api-key: <merchant_x_api_key_jwt>
```

Sample cURL:

Copy

```
curl --location 'https://api.fastflowpe.com/merchant/payment-links/v3/check-payment-status?slug=NQ7diKbFmRDT' \
--header 'x-api-key: <merchant_x_api_key_jwt>'
```

Response:

Completed

Pending

Failed

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Payment is completed",
  "data": {
    "payment_status": "COMPLETED",
    "amount": 100.0,
    "id": "a5563aae-d5d0-4ca9-8ff0-d7629d5d5b81",
    "payment_mode": "QR",
    "utr": "619704648408",
    "status": "SUCCESS"
  }
}
```

Copy

```
{
  "status": "success",
  "status_code": 200,
  "message": "Payment is pending",
  "data": {
    "payment_status": "PENDING"
  }
}
```

Copy

```
{
    "status": "success",
    "status_code": 200,
    "message": "Payment has failed",
    "detail": null,
    "data": {
        "payment_status": "FAILED"
    },
    "meta": null
}
```

[PreviousCreate Payment Link](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/create-payment-link) [NextGet PayIn PSP Providers](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/get-payin-psp-providers)

Last updated 8 days ago
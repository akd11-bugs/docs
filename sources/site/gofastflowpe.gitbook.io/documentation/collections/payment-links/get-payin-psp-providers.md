# Source: https://gofastflowpe.gitbook.io/documentation/collections/payment-links/get-payin-psp-providers

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/get-payin-psp-providers.md).

Fetches the list of active PayIn PSP providers mapped to the authenticated merchant.

#### Endpoint

Copy

```
GET https://api.fastflowpe.com/merchant/payment-links/v3/get-payin-providers
```

#### Headers

Copy

```
Accept: application/json
x-api-key: <MERCHANT_TOKEN>
```

#### cURL

Copy

```
curl --location 'https://devapi.fastflowpe.com/merchant/payment-links/v3/get-payin-providers' \
  --header 'Accept: application/json' \
  --header 'x-api-key: <MERCHANT_TOKEN>'
```

#### Success Response

Copy

```
{
  "providers": [
    {
      "psp_provider_id": "71f2904d-8f4d-4662-b98a-3198926182ec",
      "provider_name": "testuatpayin"
    }
  ]
}
```

#### Response Fields

Field

Type

Description

`providers`

array

List of active PayIn PSP providers mapped to the merchant.

`providers[].psp_provider_id`

string

Unique PSP provider ID. Use this value as `provider_id` while creating a payment link.

`providers[].provider_name`

[PreviousCheck Payment Link Status](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/check-payment-link-status) [NextTransaction API](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api)

Last updated 9 days ago
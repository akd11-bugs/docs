# Source: https://gofastflowpe.gitbook.io/documentation/collections/payment-links/create-payment-link.md

\> For the complete documentation index, see \[llms.txt\](https://gofastflowpe.gitbook.io/documentation/llms.txt). Markdown versions of documentation pages are available by appending \`.md\` to page URLs; this page is available as \[Markdown\](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/create-payment-link.md). # Create Payment Link \*\*Create Payment Link\*\*\\ Endpoint: \`\`\` POST https://api.fastflowpe.com/merchant/payment-links/create \`\`\` Headers: \`\`\` Content-Type: application/json x-api-key: \`\`\` Body Parameters:

| Field | Type | Required | Description / Allowed Values |
| --- | --- | --- | --- |
| `order_id` | string | Yes | Unique merchant order ID |
| `amount` | float | Yes | Minimum amount: 200 |
| `description` | string | Yes | Product or transaction description. |
| `customer_info` | object | Yes | Customer information object |
| `customer_info.name` | string | Yes | Customer full name |
| `customer_info.email` | string | Yes | Customer email address |
| `customer_info.phone_number` | string | Yes | 10-digit mobile number |
| `psp_provider_id` | UUID | Optional | PSP Provider ID |

Request: \`\`\`json { "order\_id": "payment\_12345", "amount": 100, "description": "Test Collection", "psp\_provider\_id":"xxxxxxxxxxxxxx", //Optional "customer\_info": { "name": "xxxxxx", "email": "xxxxxxxxx", "phone": "xxxxxxxxxxxxxxxx" } } \`\`\` Sample cURL: \`\`\`json curl --location 'https://api.fastflowpe.com/merchant/payment-links/create' \\ --header 'x-api-key: \\ --header 'Content-Type: application/json' \\ --data-raw '{ "order\_id": "ORD\_4421", "amount" : 100, "description":"sample product", "customer\_info" :{ "name": "Customer", "email": "customer@gofastflowpe.com", "phone": "8989898989" }, "expiry": "2026-08-29T12:12:09.823481+05:30" }' \`\`\` Response: {% tabs %} {% tab title="Success" %} \`\`\`json { "status": "success", "status\_code": 201, "message": "Payment link created successfully", "detail": "New payment link generated", "data": { "id": "0d106d5a-aa6e-4994-a4ef-8058891d270f", "merchant\_id": "5f600966-391e-4e2a-9dab-9a139251732f", "slug": "QdGaMy0f80zu", "description": "sample product", "one\_time": true, "expiry": "2026-08-29T12:12:09.823481+05:30", "amount": 300.0, "customer\_info": { "name": "Customer", "email": "customer@gofastflowpe.com", "phone": "8989898989", "currency": "INR" }, "status": "ACTIVE", "payment\_status": "PENDING", "order\_id": "ORD\_4421", "payment\_mode": null, "psp\_provider\_id": null, "payment\_url": "https://go.fastflowpe.com/pay/QdGaMy0f80zu", "created\_at": "2026-07-29T12:12:09.823481+05:30", "updated\_at": "2026-07-29T12:12:09.823481+05:30" }, "meta": null } \`\`\` {% endtab %} {% tab title="Failure" %} \`\`\`json { "status": "error", "status\_code": "4xx", "message": "", "detail": "", "data": null, "meta": null } \`\`\` {% endtab %} {% endtabs %}
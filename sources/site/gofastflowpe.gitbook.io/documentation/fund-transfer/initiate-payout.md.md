# Source: https://gofastflowpe.gitbook.io/documentation/fund-transfer/initiate-payout.md

\> For the complete documentation index, see \[llms.txt\](https://gofastflowpe.gitbook.io/documentation/llms.txt). Markdown versions of documentation pages are available by appending \`.md\` to page URLs; this page is available as \[Markdown\](https://gofastflowpe.gitbook.io/documentation/fund-transfer/initiate-payout.md). # Initiate Payout The Payout API allows you to initiate fund transfers from your merchant account to a\\ beneficiary's bank account. This API supports multiple payment modes such as IMPS, NEFT, and\\ RTGS, enabling real-time or scheduled payouts depending on the selected method. \*\*Method\*\* : \*\*POST\*\* \*\*Payload\*\* : \*\*JSON\*\* \*\*Endpoint :\*\* \[\*\*https://api.fastflowpe.com/merchant/api/v2/payout/initialize\*\*\](https://api.fastflowpe.com/merchant/api/v2/payout/initialize%27) \*\*Headers :\*\* \`x-api-key : \` \*\*Request Body Parameters:\*\*

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `payment_type` | `string` | ✅ | Mode of payment, e.g., `IMPS`, `NEFT`, `RTGS`. |
| `amount` | `float` | ✅ | Amount to be transferred |
| `contact_id` | `string` | ❌ | Reference ID for stored contact bank details. |
| merchant\_ref\_id | string | | Reference ID. |
| va\_id | string | ✅ | VA\_ID (it will be shared by the team / you can get it via dashboard) |

\*\*Payload:\*\* {% code overflow="wrap" %} \`\`\`json { "payment\_type": "IMPS", "amount": 1000, "contact\_id": , "merchant\_ref\_id": , "va\_id":"SVA-123456" } \`\`\` {% endcode %} \*\*Sample cURL:\*\* {% code overflow="wrap" %} \`\`\`json curl --location 'https://api.fastflowpe.com/merchant/api/v2/payout/initialize' \\ --header 'x-api-key: ' \\ --data '{ "payment\_type": "IMPS", "amount": 501, "contact\_id": "0d39ff01-eebe-4d7c-9e89-f4ae657605f4", "merchant\_ref\_id": , }' \`\`\` {% endcode %} \*\*Response : \*\*\*\*JSON\*\* \`\`\`json { "status": "success", "status\_code": 200, "message": "Payout Initiation Success", "detail": null, "data": { "message": "Payout Initiation Success", "transaction\_id": "your-transaction-id-here", "reason": "Message String Here" } } \`\`\`
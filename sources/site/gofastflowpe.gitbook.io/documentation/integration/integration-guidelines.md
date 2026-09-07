# Source: https://gofastflowpe.gitbook.io/documentation/integration/integration-guidelines

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/integration/integration-guidelines.md).

As a FastFlowPe merchant, you can initiate payouts and track their status via the dashboard or APIs, with optional callbacks for transaction status updates. To securely interact with FastFlowPe’s REST APIs, you must integrate our authentication mechanism, ensuring all requests are properly authorized.

FastFlowPe integrations use X-API-Keys—short-lived tokens that ensure secure and authenticated communication between your system and FastFlowPe.

Merchants must register a primary and secondary IP address, both whitelisted by us. Only requests from these IPs with a valid X-API-Key are accepted. Each system can have only one active X-API-Key at a time—generating a new key invalidates the old one to prevent misuse. X-API-Keys are generated using the Client ID and Client Secret available in the merchant dashboard’s API section.

[NextClient Credentials](https://gofastflowpe.gitbook.io/documentation/integration/client-credentials)

Last updated 7 days ago
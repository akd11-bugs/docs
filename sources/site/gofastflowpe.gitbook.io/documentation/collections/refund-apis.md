# Source: https://gofastflowpe.gitbook.io/documentation/collections/refund-apis

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis.md).

FastFlowPe offers following refund APIs:

- **Initiate Refund** – Creates a refund request for a previously successful PayIn transaction. Upon successful validation, the API returns a unique refund `transaction_id` that can be used to track the refund.

- **Check Refund Status** – Retrieves the latest status of a previously initiated refund using its refund `transaction_id`. This API allows merchants to verify whether the refund has been successfully processed or has failed.

[PreviousCheck Transaction API](https://gofastflowpe.gitbook.io/documentation/collections/transaction-api/check-transaction-api) [NextInitiate Refund API](https://gofastflowpe.gitbook.io/documentation/collections/refund-apis/initiate-refund-api)

Last updated 8 days ago
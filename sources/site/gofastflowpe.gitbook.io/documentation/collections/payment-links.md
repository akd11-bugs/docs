# Source: https://gofastflowpe.gitbook.io/documentation/collections/payment-links

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/collections/payment-links.md).

The Payment Link API allows a merchant to create a payable link for a customer and track its payment status. The merchant creates a link by passing the order amount, customer details, and a unique `order_id`. The API returns a hosted payment URL that can be shared with the customer.

After the customer completes or attempts payment, the merchant can use the status-check API with the payment link `slug` to verify whether the payment is still pending or completed successfully.

Authentication is done using the merchant `x-api-key`. The API key identifies the merchant and must be sent in every request header.

[PreviousIP Whitelisting Guide](https://gofastflowpe.gitbook.io/documentation/integration/ip-whitelisting-guide) [NextCreate Payment Link](https://gofastflowpe.gitbook.io/documentation/collections/payment-links/create-payment-link)

Last updated 8 days ago
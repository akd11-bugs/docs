# Source: https://gofastflowpe.gitbook.io/documentation/callback-configuration-1

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/callback-configuration-1.md).

### Callback Configuration for PayIn.

We will hit an endpoint **provided by you** with the following payload.

**Method** : **POST**

**Payload** : **JSON**

Copy

```
"transaction": {
    "id": str(transaction.id),
    "order_id":str(transaction.order_id),
    "amount": str(transaction.amount),
    "payment_type": transaction.payment_mode,
    "utr": transaction.utr,
    "status": psp_status,
    "transaction_details": transaction.customer_info,
    "resp_message": parsed_response
}
                            
```

### How to tell us where to attempt the callback at ?

You need to pre-configure your webhook URL with us before we can start sending callbacks to your server whenever a transaction status is updated. In the dashboard, you need to get to settings followed by clicking on tab "Webhooks" and in the form below you can configure your desired callback url.

![](https://gofastflowpe.gitbook.io/documentation/~gitbook/image?url=https%3A%2F%2F1141656871-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsoqiQl6wQDTEheDT0DWu%252Fuploads%252FVi2AcjSY3n1370f9pgQ3%252FImage%252005-08-25%2520at%252019.55.jpeg%3Falt%3Dmedia%26token%3D181dc145-9cae-40bc-963b-1a20799dca87&width=768&dpr=3&quality=100&sign=b8552d07&sv=2)

#### To configure callback url : **Login → Settings → Webhooks → Debit - PayOut → Update**

**Note****:** Only HTTPS-enabled webhook URL will be accepted and processed. After setting it up, please allow 2–3 minutes for the next callback to reach the provided endpoint post transaction.

### Callback Configuration for PayOut.

**Method** : **POST**

**Payload** : **JSON**

Copy

```
"transaction": {
            "id": str(transaction.id),
            "amount": str(transaction.amount),
            "payment_type": transaction.payment_mode,
            "utr": response_data.get('utr') or transaction.utr,
            "status": psp_status,
            "beneficiary_details": transaction.customer_info,
            "merchant_ref_id": transaction.merchant_ref_id
        }
```

[PreviousCheck Status API](https://gofastflowpe.gitbook.io/documentation/fund-transfer/check-status-api) [NextHelp Centre](https://gofastflowpe.gitbook.io/documentation/help-centre)

Last updated 7 days ago
# Source: https://gofastflowpe.gitbook.io/documentation/integration/api-authentication-setup

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/integration/api-authentication-setup.md).

Note : The Client ID and Client Secret are permanent credentials and never change. In contrast, X-API-Tokens are short-lived and expire after 30 minutes; once expired, a new token must be generated via the dashboard or the provided API.

There are two ways to acquire an `x-api-key`.

1. **Via Dashboard:** This method has already been explained [here](https://gofastflowpe.gitbook.io/documentation/integration/api-authentication-setup#generate-an-x-api-key-from-dashboard).

2. **Via API:** You can use your `client-id` and `client-secret` by sending them as headers in the request which in response will return your fresh new x-api-key.

You can refer to the sample request below:

### 1\. Via API - Acquiring an x-api-key using client-id & client-secret

**Request Type** : **GET**

**Headers** :

`client-id : <Your Client ID>`

`client-secret : <Your Client Secret>`

**Sample cURL**

Copy

```
curl --location 'https://auth.fastflowpe.com/system/generate_x_api_token_merchant' \
--header 'Accept: application/json' \
--header 'client-id: Your-Client-ID-Here' \
--header 'client-secret: Your-Client-Secret-Here'
```

**Response** : **JSON**

Copy

```
{
    "status": "success",
    "status_code": 200,
    "message": "Merchant X-API-Key generated and saved.",
    "detail": null,
    "data": {
        "x_api_key": "<Your New x-api-key will come here>"
    }
}
```

**Note** : To avoid 401 Unauthorized errors caused by token expiry (after 30 minutes), you can automate x-api-key generation. Set up a cron job to call our API every 29–30 minutes and fetch a new key for uninterrupted access. When a new x-api-key is generated, the previous one is automatically invalidated and can no longer be used.

### 2\. Via Dashboard - Acquiring an x-api-key from the dashboard

To **generate a new X-API-Key**, click the **Generate Key** button in the **API section** of your merchant dashboard.

You can access the dashboard at : [https://go.fastflowpe.com/](https://go.fastflowpe.com/)

After you login with your register email and password, you can access this feature under

[**Settings → API**](https://gofastflowpe.gitbook.io/documentation/integration/api-authentication-setup#about-client-id-client-secret-x-api-key) on your dashboard.

![](https://gofastflowpe.gitbook.io/documentation/~gitbook/image?url=https%3A%2F%2F1141656871-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsoqiQl6wQDTEheDT0DWu%252Fuploads%252FiwDmRPiHzItQaBdINBGT%252FImage%252005-08-25%2520at%252009.17.jpeg%3Falt%3Dmedia%26token%3D82d006dc-e936-49d0-b58c-ba69a0551ec1&width=768&dpr=3&quality=100&sign=9abcc988&sv=2)

In this section, you can:

- View your **Client ID** and **Client Secret**

- View your **currently active X-API-Key**

- **Generate a new X-API-Key**

**Note** : When you click **Generate Key**, the **existing X-API-Key is automatically invalidated**, and a **new key is generated and activated immediately**. You can copy it from the dashboard and use immediately.

#### To generate an x-api-key from dashboard : **Login → Settings → API → X-API Key →** **Generate Key Button ( in red )**

[PreviousClient Credentials](https://gofastflowpe.gitbook.io/documentation/integration/client-credentials) [NextIP Whitelisting Guide](https://gofastflowpe.gitbook.io/documentation/integration/ip-whitelisting-guide)

Last updated 8 days ago
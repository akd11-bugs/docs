# Source: https://gofastflowpe.gitbook.io/documentation/integration/client-credentials

For the complete documentation index, see [llms.txt](https://gofastflowpe.gitbook.io/documentation/llms.txt). This page is also available as [Markdown](https://gofastflowpe.gitbook.io/documentation/integration/client-credentials.md).

Each merchant is issued a Client ID and Client Secret at signup, which uniquely identify them with FastFlowPe. These credentials must be kept secure, as anyone with access can generate an X-API-Key and use it to access the Payout API.

The visibility of these **permanent credentials** is available on the **merchant dashboard** at [https://go.fastflowpe.com/sign-in](https://go.fastflowpe.com/)

#### To view your credentials: **Login → Settings → API → API Key**

![](https://gofastflowpe.gitbook.io/documentation/~gitbook/image?url=https%3A%2F%2F1141656871-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsoqiQl6wQDTEheDT0DWu%252Fuploads%252FiwDmRPiHzItQaBdINBGT%252FImage%252005-08-25%2520at%252009.17.jpeg%3Falt%3Dmedia%26token%3D82d006dc-e936-49d0-b58c-ba69a0551ec1&width=768&dpr=3&quality=100&sign=9abcc988&sv=2)

**Note** : While **IP whitelisting** ensures that any request originating from an **unrecognised IP address** is rejected, it is still **critical** that merchants **protect their Client ID and Client Secret** to prevent misuse or unauthorised access.

**Also, please note that**

- **if your Client ID or Client Secret is exposed, contact FastFlowPe Support immediately.**

- **if your X-API-Key is leaked or misused, regenerate it via the Merchant Dashboard or API.** The old key will be **automatically revoked** upon generating a new one.

- **the x-api-key is valid for 30 minutes. Once expired, it will automatically be invalidated.**

[PreviousIntegration Guidelines](https://gofastflowpe.gitbook.io/documentation/integration/integration-guidelines) [NextAPI Authentication Setup](https://gofastflowpe.gitbook.io/documentation/integration/api-authentication-setup)

Last updated 8 days ago
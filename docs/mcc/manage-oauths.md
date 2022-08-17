## Overview

You can create and store OAuth entries within the Matillion Platform to authenticate data sources.

Any existing OAuth entries are listed on this page, oldest first. Click the trashcan button alongside an OAuth entry to delete it, and then click **Yes, delete** to confirm deletion or click **Never mind** to cancel the deletion process.

---

## Add an OAuth entry

:::info
The **Add new OAuth** modal requires your app's credentials. You'll need to know these credentials, or have access to the app. Please contact your administrator for your data source service if you don't have the required permissions.
:::

To add a new OAuth entry, click **Add OAuth**.

In the **Add new OAuth** modal, complete the following fields:

|Property|Description|
|---|---|
|Name|A unique, descriptive name for the OAuth entry.|
|Grant Type|Select a grant type. Choose either Authorization Code or Client Credentials. [Which should I use?](#which-grant-type-should-i-use)|
|Credentials Mechanism|Select whether the credentials will be formatted in the request body or as request headers when initially requesting an access token. This parameter is only available when **Grant Type** is **Authorization Code**.|
|Client ID|A unique client ID string for your application. This credential will be available when you create an app for your data source service in the corresponding developer portal.|
|Client Secret|A unique client secret string for your application. This credential will be available when you create an app for your data source service in the corresponding developer portal. Typically, the client secret is located underneath or after the client ID. Please note, some services will only reveal a client secret once upon creation of an app, and therefore it's vital that you copy and save the client secret in a secure location for later access.|
|Authorize URL|An authorization URL of your app. This parameter is only available when **Grant Type** is **Authorization Code**.|
|Access Token URL|A URL to an API access token for your app.|

Click **Authorize**. This action will create the OAuth entry on the Matillion Platform, attempting to authorize and obtain an access token. For the Authorization Code grant type, you will be redirected to the third-party service, who will then redirect you back to the Matillion Platform upon confirmation.

Any errors that occur during the authorization attempt will be displayed at this step, with error details.

---

## Which Grant Type should I use?

The Grant Type options available when adding an OAuth entry represent the two main types of flow for OAuth:

- [Authorization Code](https://oauth.net/2/grant-types/authorization-code/): the details you enter are used to redirect you to the third-party service where you'll grant Matillion Custom Connector access to your data, after which, Matillion Custom Connector can obtain a token and have a way to refresh it periodically when it expires.
- [Client Credentials](https://oauth.net/2/grant-types/client-credentials/): the details you enter are all that's needed to authenticate on an ongoing basis.

It is recommended that the client credentials flow where possible, because it's the most appropriate for this kind of integration and there are fewer potential issues. However, many APIs only offer the Authorization Code flow, so Matillion Custom Connector supports that too.

If you're not sure which option to choose, check the details and documentation provided by your third-party service. If they show a URL that includes `authorize`, discusses scopes, or asks you for a callback URL, then it's the Authorization Code flow.

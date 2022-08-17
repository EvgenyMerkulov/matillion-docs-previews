## Overview

In the **Connectors** pane of Matillion Custom Connectors, you can create custom data source connectors to build data pipelines in Matillion Data Loader.

---

## Prerequisites

- You need to know how to authenticate with your third-party service.
- It's recommended to have your third-party's API documentation to hand, as well as their API's main URL.

---

## Add connector

If you don't have any connectors yet, click **Add connector** in the middle of the pane.

Your new connector will begin with a placeholder name such as `Untitled Connector X`. Click the edit button and rename your connector to something unique and descriptive.

## Request

1. Set the request to either `GET` or `POST`. If you're not sure which request method to use, it's probably a `GET`, but please consult your third-party's API documentation.
2. Paste or add your endpoint URL.

### Authentication

:::info
The specific authentication details you enter here are only used for making test requests, and aren't saved as part of the connector - Matillion Platform only saves the authentication type. You'll be asked to enter authentication details when you set up a pipeline with this connector.
:::

Set the authentication type by clicking the dropdown.

- **Basic Auth** requires the username and password used to access the third-party service.
- **Bearer Token** requires a single bearer token from your third-party service.
- **API Key** requires a key name and the value of the key. Additionally, you can set the API key as a header or query parameter.
- **OAuth** requires an OAuth entry. Select one from the dropdown, or click **Add new OAuth**. You can also choose **Manage OAuths**

### Parameters

In the **Parameters** tab, you can specify any query or URI parameters needed to connect to your endpoint.

To add a query or URI parameter:

1. Click **Add a Query parameter** or **Add a URI parameter**.
2. Set the parameter name and value in the corresponding columns.
3. In the **Configurability** column, toggle to either **Constant** (the default) or **Configurable**. Constant parameters retain the value you specify in this setup, whereas configurable parameters are set when building the pipeline, and their value here is for testing only.
4. If you wish to discard the parameter, click **Remove** (trashcan).

:::info
You can also add query parameters by typing them at the end of the URL.
:::

### Headers

In the **Headers** tab you can specify any request headers that define the HTTP(S) interaction.

:::warning
Don't add authentication-specific headers here, use Authentication tab instead to ensure they're managed with the appropriate level of security.
:::

To add a header parameter:

1. Click **Add a Header Parameter**.
2. Set the parameter name and value in the corresponding columns.
3. In the **Configurability** column, toggle to either **Constant** (the default) or **Configurable**. Constant parameters retain the value you specify in this setup, whereas configurable parameters are set when building the pipeline, and their value here is for testing only.
4. If you wish to discard the parameter, click **Remove** (trashcan).

### Body

Any data sent from the client to your API. Only used for `POST` requests. This field is disabled for `GET` requests.

Click **Send** when you are ready.

---

### Send

Clicking **Send** will produce a response. Clicking the **Response** tab shows and hides the response body and headers, which users can inspect.

The UI also displays the status code of the request/response, for example, 200 (success).

---

## Structure

This is where you can build and edit the schema that represents the shape of your API's response. It's used later when loading your data into your destination.

Column names and data types are listed. Click **...** and then click **Edit element** if you need to edit the column name or data type. Click **delete element** if you wish to delete this column from the schema.

Click **Refresh structure** when you've finished making changes.

---

## Pagination

In this tab, you can set your pagination strategy. **No pagination** is the default setting.

---

### Relative Path paging

|Property|Description|
|---|---|
|Base URI|The URI constant to exclude from the relative path.|
|Next Page URI|The property in the response used to indicate the next page. The dropdown will display each column name as selectable.|
|Page Size Parameter|The query parameter used to specify the page size.|
|Page Size|The number of records to return per page.|

---

### Full Path paging

|Property|Description|
|---|---|
|Next Page URI|The property in the response used to indicate the next page. Click the **Choose from tree** icon to the right of the dropdown field to select one of the columns.|
|Page Size Parameter|The query parameter used to specify the page size.|
|Page Size|The number of records to return per page.|

---

### Page Based paging


|Property|Description|
|---|---|
|Page Size Parameter|The query parameter used to specify the page size.|
|Page Size|The number of records to return per page.|
|Page Number Parameter|The query parameter used to specify the page number.|
|Last Page|The property in the response used to indicate the last page.|

---

### Link Header

|Property|Description|
|---|---|
|Page Size Parameter|The query parameter used to specify the page size.|
|Page Size|The number of records to return per page.|

---

### Offset paging

|Property|Description|
|---|---|
|Limit|The number of records to return per page.|
|Record Count|Select a column from the tree to count the total records.

---

### Cursor paging

|Property|Description|
|---|---|
|Cursor|The property in the response for the cursor. Click the **Choose from tree** icon to the right of the dropdown field to select one of the columns.|
|Cursor Parameter|The name of the cursor query parameter.|
|Page Size Parameter|The query parameter used to specify the page size.|
|Page Size|The number of records to return per page.|

Click **Save** to save your connector's configuration.

Click **Connectors** in the left-hand navigation to return to the Connectors overview.

---

## Find your connector in Matillion Data Loader

You can select your newly created connector in Matillion Data Loader. Click **Choose source** after clicking **Add pipeline**. Matillion Data Loader lists sources alphabetically. You can use the search field to filter.

---

## Connector actions

- To edit a connector, click the edit (pencil) icon.
- To delete a connector, click the delete (trashcan) icon and then click **Yes, delete** to confirm; or click **Never mind** to cancel deletion.
- To download and export the connector for use in Matillion ETL, click the export icon.

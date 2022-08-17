## Overview

Connectors created in Matillion Custom Connectors can be exported to Matillion ETL as an **API Extract Profile** for use in Matillion ETL orchestration jobs.

This is a two-step process:

1. [Export](#export-the-cyoc-connector) the connector from Custom Connectors as a JSON file.
2. [Import](#import-the-connector-into-matillion-etl) the JSON file into Matillion ETL using the **Manage Extract Profiles** feature.

---

## Export the connector

This process assumes you have already created a suitable connector in Custom Connectors. Read [_Connectors Overview_](connectors-overview.md) for details.

To export a connector:

1. In Custom Connectors, navigate to **Connectors**.

2. Click the **Download Connector Export** icon to the right of the connector you want to export.

3. The connector will be written to your default download location (depending on your browser and operating system) as a `.json` format file, with the name `<connector name>.json`. For example: `Finance API Connector.json`.

The export is now complete. Navigate to Matillion ETL and import the connector.

---

## Import the connector into Matillion ETL

In Matillion ETL, you need to create an API Extract Profile using the exported connector. To create the profile:

1. In your Matillion ETL instance, click **Project** > **Manage API Profiles** > **Manage Extract Profiles**.

2. In the **Manage Extract Profiles** dialog, click the upload button in the lower left.

3. Browse to the location of the `.json` file you exported from Custom Connectors and select the file. You should see the message "API Extract File was uploaded successfully", indicating that the file is in an acceptable format and has imported correctly. Click **OK**.

4. The new profile is now listed in the **Manage Extract Profiles** dialog, and is ready for you to use in orchestration jobs. The profile will have the name it was given in Custom Connectors. You can perform further configuration of the profile here if you wish to edit the endpoints or add more endpoints, but this shouldn't be necessary if the connector was correctly configured in Custom Connectors.

5. Click **OK** to close the dialog.

6. To use the connector in an orchestration job, add an **API Extract** component to the job canvas and configure the following properties for it:
    - **Profile**: Select the profile you have imported.
    - **Data Source**: Select from the list of endpoints. All the endpoints you created for the connector in Custom Connectors will be available for use as the Data Source.

For more information about configuring extract profiles in Matillion ETL, read [_Manage Extract Profiles_](/docs/7505305).

For more information about using the API Extract component, read [_API Extract_](/docs/1959484).

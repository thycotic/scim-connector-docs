[title]: # (Reports)
[tags]: # (configuration)
[priority]: # (213)
# Reports Generated for Secret Server

After the Thycotic SCIM Connector has been installed and configured, custom reports are generated in Secret Server. These reports are used for transactions and filtering.

>**Note**: To reduce the access privileges for the SCIM connector, you can create the reports manually in Secret Server and remove the "Administer Reports" rights from the application role that was created in Secret Server.

To manually generate the reports in Secret Server, locate the SQL files in the SQL directory on the web server:

For each file that is in the SQL directory:

1. Open the SQL file.
1. Copy the SQL statement.
1. Execute it in Secret Server.

1. Navigate to __Reports | Add new report | Paste__ the SQL statement into the SQL report section.
The Report name must be the same as the file name.
   * Report category:__<explain>__
   * Chart type: __None__
   * Page size:

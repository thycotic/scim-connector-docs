[title]: # (App Settings)
[tags]: # (json)
[priority]: # (204)
# AppSettings.json

AppSettings.json can located in the `root\Responses` folder of the SCIM Connector Web Directory.

   >**Note:** Settings are provided here for informational purposes. This file should not be modified directly unless directed by Thycotic Support or Professional Services. Incorrect values may cause SCIM Connector to stop working or return incorrect results. To modify configurable settings, log into the SCIM Connector user interface and select the Settings page then the Configuration Settings tab.These settings are global settings and will impact the performance of all connected endpoints.

__BULK_MAX_OPERATIONS__:

Max operations allowed in a single bulk call.
   * Default: 1000

__BULK_MAX_PAYLOAD__:

Max number of bytes allowed in a single bulk call.
   * Default: 1048576

__EXPIRY_TOKEN_TIME_MIN__:

Token timeout when logging into the user interface.
   * Default: 60

__NON_EXPIRY_TOKEN_TIME_DAYS__:

Token timeout for SCIM Connector Endpoints.
   * Default: 730

__CONFIG_FILE_PATH__:

Override for where the Settings.enc is stored.

__CONFIG_FILE_NAME__:

Encrypted file that stored Secret Server connection information.
   * Default: Settings.enc

__CERT_NAME__:

Deprecated.
   * Default: CN=SSScim

__LOG_PATH__:

Override that allows the log files to be written to a different path.

__NOTIFICATION_PATH__:

Deprecated.

__LOG_FREQUENCY__:

Determines when a new log file is generated. Old log files are not deleted.
   * Default: Hourly

__Allow_Endpoint_HTTP__:

Determines if http communication is allowed.
   * Default: False

__SCIM_Connector_Disabled__:

When true, SCIM Connector will not process requests.
   * Default: False

__SCIM_Threshold__:

Number of errors in a row before SCIM Connector will automatically disable itself.
   * Default: 20

__SS_SCIMEndpoint_Folder_Name__:

Deprecated.
   * Default: SCIMEndpoints

__SS_SCIM_Secret_Name__:

Prepend to the Secret Name for the sharing access to SCIM Connector.
   * Default: SCIMSecret

__SS_TOKEN_ENDPOINT__:

Secret Server Endpoint for obtaining a token.
   * Default: /oauth2/token

__VERIFY_ENDPOINT__:

SCIM Connector Endpoint for retrieving SCIM Catalog.
   * Default: /v2/ServiceProviderConfig

__SS_Domain__:

Default domain used when calling Secret Server for authentication.
   * Default: local

__SS_GrantType__:

Default Secret Server Authentication type.
   * Default: password

__SS_UsersFilterUrl__:

Secret Server Endpoint for retrieving users using a search filter.
   * Default: /api/v1/users?skip=0&take=999999999&filter.includeInactive=true&filter.searchText={0}

__SS_UsersByIDUrl__:

Secret Server Endpoint for retrieving a user (ID is appended).
   * Default: /api/v1/users/

__SS_UsersByIDGroupsUrl__:

Secret Server Endpoint for retrieving groups by ID.
   * Default: /api/v1/users/{0}/groups?skip=0&take=999999999

__SS_GroupsFilterUrl__:

Secret Server Endpoint for retrieving groups with a filter.
   * Default: /api/v1/groups?skip=0&take=999999999&filter.includeInactive=true&filter.searchText={0}

__SS_GroupsByIDUrl__:

Secret Server Endpoint for retrieving groups (ID is appended).
   * Default: /api/v1/groups/

__SS_GroupsByIDUsersUrl__:

Secret Server Endpoint for a group and all users within the group.
   * Default: /api/v1/groups/{0}/users?skip=0&take=999999999

__SS_CreateUpdateUsersUrl__:

Secret Server Endpoint to update a user.
   * Default: /api/v1/Users/

__SS_Current_User__:

Secret Server Endpoint to retrieve the logged in user.
   * Default: /api/v1/users/current

__SS_CreateUpdateGroupsUrl__:

Secret Server Endpoint to update or create a group.
   * Default: /api/v1/Groups/

__SS_CreateUserInGroupsUrl__:

Secret Server Endpoint to update or add a user to a group.
   * Default: /api/v1/Groups/{0}/users/

__SS_DeleteUserFromGroupUrl__:

Secret Server Endpoint to remove a user from a group.
   * Default: /api/v1/Groups/{0}/users/{1}

__SS_ReportUserAcivityUrl__:

Secret Server Endpoint execute a report.
   * Default: /api/v1/reports/execute

__SS_FoldersFilterUrl__:

Secret Server endpoint to retrieve folders.
   * Default: /api/v1/folders?skip=0&take=999999999

__SS_FolderPermissionsByIDUrl__:

Secret Server endpoint to retrieve folder permissions by folder id.
   * Default: /api/v1/folder-permissions?filter.folderid=

__SS_CreateFolderPermission__:

Secret Server endpoint to create or add folder permissions.
   * Default: /api/v1/folder-permissions/

__SS_CreateSecretPermission__:

Secret Server endpoint to create or add secret permissions.
   * Default: /api/v1/secret-permissions/

__SS_CreateFolder__:

Secret Server endpoint to create or add folder.
   * Default: /api/v1/folders/

__SS_CreateSecret__:

Secret Server endpoint to create or add secrets.
   * Default: /api/v1/secrets/

__SS_Add_Secret_Into_Folder__:

Secret Server add a secret to a folder.
   * Default: /api/v1/secrets/{0}/general

__SS_FolderSecretsByIDUrl__:
Secret Server endpoint to retrieve a Secret by ID.
* Default: /api/v1/Secrets?filter.folderId={0}

__SS_SecretsFilterUrl__:

Secret Server endpoint to retrieve a Secret by ID with a filter.
   * Default: /api/v1/secrets?skip=0&take=999999999&filter.searchText={0}

__SS_RestrictedSecretsFilterUrl__:

   * Default: /api/v1/secrets?paging.filter.includeRestricted=true&paging.filter.folderid={0}&paging.filter.permissionRequired=1&paging.filter.doNotCalculateTotal=true&paging.sortBy[0].name=name&paging.sortBy[0].direction=Asc&paging.take=999999999

__SS_FolderSecretsByIDUrls__:

Secret Server endpoint to retrieve a Secrets by folder.
   *Default: /api/v1/secrets?skip=0&take=999999999&filter.folderId={0}

__SS_SecretPermissionsByIDUrl__:

Secret Server endpoint to retrieve a Secret Permissions by ID.
   * Default: /api/v1/secret-permissions?filter.secretId=

__SS_ALL_USER__:

Secret Server endpoint execute reports.
   * Default: /api/v1/reports/execute

__SS_ALL_REPORT__:

Secret Server endpoint execute reports returning all results.
   * Default: /api/v1/reports?skip=0&take=999999999

__SS_CREATE_CUSTOM_REPORT__:

Secret Server endpoint Create reports.
   * Default: /api/v1/reports/

__SS_REPORT_ALL_USER__:

SCIM All Users.

__SS_REPORT_ALL_USER_GROUPS__:

Report name used by SCIM Connector.
   * Default: SCIM All User Groups

__SS_REPORT_ALL_GROUP__:

Report name used by SCIM Connector.
   * Default: SCIM All Groups

__SS_REPORT_ALL_FOLDERS__:

Report name used by SCIM Connector.
   * Default: SCIM All Folders

__SS_REPORT_ALL_SECRETS__:

Report name used by SCIM Connector.
   * Default: SCIM All Secrets

__SS_REPORT_ALL_FOLDERS_PERMISSION__:

Report name used by SCIM Connector.
   * Default: SCIM All Folders Permission

__SS_REPORT_ALL_SECRETS_PERMISSION__:

Report name used by SCIM Connector.
   * Default: CIM All Secrets Permission

__SS_USERCATEGORYID__:

Report Category ID used by SCIM Connector.
   * Default: 2

 __SS_GROUPCATEGORYID__:

Report Category ID used by SCIM Connector.
   * Default: 7

__SS_FOLDERCATEGORYID__:

Report Category ID used by SCIM Connector.
   * Default: 3

__SS_SECRETCATEGORYID__:

Report Category ID used by SCIM Connector.
   * Default: 4

__APP_NAME__:

Deprecated.
   * Default: SCIMConnector

__SocketURL__:

wss://\$\$Host\$\$/Server/ServerSocket.ashx?channel=messages.

__SQL_FILE_NAME_ALL_FOLDERS__:

SS_Report_All_Folders.

__SQL_FILE_NAME_ALL_SECRETS__:

SS_Report_All_Secrets.

__SQL_FILE_NAME_ALL_FOLDERS_PERMISSION__:

SS_Report_All_Folders_Permission.

__SQL_FILE_NAME_ALL_SECRETS_PERMISSION__:

SS_Report_All_Secrets_Permission.

__SS_SecretByIDUrl__

/api/v1/secrets/.

 __SS_SecretFieldsByIDUrl__:

 /api/v1/secret-templates/.

__SS_WebPasswordSecretTemplateID__:
9.

__SS_All_Folders__:

/api/v1/folders?skip=0&take=999999999&filter.searchText={0}.

__SS_CurrentUser__:

/api/v1/users/current.

__SS_All_User_SecretPermissions__:

/api/v1/secret-permissions?filter.userid={0}&filter.secretId={1}.

__SS_All_Group_SecretPermissions__:

/api/v1/secret-permissions?filter.groupid={0}&filter.secretId={1}.

__SS_CreateSecretPermissions__:

/api/v1/secret-permissions/.

__SS_SecretApproval__:

/api/v1/secrets/{0}/security-approval.

__SS_SecretAccessRequest__:

/api/v1/secret-access-requests.

__SS_FilterSecretAccessRequestBySecretId__:

/api/v1/secret-access-requests/secrets/{0}.

__SS_Admin_Permission__:

First time setup this is the permission name that is checked to ensure the user has administrator rights.
   * Default: Administer Role Permissions

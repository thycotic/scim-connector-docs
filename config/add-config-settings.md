[title]: # (Additional Configuration and settings storage)
[tags]: # (configuration)
[priority]: # (203)
# Additional Configuration and settings storage

**There are three files local to the SCIM Connector that contain important
Settings and Configuration options: Web.config, Settings.enc, and
AppSettings.json**

**Web.config – located in the root of the SCIM Connector Web Directory**

**While the Web.Config contains standard web application information it also
contains encrypted values that are required to decrypt the settings.enc. The
values to decrypt the settings.enc are also encrypted using IIS built in machine
RSA Protected Configuration Provider**

**The encrypted keys will appear as CipherData in the web.config. It is critical
that these entries are not modified or deleted. Without these values, the
Settings.enc cannot be decrypted. If the web.config is deleted or the data in
the CipherData sections are changed or deleted, settings.enc will need to be
deleted and SCIM Connector Settings will need to be re-entered**

\<CipherData\>

\<CipherValue\>

oqXTmtY1NwaK38Wj7HGeIozZo9K3JgWkkmU3w7619DqovQYBY9UeSHTbkd8YGc7ZbcJ6doyCEUfkuTSVuFslCsL8+0gIwl0d1Ni/Nyha4q7DhADj8MBq/aUn5SfrJd+x7Z+TDJ2in/5klJ2EFmLeZBq7inC5aqIOeZ0ydAD0P+sKhrdeBrN2e6T4rXG3z++cnDcD0iUejPnc/yI+M5gy+QKkqlATlp7fpWGfgAczss45V0pwcko/9FRzmA==

\</CipherValue\>

\</CipherData\>

\<CipherData\>

\<CipherValue\>

81fekLRnjFbNN6wEhfj6YbbiznDcIBSzkF46EKBuNDYz+tlgb7whnut/C4QxkVV87wDWBZhiIE1jM+2UhiikM8nznqsfxpVk01XCEyTj7F2U4/PNATlomTubsK6cVOtgY7dMchou8MYw6HQb+Y/WaA68rFGMagYteIgt5GgQGfuhRDdZjWzxaeCHeVljveNh24jyzy7wdlFQ2HGS/m+7lAL705cbDPIanRKFAaoXfiuFtXfAmS5vHV9Uqdwrs86JT

\</CipherValue\>

\</CipherData\>

**Additionally, the web.config will contain the machine key which is necessary
for some decryption purposes. Do not modify or delete the machine key value from
the web.config or SCIM Connector will fail to be able to function.**

**If either of the above settings in the web.config are modified or corrupted,
the settings.enc will need to be deleted and SCIM Connector Settings will need
to be reentered.**

**Settings.enc – located in the root of the SCIM Connector Web Directory. Do not
modify or delete this file. For each Secret Server that is connected to the SCIM
Connector required information is stored in the Settings.enc. This file is
encrypted to ensure sensitive information is not viewable or accessible. If the
settings.enc is modified, decryption will fail, and the file will need to be
deleted and SCIM Connector Settings will need to be re-entered**

**Encrypted data that includes:**

**Secret Server URL**

**Secret Server Application Username**

**Secret Server Application Account Password**

**SCIM Connector Secret ID**

**SCIM Connector Secret Folder ID**

dJj511YhAArtIskEbGEK4UKycONTAPGTaKdQTuqEGUQpr5aygCqzO4dGKlkCMOKE+pw2IviCRifFiuF3U3BOzAdldMdQWGp6u65EmRPSXv8F7rA9yDvtCrAd775F2vKSEvRFgjIdyfc5/MXMULH/cU4JrHHbJd+LX6EvdcXRtvieZYFC/hiEjnGA3E2E3RJGUtW/wCO4gR3VuIukcbKb6P+V/oQeObXZxEEki3JgwY2Q9WEbW8LpL+SHso+AHW8bX5SU/bQX+vgaLrhNgnEeHCzqRuPU3Knv8FKDf0PbrK2KC13DPYbnrn2FIxL89bfw6PRLCru1wxNfyTEEIg8HxvCefOOmGF+TL0fd19i6rt1vanyYPXUBhpCGg8udvkxWGuHc6ogoHQeeFOF8g09Dwm2jx060i4IKSRGOTwtShY7V6fahioQ5QpEuhDXHLnYs9ekuZHz+8Vc0Az43L1Ce+WiTKWq0qdPQ4Mj6/COeA482/CvaFoCcnAWqFFQQjBT6CwEX/ziK0ILp1rrVzIadNc4TdQNOTw7Kl7+pdqJRokWCwkR1A0baQuC6ZFu45DqIZRg+lynk7BrG7J/FnIPn3A==

**AppSettings.json – located in the root\\Responses folder of the SCIM Connector
Web Directory**

**Settings are provided here for informational purposes. This file should not be
modified directly unless directed by Thycotic Support or Professional Services.
Incorrect values may cause SCIM Connector to stop working or return incorrect
results. To modify configurable settings, log into the SCIM Connector user
interface and select the Settings page then the Configuration Settings tab.
These settings are global settings and will impact the performance of all
connected endpoints.**

1.  "BULK_MAX_OPERATIONS": "1000" --- Max operations allowed in a single bulk
    call

2.  "BULK_MAX_PAYLOAD": "1048576" --- Max number of bytes allowed in a single
    bulk call

3.  "EXPIRY_TOKEN_TIME_MIN": "60", --- Token timeout when logging into the user
    interface

4.  "NON_EXPIRY_TOKEN_TIME_DAYS": "730" --- Token timeout for SCIM Connector
    Endpoints

5.  "CONFIG_FILE_PATH": "" --- Override for where the Settings.enc is stored

6.  "CONFIG_FILE_NAME": "Settings.enc" --- Encrypted file that stored Secret
    Server connection information

7.  "CERT_NAME": "CN=SSScim" --- Deprecated

8.  "LOG_PATH": "" --- Override that allows the log files to be written to a
    different path

9.  "NOTIFICATION_PATH": "" --- Deprecated

10. "LOG_FREQUENCY": "Hourly" --- Determines when a new log file is generated.
    Old log files are not deleted

11. "Allow_Endpoint_HTTP": "false" --- Determines if http communication is
    allowed

12. "SCIM_Connector_Disabled": "false" --- When true, SCIM Connector will not
    process requests

13. "SCIM_Threshold": "20" --- Number of errors in a row before SCIM Connector
    will automatically disable itself

14. "SS_SCIMEndpoint_Folder_Name": "SCIMEndpoints" --- Deprecated

15. "SS_SCIM_Secret_Name": "SCIMSecret" ---- Prepend to the Secret Name for the
    sharing access to SCIM Connector

16. "SS_TOKEN_ENDPOINT": "/oauth2/token" --- Secret Server Endpoint for
    obtaining a token

17. "VERIFY_ENDPOINT": "/v2/ServiceProviderConfig" --- SCIM Connector Endpoint
    for retrieving SCIM Catalog

18. "SS_Domain": "local" --- Default domain used when calling Secret Server for
    authentication

19. "SS_GrantType": "password" --- Default Secret Server Authentication type

20. "SS_UsersFilterUrl":
    "/api/v1/users?skip=0&take=999999999&filter.includeInactive=true&filter.searchText={0}"
    --- Secret Server Endpoint for retrieving users using a search filter

21. "SS_UsersByIDUrl": "/api/v1/users/" --- Secret Server Endpoint for
    retrieving a user (ID is appended)

22. "SS_UsersByIDGroupsUrl": "/api/v1/users/{0}/groups?skip=0&take=999999999"
    --- Secret Server Endpoint for retrieving groups by ID

23. "SS_GroupsFilterUrl":
    "/api/v1/groups?skip=0&take=999999999&filter.includeInactive=true&filter.searchText={0}"
    --- Secret Server Endpoint for retrieving groups with a filter

24. "SS_GroupsByIDUrl": "/api/v1/groups/" --- Secret Server Endpoint for
    retrieving groups (ID is appended)

25. "SS_GroupsByIDUsersUrl": "/api/v1/groups/{0}/users?skip=0&take=999999999"
    --- Secret Server Endpoint for a group and all users within the group

26. "SS_CreateUpdateUsersUrl": "/api/v1/Users/" --- Secret Server Endpoint to
    update a user

27. "SS_Current_User": "/api/v1/users/current" --- Secret Server Endpoint to
    retrieve the logged in user

28. "SS_CreateUpdateGroupsUrl": "/api/v1/Groups/" --- Secret Server Endpoint to
    update or create a group

29. "SS_CreateUserInGroupsUrl": "/api/v1/Groups/{0}/users/" --- Secret Server
    Endpoint to update or add a user to a group

30. "SS_DeleteUserFromGroupUrl": "/api/v1/Groups/{0}/users/{1}" --- Secret
    Server Endpoint to remove a user from a group

31. "SS_ReportUserAcivityUrl": "/api/v1/reports/execute" --- Secret Server
    Endpoint execute a report

32. "SS_FoldersFilterUrl": "/api/v1/folders?skip=0&take=999999999" --- Secret
    Server endpoint to retrieve folders

33. "SS_FolderPermissionsByIDUrl": "/api/v1/folder-permissions?filter.folderid="
    --- Secret Server endpoint to retrieve folder permissions by folder id

34. "SS_CreateFolderPermission": "/api/v1/folder-permissions/" --- Secret Server
    endpoint to create or add folder permissions

35. "SS_CreateSecretPermission": "/api/v1/secret-permissions/" --- Secret Server
    endpoint to create or add secret permissions

36. "SS_CreateFolder": "/api/v1/folders/"--- Secret Server endpoint to create or
    add folder

37. "SS_CreateSecret": "/api/v1/secrets/"--- Secret Server endpoint to create or
    add secrets

38. "SS_Add_Secret_Into_Folder": "/api/v1/secrets/{0}/general" --- Secret Server
    add a secret to a folder

39. "SS_FolderSecretsByIDUrl": "/api/v1/Secrets?filter.folderId={0}" --- Secret
    Server endpoint to retrieve a Secret by ID

40. "SS_SecretsFilterUrl":
    "/api/v1/secrets?skip=0&take=999999999&filter.searchText={0}" --- Secret
    Server endpoint to retrieve a Secret by ID with a filter

41. "SS_RestrictedSecretsFilterUrl":
    "/api/v1/secrets?paging.filter.includeRestricted=true&paging.filter.folderid={0}&paging.filter.permissionRequired=1&paging.filter.doNotCalculateTotal=true&paging.sortBy[0].name=name&paging.sortBy[0].direction=Asc&paging.take=999999999"

42. "SS_FolderSecretsByIDUrls":
    "/api/v1/secrets?skip=0&take=999999999&filter.folderId={0}" --- Secret
    Server endpoint to retrieve a Secrets by folder

43. "SS_SecretPermissionsByIDUrl": "/api/v1/secret-permissions?filter.secretId="
    --- Secret Server endpoint to retrieve a Secret Permissions by ID

44. "SS_ALL_USER": "/api/v1/reports/execute" --- Secret Server endpoint execute
    reports

45. "SS_ALL_REPORT": "/api/v1/reports?skip=0&take=999999999" --- Secret Server
    endpoint execute reports returning all results

46. "SS_CREATE_CUSTOM_REPORT": "/api/v1/reports/" --- Secret Server endpoint
    Create reports

47. "SS_REPORT_ALL_USER": "SCIM All Users"

48. "SS_REPORT_ALL_USER_GROUPS": "SCIM All User Groups" --- Report name used by
    SCIM Connector

49. "SS_REPORT_ALL_GROUP": "SCIM All Groups" --- Report name used by SCIM
    Connector

50. "SS_REPORT_ALL_FOLDERS": "SCIM All Folders" --- Report name used by SCIM
    Connector

51. "SS_REPORT_ALL_SECRETS": "SCIM All Secrets" --- Report name used by SCIM
    Connector

52. "SS_REPORT_ALL_FOLDERS_PERMISSION": "SCIM All Folders Permission" --- Report
    name used by SCIM Connecto

53. "SS_REPORT_ALL_SECRETS_PERMISSION": "SCIM All Secrets Permission" --- Report
    name used by SCIM Connector

54. "SS_USERCATEGORYID": "2" --- Report Category ID used by SCIM Connector

55. "SS_GROUPCATEGORYID": "7" --- Report Category ID used by SCIM Connector

56. "SS_FOLDERCATEGORYID": "3" --- Report Category ID used by SCIM Connector

57. "SS_SECRETCATEGORYID": "4” --- Report Category ID used by SCIM Connector

58. "APP_NAME": "SCIMConnector", --- Deprecated

59. "SocketURL": "wss://\$\$Host\$\$/Server/ServerSocket.ashx?channel=messages"

60. "SQL_FILE_NAME_ALL_FOLDERS": "SS_Report_All_Folders"

61. "SQL_FILE_NAME_ALL_SECRETS": "SS_Report_All_Secrets"

62. "SQL_FILE_NAME_ALL_FOLDERS_PERMISSION": "SS_Report_All_Folders_Permission"

63. "SQL_FILE_NAME_ALL_SECRETS_PERMISSION": "SS_Report_All_Secrets_Permission"

64. "SS_SecretByIDUrl": "/api/v1/secrets/"

65. "SS_SecretFieldsByIDUrl": "/api/v1/secret-templates/"

66. "SS_WebPasswordSecretTemplateID": "9"

67. "SS_All_Folders":
    "/api/v1/folders?skip=0&take=999999999&filter.searchText={0}"

68. "SS_CurrentUser": "/api/v1/users/current"

69. "SS_All_User_SecretPermissions":
    "/api/v1/secret-permissions?filter.userid={0}&filter.secretId={1}"

70. "SS_All_Group_SecretPermissions":
    "/api/v1/secret-permissions?filter.groupid={0}&filter.secretId={1}"

71. "SS_CreateSecretPermissions": "/api/v1/secret-permissions/"

72. "SS_SecretApproval": "/api/v1/secrets/{0}/security-approval"

73. "SS_SecretAccessRequest": "/api/v1/secret-access-requests"

74. "SS_FilterSecretAccessRequestBySecretId":
    "/api/v1/secret-access-requests/secrets/{0}"

75. "SS_Admin_Permission": "Administer Role Permissions" --- First time setup
    this is the permission name that is checked to ensure the user has
    administrator rights.

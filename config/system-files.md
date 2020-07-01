[title]: # (System Files)
[tags]: # (configuration)
[priority]: # (211)
# SCIM Connector System Files

This section will cover any other topics that might be relevant.

## Log files

* Default log location is `<application root directory>/Log directory`
* Default naming convention for log files is `<YEAR><MONTH><DAY><HOUR>`. For example: `2019030904.log`.

## Encrypted Configuration File

* File Name: `settings.enc`
* Default location: Application root directory

## Web.config file

The `web.config` file contains encrypted information regarding endpoints and application configuration options:

```xml
<appSettings>
    <add key="CONFIG_FILE_PATH" value="" />
    <add key="CONFIG_FILE_NAME" value="settings.enc" />
    <add key="LOG_PATH" value=" <Application Root File Path> \\Log" />
    <add key="NOTIFICATION_PATH" value="" />
    <add key="SCIM_BASE_URL" value="http:// <SCIM Server domain name or IP address>/SSI" />
    <add key="SS_BASE_URL" value="https:// <Secret Server domain name or IP address>/SecretServer" />
    <add key="SS_TOKEN_ENDPOINT" value="/oauth2/token" />
    <add key="SS_Domain" value="local" />
    <add key="SS_GrantType" value="password" />
    <add key="SS_UsersFilterUrl" value="/api/v1/users?skip=0\&amp;take=999999999" />
    <add key="SS_UsersByIDUrl" value="/api/v1/users/" \>
    <add key="SS_UsersByIDGroupsUrl" value="/api/v1/users/{0}/groups?skip=0\&amp;take=999999999" />
    <add key="SS_GroupsFilterUrl" value="/api/v1/groups?skip=0\&amp;take=999999999"/>
    <add key="SS_GroupsByIDUrl" value="/api/v1/groups/" />
    <add key="SS_GroupsByIDUsersUrl" value="/api/v1/groups/{0}/users?skip=0\&amp;take=999999999" />
    <add key="SS_CreateUpdateUsersUrl" value="/api/v1/Users/" />
    <add key="SS_CreateUpdateGroupsUrl" value="/api/v1/Groups/" />
    <add key="SS_CreateUserInGroupsUrl" value="/api/v1/Groups/{0}/users/" />
    <add key="SS_DeleteUserFromGroupUrl" value="/api/v1/Groups/{0}/users/{1}" />
    <add key="SS_ReportUserActivityUrl" value="/api/v1/reports/execute" />
    <add key="SS_FoldersFilterUrl" value="/api/v1/folders?skip=0\&amp;take=999999999" />
    <add key="SS_FolderPermissionsByIDUrl" value="/api/v1/folder-permissions?filter.folderid=" />
    <add key="SS_FolderSecretsByIDUrl" value="/api/v1/Secrets?filter.folderId={0}"/>
    <add key="SS_SecretsFilterUrl" value="/api/v1/secrets?skip=0\&amp;take=999999999" />
    <add key="SS_SecretPermissionsByIDUrl" value="/api/v1/secret-permissions?filter.secretId=" />
</appSettings>
```

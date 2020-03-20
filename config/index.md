[title]: # (Setting up SCIM)
[tags]: # (connecting,configuration)
[priority]: # (200)
# SCIM Connector Set Up

## Connecting to Secret Server

Before making a connection to Secret Server from the SCIM Connector application, there are some configuration requirements to set in Secret Server.

## Required Secret Server Configuration

1. Create a new user in Secret Server.
2. Select the __Advanced__ option.
3. Mark the account as an __Application Account__.  

>**Important**: Be sure to remember the user name and password for this account because you are required to enter this information into the SCIM Connector application.  

>**Note**: After the configuration is complete, if you are having difficulty displaying the PAM containers and data in SailPoint, we recommend you come back into Secret Server and switch this account back to a standard licensed account instead of the application account.

### Permissions

#### Role-Level Permissions

Permissions are applied at the role level. To give the correct permissions to the SCIM Connector application, create a role, and add the following permissions:

- Add Secret
- Administer Create Users
- Administer Groups
- Administer Reports
- Administer Users
- View Folders
- View Groups
- View Reports
- View Secret
- View Users

These are the minimum required permissions.

#### Special Considerations

If the SCIM endpoints do not make changes to secrets, users, groups or group membership, consider using these permissions:

- Administer Reports
- View Folders
- View Groups
- View Reports
- View Secret
- View Users

Once the role has been created, you can assign the application account to the
newly created role.

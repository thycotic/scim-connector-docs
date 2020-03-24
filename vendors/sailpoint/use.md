[title]: # (Using SailPoint IdentityIQ)
[tags]: # (third-party)
[priority]: # (3)
# Using SailPoint IdentityIQ After a Connection Is Made

Once SailPoint IdentityIQ is configured to work as an endpoint for the SCIM Connector and a connection has been established from the SCIM Connector itself, users can run actions directly from IdentityIQ.

## Examples

###  Adding a User to a Group

1. In the main SailPoint dashboard, click the menu icon in the top left corner and select __Manage Access__.
1. Click to select the __Manage User Accounts__ sub-option.
1. Search for the user name for the account that you want to add to a group. 
1. Once the user is found, click to select the radio button in the top left corner of the user card. The button turns green.
1. Click __Next__.
1. Search to find the group that the user should be added into.
1. Click to select the checkmark circle in the top left corner of the user card. The circle turns green.
1. Click __Next__.
1. Review the setting to ensure the correct user and group are selected.
1. Click __Submit__ at the bottom of the page to complete the action.

After add the user to the group, you should be able to view their access to the container on the Privileged Account Management page, and they will be listed in the Effective Access tab for the container that the group is applied to.

Please see the [SailPoint Documentation](index.md) section for more information on navigating SailPoint IdentityIQ.

#### Directly Adding a User to a Container

1. In the main SailPoint dashboard, click the menu icon in the top left corner and select __Manage Access__ from the menu that opens.
1. Click to select the __Privileged Account Management__ sub-option. The Privileged Account Management page appears, and you see all of the PAM containers and folders the logged in user has access to. 
1. Find the container you want to add access to (manually or using the search feature).
1. Click __Manage__ at the bottom of that container box.
1. Click __Add Identities__ on the right-hand side. This starts the process of giving a user direct permissions access to the container. The Choose Identities dialog opens.
1. Search for the user account that should be added. 
1. Click __Next__ to continue. The dialog name changes to Add Container Permissions, and you now can select the access level you want to apply to the account. 
1. Click to select the check box for the permission you want to add.
1. Click __Submit__ to complete the action.

After the user has been added to the container, you should be able to view their access to the container on the Privileged Account Management page, and they should be listed in the Direct Access tab.

Please see the [SailPoint Documentation](index.md) section for more information on navigating SailPoint IdentityIQ.

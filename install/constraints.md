[title]: # (Best Practices and Implementation Considerations)
[tags]: # (best practices)
[priority]: # (106)
# SCIM Connector Best Practices for Integration With Secret Server

### Introduction

This document is intended to provide best practices in relation to configuring
SCIM for use with Secret Server. While we try to generalize much of the
suggestions within this document so that it can apply to others vendors that are
leveraging SCIM, we have chosen to work directly with Sailpoint as a partner for
the development of this document. This means that some of the documentation does
include screenshots specific to Sailpoint’s IdentityIQ interface and
configuration. We also reiterate Sailpoint specific limitations and concepts and
walk through a few typical use cases that may be specific to Sailpoint.

### Broad SCIM Implementation Considerations

-   Secret Server does not delete users in order to maintain audit trails. As a
    result, when you delete a user with a SCIM call, it disables the user. The
    disabled user cannot be granted access to a container, privileged data, or
    group unless they are enabled again.

-   Secret Server throws an error if instructed to delete an already deleted
    user. Disabling (deleting) already disabled users (by ID) will result in the
    SCIM Connector reporting a 404 error in the logs.

-   The process for provisioning local user accounts versus adding AD accounts
    to Secret Server via SCIM may look vastly different based on each vendor. If
    you do plan to leverage local accounts in Secret Server, it is recommended
    in your SCIM provider to auto-create passwords that align with the local
    user password policy configured within Secret Server. Otherwise you may get
    an error when generating a new account through SCIM that does not conform to
    the Secret Server Local User password requirements. This can be found in
    Admin \> Configuration \> Local User Passwords. Below is a screenshot of the
    local user password requirement that will clear our security hardening
    report.

   ![](images/6d14a0bdb2e315ba7b01e097ea3b2857.png)

-   Some SCIM providers when creating an Application define an “Owner” of that
    application. This owner may be leveraged for approvals of some requests
    within the SCIM Server. It is important to think about who you want the
    Application owners to be. This often may be aligned with Secret Server SMEs
    but may also be aligned with “approvers” that you use within Secret Server
    for Request Access For Approval workflows.

-   Careful consideration should be made when determining who should have access
    to the “SCIM Connector Secret” that is stored within Secret Server long
    term. Those who are Administering the SCIM Connector should have access to
    this Secret, but likely no other users except for possibly a Secret Server
    SME/Admin. This is because this Secret Contains legitimate account
    information for an API user within Secret Server. It is recommended to
    combine this Secret with a Request For Access workflow process for any
    additional users that may request access to this Secret outside of your
    initial defined list of users. This flow is documented in our recently
    published SCIM 2.5 documentation.

   ![](images/3c322a7ac085da22005adf85c2c5ddea.png)

-   It is recommended to track where all within your environment your SCIM API
    user account is being leveraged so that you can ensure that account does not
    have access to secrets or folders that you do not want it to have access to.
    Since the account has privileged access within Secret Server, this is
    important. You may even want to align specific event subscriptions within
    Secret Server to track the activity of SCIM. There are several reports that
    are generated when using SCIM to help track this type of activity as well
    that can be sent to specific people on a schedule. Below is a list of the
    built in reports that are generated and can be used:

    -   SCIM All Users

    -   SCIM All Groups

    -   SCIM All User Groups

    -   SCIM All Folders

    -   SCIM All Folder Permissions

    -   SCIM All Secrets

    -   SCIM All Secrets Permissions

-   It is important to be mindful of this setting under **Admin \> Configuration
    \> Folders.**

   ![](images/568fbe51fcde509cb30e9b65f7b82ae6.png)

If this is set to Yes, which is a best practice within Secret Server, you will
need to be careful when breaking inheritance to assign permissions to a user to
a subfolders from your SCIM provider. If for example they are assigned “View”
access to a subfolder but not the parent folder, then they may not be able to
navigate to the folder that they have been provisioned access to. If this
setting is unchecked, they will be able to view the folder structure and access
the specific subfolder they’ve been regardless of parent folder level access.

### Sailpoint Specific Concepts and Limitations

<https://docs.thycotic.com/scim/2.0.0/vendors/sailpoint/sp-constraints.md>

-   In SailPoint IdentityIQ, there are “containers” and “privileged data.” The
    containers map to Secret Server folders, and privileged data maps to
    secrets.

-   SailPoint allows adding permissions to containers, but they cannot be
    directly added to privileged data. That is, they cannot be added directly to
    a Secret Server Secret. So when a user gets access to a container, the user
    is really getting access to a Secret Server folder.

-   While there is no direct way to give users access to a specific secret, they
    can still be given access indirectly by adding a user into a group that
    already has access to both the folder/container and the secret/privileged
    data.

-   When a users are given access to a container/folder, either with direct
    access or by adding them to a group, they only have “view” access to the
    container. More granular assignment of permission levels can only be defined
    in SS.

-   If the “view” permission setting seen in the Configuring a “SailPoint
    IdentityIQ Endpoint” section is not configured correctly, an incorrectly
    formatted POST call to the SCIM Connector application will result, which
    returns a HTTP 400 error message.

-   Any sensitive information that is associated with a secret/privileged data,
    such as a password, is not shared over the SCIM Connector and must be viewed
    in SS.

-   Personal folders in Secret Server can be viewed in SailPoint, but users
    cannot be given direct access to the folders. However, users can be given
    access by adding them to an existing group. The owner of the personal folder
    cannot have their access removed from the folder.

-   Using custom attributes or extensions with SailPoint IdentityIQ and the SCIM
    Connector is not currently supported.

*The following sections assumes that you have Sailpoint connected to Secret
Server SCIM and that the connectivity has been validated as working. Below we
cover the most common “Create” type use cases*

### SCIM - Creating New Users

For creating new “Local” users in Secret Server from Sailpoint, ensure that you
have a Provisioning policy with a form for creating new accounts. Below is a
screenshot of this area in Sailpoint.

   ![](images/df669481b40c0bc5d934c32ab7f67bbf.png)

The form itself has a few fields that are relevant to be completed for new users
provisioned through Sailpoint

   ![](images/1c6292d2ccb78163b54723e0a547ca10.png)

The password field aligns with a password policy rule. This rule should align
with your Secret Server’s local password policy so that you can ensure when
users are provisioned through Sailpoint, that they are compliant with the rules
enforced for new local users in Secret Server, and provision correctly.

   ![](images/922759d8cfc0d6222ac2016a5cb99d7c.png)

   ![](images/66bec42570668606b4d5a90e39dd63af.png)

Create a new identity in Sailpoint. This can be done under the **Manage
Identity** section and by clicking **Create Identity.**

   ![](images/6c353c51301ed80b7e63ac05036962db.png)

Approve the creation of the account. Under **Manage Access** \> **Manage
Accounts** section, locate the user you created then click **Manage**

   ![](images/353cea26bfaa36eacc36c7495b7e76cf.png)

Click the **Request Account** button

   ![](images/2dcc9b3ce0a6db7aad51fe67f53c5b6e.png)

Select **Thycotic PAM.**

   ![](images/3175b63d27af12a439d4eb98f8068850.png)

When you get to the **Submit** page it will indicate that more information is
needed and you need to complete a form.

Complete the form.

   ![](images/25b4e773d2718f64267eaa36c9625f92.png)

Click OK at the bottom. The account change submission should happen and can be
tracked under **My Work \> Access Requests.**

   ![](images/294633abf1d90c6ff4e9c7c22cf93002.png)

You can check Secret Server to verify that the account has been created under
**Admin \> Users.**

   ![](images/273b7f2a9b1da069418489b438898c2c.png)

If you run your Perform Identity Request Maintenance task, you should see the My
Work Access Request show up as complete

   ![](images/648df88f36ab7a1e19ca00d3327694a2.png)

When assigning a user to an AD group, simply provision the user to the AD group
within Sailpoint. The easiest way we have found to do this is under the **Manage
Access \> Manage User Access** tab. Filter based on the Active Directory
Application you have already added to Sailpoint.

   ![](images/24a39f1861a32112f157a512574824c7.png)

   ![](images/b0a80ae6ccc8a9f0676618313a5d62cf.png)

   ![](images/2f56c6bd6aa2d3a3660c9393bb030ce4.png)

Ensure that on the Secret Server side, that this group is set up for
Synchronization for the Domain you have added. On the next Secret Server AD
synchronization, this user will be added to Secret Server and will be
provisioned access to any folders where that AD group is aligned for access.

### SCIM – Assigning Users to Local Secret Server groups 

Go to the **Manage Access \> Manage User Access** tab and apply a filter to
filter based on the Thycotic PAM application. This should reveal any local
groups in Secret Server

   ![](images/026f3559c7b5b5fa5310a71ff61c5544.png)

   ![](images/37efe161c930761b83df76e13fabc409.png)

You can verify this user was added to the group in Secret Server

   ![](images/877e291f169b3ddd17dc6a5482dc3484.png)

### SCIM – Creating New Groups

One way to create local groups within Secret Server through Sailpoint is under
the **Applications \> Entitlement Catalog** section. You can click on **Add New
Entitlement**

   ![](images/1d4c20fe15f98de4b38fcbdf89ead438.png)

Then click on the Thycotic PAM Application. For Type, choose Group, and for
Display Value enter the display value of your group.

   ![](images/b02e96b844f5181ba0a8c74af496ea71.png)

   ![](images/76cafb1ca6f88db2467dc3d664763a22.png)

After you click save, you will have to approve the workflow. Then the group will
be created in Secret Server.

   ![](images/8c11bd5923e03ffdd807f8326a2eb35e.png)

As previous examples have shown, you can create a provisioning policy form
similarly to the Create Identity form we did earlier.

### SCIM – Assigning Users To Folders

When assigning users to folders, please ensure that the SCIM API account has the
correct access to the folder in which you want to add the user to. As mentioned
in the best practices, assign the minimum permissions needed for anticipated
access that is required to be provisioned through SCIM.

In this example I removed the Tester account from the management group in Secret
Server. I then assigned the user to the Data Management folder in Secret Server
through Sailpoint.

(Before)

   ![](images/fe002718a0f75184b060cdf07b9ce1cc.png)

   ![](images/4ad601bc7806ac83b13aacdfe2e8c424.png)

In Sailpoint, go to **Manage Access \> Privileged Account Management.** Locate
the Folder in question and click manage

   ![](images/e9b5e41989d24d479d2f7b7e96d08fb1.png)

Click the **Add Identities** button

   ![](images/5782e79b9cb82def273c85b03c80e4a1.png)

   ![](images/e0edf84c75a19877afbb76d11c4d4f68.png)

Align the View permission

   ![](images/50c852b3904f051ef3e6dce1f7f44f78.png)

After the task has ran, verify that the account has been added to the folder

   ![](images/0ac1741a19505093be2ec1b4d5ee5f97.png)


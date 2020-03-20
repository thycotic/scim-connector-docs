[title]: # (Limitations)
[tags]: # (minimum)
[priority]: # (105)
# SCIM Connector Limitations

There are limitations of the SCIM Connector application:

* It does not currently support 'PATCH' calls from the SCIM standard.
* It does not delete users. Secret Server does not delete users in order to maintain audit trails. As a result, when you delete a user with a SCIM call, it disables the user. The disabled user cannot be granted access to a container or group unless they are enabled again.
* It throws an error if instructed to delete and already deleted user. Disabling (deleting) already disabled users (by ID) causes the SCIM Connector application to report a 404 error in the logs.

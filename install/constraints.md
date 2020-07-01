[title]: # (Implementation Considerations)
[tags]: # (minimum)
[priority]: # (105)
# SCIM Connector Implementation Considerations

There are expected error responses when using the SCIM Connector:

* Secret Server does not delete users in order to maintain audit trails. As a result, when you delete a user with a SCIM call, it disables the user. The disabled user cannot be granted access to a container, privileged data or group unless they are enabled again.
* Secret Server throws an error if instructed to delete and already deleted user. Disabling (deleting) already disabled users (by ID) will result in the SCIM Connector reporting a 404 error in the logs.

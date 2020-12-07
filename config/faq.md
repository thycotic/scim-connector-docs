[title]: # (FAQ)
[tags]: # (faq)
[priority]: # (206)
# FAQ

## The administrator that set up the SCIM Connector has left the company. How can I access the SCIM Connector?

In Secret Server share the SCIM Connector secret with the new administrator and make them the “Owner” of the Secret. Once this is done, they will be able to log into the SCIM Connector with their Secret Server Credentials.

## What happens while adding a new user when a username is already in Secret Server?

First SCIM Connector checks for unique email address. If the email address does not exist in Secret Server and the attempt to add a user fails due to a username conflict, the user will be created in Secret Server using the email address for the username.

## The endpoint tab is not Active / I Can not click on the endpoint tab in the SCIM Connector UI.

1. SCIM Connector is disabled. Check the Configuration settings, correct any errors in the log and re-enable SCIM Connector. Then the endpoint tab should be available.

1. The Application Account has not been configured. Configure the application account and the tab should be available.

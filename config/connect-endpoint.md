[title]: # (Endpoint Connections)
[tags]: # (connecting,configuration)
[priority]: # (202)
# SCIM Endpoint Connections

The SCIM Connector application can connect to multiple SCIM endpoints at a time. Each SCIM endpoint has a defined set of required fields within the SCIM Connector but may also require additional steps from the third-party vendor endpoint.

Below are the basic steps for entering the values for the SCIM endpoint.

## Making a SCIM Endpoint Connection

1. In the SCIM Connector application, click the __+__ button in the top right of the page and select __Add Integration__.

1. Alternatively, users can select the __Settings__ menu on the left, and navigate to the __SCIM Endpoint__ tab at the top of the page.

<!-- add an overview of the configuration  (mini-toc) - add image -->

1. Once you add an endpoint, the __SCIM Endpoint__ configuration page appears:  

<!-- add an overview of the configuration  (mini-toc) - add image -->

   1. Enter the following:

      * __Name__ text box: The friendly name you want to give to the endpoint connection.
      * __Username__ text box: The user account that should be used to connect to the endpoint.
      * __Password__ text box: The password for the user account that is used to connect.
      * __Base URL__ text box: The URL for where the calling application resides, so a connection can be established.
      * __Authentication__ list box: There are two authentication methods that are currently supported by the Thycotic SCIM Connector. They are:
        * __Non-expiring token:__ This enables the Token field below, allowing e-token generation and storing the SCIM Connector applications.  If the non-expiring token is regenerated or deleted from the SCIM Connector, subsequent calls using the non-expiring token will fail, resulting in an unauthorized request response.
        * __OAuth2:__ This option disables the __Token__ field below and only allows for the OAuth2 standard to be used for authentication calls with the SCIM Connector application.
      * __Token__ view box: This option is enabled when the "Non-expiring token" is the authentication type. Clicking the first button to the immediate right generates the token and fills its value in the Token field. Clicking the second button to the right copies that token to the clipboard.

   1. Click __Verify__ to validate the entered information.
   1. Click __Save__.

>**Note**: In addition to making a connection to the SCIM Endpoint through the SCIM Connector application, users may need to make configuration adjustments within the target endpoint system. For a list of known endpoint side configurations, please see the [Configuring Third-Party Vendors](#ConfiguringThird-PartyVendors) section.

The SCIM Endpoints page lists all the current connections that are made to any SCIM endpoint. Users can modify the existing connection settings by clicking the __Edit__ button to the right-hand side of the specific connection.

<!-- - check the line where it indicates the "right-hand" -->

Users can run a connection test to any of the listed SCIM endpoints at any time by navigating to this page and clicking __Test__ to the right of the specific connection.

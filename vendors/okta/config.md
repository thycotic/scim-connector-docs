[title]: # (Configure Okta Endpoint)
[tags]: # (third-party)
[priority]: # (2)
# Configuring an Okta Endpoint to Work with the SCIM Connector

The steps in this topic are required to configure Okta for use as a SCIM EndPoint for the SS SCIM Connector application. They are in addition to making a SCIM Endpoint connection within the SCIM Connector application itself.

By default, there are two fields in OKTA that are marked as mandatory and used to identify users; these are the First Name and Last Name fields (please see the Okta Universal Directory link below for details).

However, the SS SCIM Connector application uses the primary email value to identify users instead, so if the SCIM connector uses the SCIM standard to request user values, it passes blank values for these two fields, resulting in data request or importation failure. To allow OKTA and the SCIM Connector to communicate successfully, you must change the status of these two fields (First Name and Last Name) from [mandatory to optional](https://support.okta.com/help/s/question/0D50Z00008G7VLL/can-we-make-firstname-and-lastname-as-optional-fields).

Once the fields are made optional, some additional changes are required in the code for the JSON body of the POST call (the yellow-highlighting shows the modified text):

Original JSON body for the POST call:

![JSON POST](images/post.png "JSON original POST call")

Modified JSON body for the POST call:

![JSON POST](images/post-2.png "JSON modified POST call")



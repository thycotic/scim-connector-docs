[title]: # (Okta Provisioning)
[tags]: # (okta)
[priority]: # (3)
# Okta Provisioning

## Connect your SCIM service with a Okta integration

1. Begin by signing up for an developer account using URL:
    `https://developer.okta.com/signup`

1. After the creating account we will receive the email, open the link to your developer account.

   ![](images/3a412a80772caa061c05769a610deb29.png)
1. Enter the __username__ and __password__.

   ![](images/c413660bfc2625afa398b59d10580a8c.png)
1. Navigate to the Admin Console in your Okta org by clicking __Admin__.

1. If you are in the Developer Console, click __Developer Console__ and then __Classic UI__ to switch over to the Admin Console in your Okta org.

   ![](images/efbc2cc31d503895ce81861d736125a8.emf)
1. Click __Applications__.

   ![](images/ca232b1b2e9d578f449f3fd973e954df.emf)
1. Click __Add Application__.

   ![](images/1be304a7f8a05ec0980c26f243d119a2.png)
1. Search for __SCIM 2.0__.

   >**Note:** Three different SCIM template applications, will be displayed each of the three authentication methods that you can use to connect to your SCIM implementation (Basic Auth, Header Auth, or OAuth Bearer Token).

   ![](images/150c00f3688d85a20b53603a4220a9bc.png)
1. Select __SCIM 2.0 Test App__ (Header Auth).
1. Click __Add__ on the template to use.

   ![](images/58f3ae5f2cd0ac43fc31e421e23f7521.png)
1. On the __General Settings__ page, give your integration a descriptive name and click __Done__.

   ![](images/0d9dd07033d50766cf70eeb8db5f1a6e.png)
1. On the __Sign-On Options__ page, verify SAML 2.0 is selected.

   ![](images/628ca552e18c72ef96cd316218187292.png)
1. Click the __Provisioning__ tab, and in the main panel, click __Configure API Integration__.

   ![](images/dc0e0bbef671d5840f5e22be567f86ec.png)
1. Select the __Enable API Integration__ check box.

   ![](images/29a7d491e4f2a6c8fff08d4d36a2a9a4.png)
1. Enter the base URL and Token from the Thycotic SCIM Connector HTTP Header. To authenticate using HTTP Header, provide a bearer token to access your SCIM implementation.  

   ![](images/36c9e5821fd9b553879fb988f004cffe.png)
1. Click __Test API Credentials__ to test whether the Okta integration can connect to your SCIM API.

   ![](images/ddd14ed2e31f71c5913b4ad73f4d1d5d.png)
1. Click __Save__ to complete the API integration.

## Configure your Okta integration

1. Login to __Okta__ using dev account.

1. Click on __application__ | __applications__.

   ![](images/740248741e680b84f3042f0fdc3fb7f6.emf)
1. Click on the __SCIM application__ created above.

   ![](images/4a96908b79e4c01e757a9dea60eba220.png)
1. Click On the __Provisioning__ tab of your Okta integration page, there are now three options listed in the __SETTINGS__ panel:

   * __To App__
   * __To Okta__
   * __API Integration__

1. Click __App__.

   ![](images/8dc9552818fd148d18b35443af906252.png)
1. Click __Edit__ to make changes to the following sections.

   ![](images/72fc46c075d3a5cc481d12f083bdd64a.png)
1. Navigate to __Directory__.
1. Click on __People__.

   ![](images/6748e4d7686a0baa9c12082c771f12dc.emf)
1. Click on __add Person__ and enter the details. 
1. Click on __Save__.

   ![](images/dd0ea852d6a5ea0c25ab5d2139e078e8.png)
1. Again go to __SCIM__ Application and click on __Assignments__.

   ![](images/d256477e3b0c371d2424b94ab2ff857a.png)
1. Click on __Assign__ and select __Assign to People__.

   ![](images/a03239740313f9be9c4f7f5fb51499ba.png)
1. Select the user which we want to sync to Secret Server and select __Assign__ and then click on __Done__.

   ![](images/6c5b7a9292e84562f11d98f122688e45.png)
1. Click on __Save and GoBack__.

   ![](images/cfca7332a1fb4027746dffa2ac4407a8.png)
1. User will be sync to Secret Server.
1. Login to __SecretServer | click on Admin | Users__.
1. Search for the user created in Okta in Secret Server

   ![](images/1cdc1fe686e8fd16a589130f85461627.png)
1. To import the user and groups from Secret Server click on the __Import tab__.

   ![](images/dff0ac12e9059d21b6859becbc8a6723.png)
1. Click on __Import Now__.

   ![](images/4207afb96462d28033cf1569c42707e6.png)
1. After completion of process users from Secret Server will be displayed.

   ![](images/b866c861fcc5758977d5bc47d8e39b08.png)
1. Click on __Directory | Groups__.

   ![](images/75fa135fdfd3b8ca07738afbf534e195.emf)
1. SecretServer Groups will be displayed.

   ![](images/9b93578067dfd0aaf5d03db16d711fb3.png)

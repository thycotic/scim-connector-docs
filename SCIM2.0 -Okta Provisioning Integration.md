**Okta Provisioning**

**Connect your SCIM service with a Okta integration**
-----------------------------------------------------

1.  Begin by signing up for an developer account using URL:
    <https://developer.okta.com/signup>

2.  After the creating account we will receive the email, open the link to your
    developer account.

    ![](media/3a412a80772caa061c05769a610deb29.png)

3.  Enter the username and password

    ![](media/c413660bfc2625afa398b59d10580a8c.png)

4.  Navigate to the Admin Console in your Okta org by clicking **Admin**.

5.  If you are in the Developer Console, click **Developer Console** and
    then **Classic UI** to switch over to the Admin Console in your Okta org.

    ![](media/efbc2cc31d503895ce81861d736125a8.emf)

6.  Click **Applications** \> **Applications**.

    ![](media/ca232b1b2e9d578f449f3fd973e954df.emf)

7.  Click **Add Application**.

    ![](media/1be304a7f8a05ec0980c26f243d119a2.png)

8.  Search for "SCIM 2.0". Three different SCIM template applications, will be
    displayed each of the three authentication methods that you can use to
    connect to your SCIM implementation (Basic Auth, Header Auth, or OAuth
    Bearer Token).

    ![](media/150c00f3688d85a20b53603a4220a9bc.png)

9.  Select SCIM 2.0 Test App (Header Auth) and then Click **Add** on the
    template to use.

    ![](media/58f3ae5f2cd0ac43fc31e421e23f7521.png)

10. On the **General Settings** page, give your integration a descriptive name
    and Click **Done**.

    ![](media/0d9dd07033d50766cf70eeb8db5f1a6e.png)

11. On the **Sign-On Options** page, verify SAML 2.0 is selected

    ![](media/628ca552e18c72ef96cd316218187292.png)

12. Click the **Provisioning** tab, and in the main panel, click **Configure API
    Integration**.

    ![](media/dc0e0bbef671d5840f5e22be567f86ec.png)

13. Select the **Enable API Integration** check box.

    ![](media/29a7d491e4f2a6c8fff08d4d36a2a9a4.png)

14. Enter the base URL and Token from the Thycotic SCIM Connector HTTP Header.
    To authenticate using HTTP Header, provide a bearer token to access your
    SCIM implementation.  
    

    ![](media/36c9e5821fd9b553879fb988f004cffe.png)

15. Click **Test API Credentials** to test whether the Okta integration can
    connect to your SCIM API.

    ![](media/ddd14ed2e31f71c5913b4ad73f4d1d5d.png)

16. Click **Save** to complete the API integration.

**Configure your Okta integration**
-----------------------------------

1.  Login to **Okta** using dev account.

2.  Click on **application** \> **applications**

    ![](media/740248741e680b84f3042f0fdc3fb7f6.emf)

3.  Click on the **SCIM application** created above

    ![](media/4a96908b79e4c01e757a9dea60eba220.png)

4.  Click On the **Provisioning** tab of your Okta integration page, there are
    now three options listed in the **SETTINGS** panel:

-   **To App**

-   **To Okta**

-   **API Integration**

1.  Click To App

    ![](media/8dc9552818fd148d18b35443af906252.png)

2.  Click **Edit** to make changes to the following sections.

    ![](media/72fc46c075d3a5cc481d12f083bdd64a.png)

3.  Goto **Directory** \> click on **People**

    ![](media/6748e4d7686a0baa9c12082c771f12dc.emf)

4.  Click on **add Person ,** Enter the details and click on **Save.**

    ![](media/dd0ea852d6a5ea0c25ab5d2139e078e8.png)

5.  Again go to **SCIM** Application , click on **Assignments**

    ![](media/d256477e3b0c371d2424b94ab2ff857a.png)

6.  Click on **Assign** and select **Assign to People**

    ![](media/a03239740313f9be9c4f7f5fb51499ba.png)

7.  Select the user which we want to sync to Secret Server and select **Assign**
    , then click on **Done**

    ![](media/6c5b7a9292e84562f11d98f122688e45.png)

8.  Click on **Save and GoBack**

    ![](media/cfca7332a1fb4027746dffa2ac4407a8.png)

9.  User will be sync to Secret Server

10. Login to SecretServer , click on Admin \> Users

11. Search for the user created in Okta in Secret Server

    ![](media/1cdc1fe686e8fd16a589130f85461627.png)

12. To import the user and groups from Secret Server click on Import tab

    ![](media/dff0ac12e9059d21b6859becbc8a6723.png)

13. Click on **Import Now**

    ![](media/4207afb96462d28033cf1569c42707e6.png)

14. After completion of process users from Secret Server will be displayed.

    ![](media/b866c861fcc5758977d5bc47d8e39b08.png)

15. Click on **Directory \> Groups**

    ![](media/75fa135fdfd3b8ca07738afbf534e195.emf)

16. SecretServer Groups will be displayed

    ![](media/9b93578067dfd0aaf5d03db16d711fb3.png)

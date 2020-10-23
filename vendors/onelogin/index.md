[title]: # (OneLogin)
[tags]: # (onelogin)
[priority]: # (1)
# OneLogin Provisioning

## Connect your SCIM service with a OneLogin integration

1. Begin by signing up for a developer account using URL:
`https://www.onelogin.com/developer-signup`

1. After creating the account, you will receive an email with a link to verify your developer account.

   ![Account](images/91258111743989fc74eecf2ad482b016.png)
1. Enter the __username__ and __password__.

   ![Username](images/4baa5cc17ca6e2c4eb9839a84e1f938f.png)
1. Click __Applications__.

   ![Application](images/50e9cbb05c92056706770e2527eaffd9.png)
1. Click on __Add App__.

   ![Add App](images/c841c564c58bee2425d6fa761715ba77.png)
1. Search for __SCIM__.

   ![SCIM](images/7e60b766f64cb21882b723bd88cf96bf.png)
1. Select SCIM Provisioner with SAML(SCIM v2 core) and enter __display name__ and click __Save__.

   ![Save](images/acc5524451b16215a44dcb20ad73a0be.png)
1. Create a new endpoint in “Thycotic SCIM Connector” for OneLOgin. To authenticate using SCIM Bearer Token, provide a bearer token to access your SCIM implementation.

   ![Endpoint](images/5d2d0ef0bb2efb20c58cfad8ea1868f5.png)
1. Click on __Configuration__, give your __SCIM Base URL__ and __SCIM Bearer Token__.
1. Click on __Enable API Connection__.

   ![Enable API Connection](images/b4bba756ad35e3f9cdfe6def6318e691.png)

## Configure your OneLogin integration

1. Click on __Provisioning__ and select enable __Provisioning__.

   ![Provisioning](images/4c8b8f2854aa93362aca1356d7d293f8.png)
1. Click the __Users__ tab, and click __New User__.

   ![User](images/576e00f711aa87443fddc7278be19744.png)
1. Enter the details of the user and click on the __Save User__ button.

   ![Save user](images/ec66f688e17ef34be287257aaa2b771c.png)
1. Click __Application__ then click on __+__ button to Add __Thycotic Secret Server__ application.

1. Click on __Save__.

   ![Save](images/f128323618676deb307ad1beab6441e7.png)
1. Click __Pending__.
1. Click __Approve__.

   ![Approve](images/d995f77255679e382f9f44653d31ac8f.png)
1. After clicking approve the user will be __Provisioned__.

   ![Provisioned](images/1187f182c1c5d87f0f47a8b36468502c.png)
1. Navigate to __Secret Server | Users__ and search for __robertt__. the user Robertt has been created in secret server.

   ![User](images/3a7080a3eada7d4a48c8949d5a5b1a36.png)
1. Click on “__User Info__” in OneLogin and update the username to __robertty__.
1. Click on __Save User__.

   ![Save user](images/a1ead62653aac383b309b6de85d7057a.png)
1. Now move to Application and click on __pending__.
1. Click on the __Approve__ button.

   ![Approve](images/fc9539589a4323956f8b622bab9b0400.png)
1. The User will be __modified__ and __Provisioned__.

   ![Modified](images/29e8cf093c8f848d705316b03c684c82.png)
1. Navigate back to __Secret server__ and you should see the user __displayName__ is updated with __robertty__ .

   ![Display name](images/132389d0b837fa90cd31a88ea7fbd879.png)
1. Click on __Application__ | __Applications__ and select __Thycotic Secret Server__ application.

   ![Thycotic Secret Server](images/fa6cbd6e4be4dbce3b8f0677fbfdaf4e.png)
1. Click on __Users__ and select Robert tail user.

   ![User](images/4341c412a8a13b93dfe7e29de6168244.png)
1. Select the group that has come from Secert Server for the user and click on __Add__.
1. Click __Save__.

   ![Save](images/1e755faffbbed9dd393769492099eb5a.png)
1. Click on __Pending__ for the user and approve it.

   ![Pending](images/f3cdedea77e16b8a1749fae2dd7f7ddb.png)
1. The user is __Provisioned__.

   ![Provisioned](images/8cc32eb00d40b00a49e531cf4b8c20d7.png)
1. Navigate back to __Secret Server__ and search for user “robertt” and click on the user. You should now see that the group is getting assigned to the user.

   ![Secret Server](images/f3aac044636f2954221bd4c64169c4d3.png)
1. Click on __Application__ | __Applications__ and select __Thycotic Secret Server__ application.

1. Click on __Provisioning__ Select “When users are deleted in OneLogin, or the user's app access is removed, perform the below action” to __Delete__.
1. Click __Save__.

   ![Save](images/79d0a280dcc42cc244d4e84245c43a9c.png)
1. Click on __Users__ Robert Tail.

   ![Users](images/6d5f96237fc2f54bd39c102b9324f365.png)
1. Click on the “__Delete__” button.

   ![Delete](images/534c2d7abfc7663a759147f9db84c706.png)
1. Navigate to __Users | Applications__.
1. Click on __Pending__ and approve it.

   ![Pending](images/b6ee20eb9b17883b1476fd11995d1dbd.png)
1. Navigate to __Secret Server| Users__ and search for the robertt user, you should see the robertt user is deleted

   ![Users](images/890716938853cfd00e266dc111831118.png)

[title]: # (Additional Configuration and settings storage)
[tags]: # (configuration)
[priority]: # (203)
# Additional Configuration and settings storage

There are three files local to the SCIM Connector that contain important
Settings and Configuration options: Web.config, Settings.enc, and
AppSettings.json.

The Web.config can be located in the root of the SCIM Connector Web Directory

While the Web.Config contains standard web application information it also
contains encrypted values that are required to decrypt the settings.enc. The
values to decrypt the settings.enc are also encrypted using IIS built in machine
RSA Protected Configuration Provider.

The encrypted keys will appear as CipherData in the web.config. It is critical
that these entries are not modified or deleted. Without these values, the
Settings.enc cannot be decrypted. If the web.config is deleted or the data in
the CipherData sections are changed or deleted, settings.enc will need to be
deleted and SCIM Connector Settings will need to be re-entered.

```

\<CipherData\>

   \<CipherValue\>

   oqXTmtY1NwaK38Wj7HGeIozZo9K3JgWkkmU3w7619DqovQYBY9UeSHTbkd8YGc7ZbcJ6doyCEUfkuTSVuFslCsL8+0gIwl0d1Ni/Nyha4q7DhADj8MBq/aUn5SfrJd+x7Z+TDJ2in/5klJ2EFmLeZBq7inC5aqIOeZ0ydAD0P+sKhrdeBrN2e6T4rXG3z++cnDcD0iUejPnc/yI+M5gy+QKkqlATlp7fpWGfgAczss45V0pwcko/9FRzmA==

   \</CipherValue\>

\</CipherData\>

\<CipherData\>

   \<CipherValue\>

       81fekLRnjFbNN6wEhfj6YbbiznDcIBSzkF46EKBuNDYz+tlgb7whnut/C4QxkVV87wDWBZhiIE1jM+2UhiikM8nznqsfxpVk01XCEyTj7F2U4/PNATlomTubsK6cVOtgY7dMchou8MYw6HQb+Y/WaA68rFGMagYteIgt5GgQGfuhRDdZjWzxaeCHeVljveNh24jyzy7wdlFQ2HGS/m+7lAL705cbDPIanRKFAaoXfiuFtXfAmS5vHV9Uqdwrs86JT

   \</CipherValue\>

\</CipherData\>

```

Additionally, the web.config will contain the machine key which is necessary for some decryption purposes. Do not modify or delete the machine key value from the web.config or SCIM Connector will fail to be able to function.

If either of the above settings in the web.config are modified or corrupted, the settings.enc will need to be deleted and SCIM Connector Settings will need to be reentered.

Settings.enc – located in the root of the SCIM Connector Web Directory. Do not modify or delete this file. For each Secret Server that is connected to the SCIM Connector required information is stored in the Settings.enc. This file is encrypted to ensure sensitive information is not viewable or accessible. If the
settings.enc is modified, decryption will fail, and the file will need to be deleted and SCIM Connector Settings will need to be re-entered.

**Encrypted data that includes:**

   * Secret Server URL

   * Secret Server Application Username

   * Secret Server Application Account Password

   * SCIM Connector Secret ID

   * SCIM Connector Secret Folder ID

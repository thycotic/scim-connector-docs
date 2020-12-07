[title]: # (Additional Configuration and settings storage)
[tags]: # (configuration)
[priority]: # (203)
# Additional Configuration and settings storage

There are three files local to the SCIM Connector that contain important
Settings and Configuration options: Web.config, Settings.enc, and
AppSettings.json.

**Web.config can be located in the root of the SCIM Connector Web Directory**

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

dJj511YhAArtIskEbGEK4UKycONTAPGTaKdQTuqEGUQpr5aygCqzO4dGKlkCMOKE+pw2IviCRifFiuF3U3BOzAdldMdQWGp6u65EmRPSXv8F7rA9yDvtCrAd775F2vKSEvRFgjIdyfc5/MXMULH/cU4JrHHbJd+LX6EvdcXRtvieZYFC/hiEjnGA3E2E3RJGUtW/wCO4gR3VuIukcbKb6P+V/oQeObXZxEEki3JgwY2Q9WEbW8LpL+SHso+AHW8bX5SU/bQX+vgaLrhNgnEeHCzqRuPU3Knv8FKDf0PbrK2KC13DPYbnrn2FIxL89bfw6PRLCru1wxNfyTEEIg8HxvCefOOmGF+TL0fd19i6rt1vanyYPXUBhpCGg8udvkxWGuHc6ogoHQeeFOF8g09Dwm2jx060i4IKSRGOTwtShY7V6fahioQ5QpEuhDXHLnYs9ekuZHz+8Vc0Az43L1Ce+WiTKWq0qdPQ4Mj6/COeA482/CvaFoCcnAWqFFQQjBT6CwEX/ziK0ILp1rrVzIadNc4TdQNOTw7Kl7+pdqJRokWCwkR1A0baQuC6ZFu45DqIZRg+lynk7BrG7J/FnIPn3A==

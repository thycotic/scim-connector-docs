[title]: # (Certificates)
[tags]: # (configuration)
[priority]: # (212)
# Self-Signed Certificates

* A self-signed certificate is generated and stored in the local computer certificate store. This certificate is used solely to encrypt and decrypt the configuration file.
* The default name for the certificate is the machine name with "Issued To" and "Issued By" also being the machine name
* If the certificate already exists a new certificate will not be created
* `IIS_USRS` must have read permissions on the certificate


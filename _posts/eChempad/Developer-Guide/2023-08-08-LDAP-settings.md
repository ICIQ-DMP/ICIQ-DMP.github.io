---
layout: default
title: LDAP settings
permalink: /eChempad/Developer-Guide/LDAP-settings/
parent: Developer Guide
grand_parent: eChempad
nav_order: 15
---

Adapting [this blog post](https://fawnoos.com/2021/02/13/cas63-bootiful-cas-client/).

To configure LDAP we need to configure a CAS server. Anf before configuring a CAS server we need to configure HTTPS for our app

### HTTPS config
###### Create new keystore with self-signed certificate
```bash
keytool -genkey -alias eChempad -keyalg RSA -validity 999 -keystore src/main/resources/security/keystore -ext san=dns:eChempad.iciq.es
Enter keystore password:  
Re-enter new password: 
What is your first and last name?
  [Unknown]:  eChempad
What is the name of your organizational unit?
  [Unknown]:  TCC     
What is the name of your organization?
  [Unknown]:  ICIQ
What is the name of your City or Locality?
  [Unknown]:  Tarragona
What is the name of your State or Province?
  [Unknown]:  Spain
What is the two-letter country code for this unit?
  [Unknown]:  ES
Is CN=eChempad, OU=TCC, O=ICIQ, L=Tarragona, ST=Spain, C=ES correct?
  [no]:  yes
```

###### Export certificate to a file 
```bash
# Export the certificate into a file
keytool -export -file src/main/resources/security/eChempad.crt -keystore src/main/resources/security/keystore -alias eChempad
```

###### Import certificate to the path keystore
```bash
# Import the certificate into the global keystore
sudo keytool -import -file src/main/resources/security/eChempad.crt -alias eChempad -keystore $JAVA_HOME/lib/security/cacerts
```

```
#Fri Sep 22 12:34:49 CEST 2023
cas.authn.ldap[0].bindCredential=password
cas.authn.ldap[0].order=0
cas.authn.ldap[0].useStartTls=false
cas.authn.ldap[0].baseDn=ou\=users
cas.authn.ldap[0].type=AUTHENTICATED
cas.authn.ldap[0].ldapUrl=ldaps\://ldap.iciq.es\:389/
cas.authn.ldap[0].minPoolSize=3
cas.authn.ldap[0].subtreeSearch=true
cas.authn.ldap[0].bindDn=cn\=admin
cas.authn.ldap[0].searchFilter=(mail\={user})
cas.authn.ldap[0].name=Custom LDAP setup
cas.authn.ldap[0].maxPoolSize=20
cas.authn.ldap[0].principalAttributeId=mail
cas.authn.ldap[0].enhanceWithEntryResolver=true
cas.authn.ldap[0].useSsl=true
cas.authn.ldap[0].principalAttributeList=mail,cn,givenName,sn
```

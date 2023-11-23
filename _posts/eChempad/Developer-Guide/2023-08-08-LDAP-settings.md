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
keytool -genkey -alias eChempad -keyalg RSA -validity 999 -keystore src/main/resources/security/keystore -ext san=dns:echempad.iciq.es
Enter keystore password:  
Re-enter new password: 
What is your first and last name?
  [Unknown]:  echempad
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

###### Add CAS certificate into eChempad app
```bash
wget https://raw.githubusercontent.com/escline/InstallCert/master/InstallCert.java
java --source 11 InstallCert.java echempad-cas.iciq.es:8443 changeit  # Press enter
cp jssecacerts src/main/resources/security
rm jssecacerts
keytool -exportcert -alias echempad-cas.iciq.es-1 -keystore src/main/resources/security/jssecacerts -storepass changeit -file src/main/resources/security/echempad-cas.iciq.es.crt
sudo keytool -importcert -alias echempad-cas.iciq.es-1 -keystore ${JAVA_HOME}/lib/security/cacerts -storepass changeit -file src/main/resources/security/echempad-cas.iciq.es.crt  ## type yes and press enter
```

### Test LDAP server
To test the LDAP server with queries and to see if it does answer us we need to install the `ldapsearch` binary package. In ubuntu we can do so by using the package manager like this:
```shell
sudo apt install -y ldap-utils
```

### TL;DR HTTPS certificates
1- Get as many certificates you can from your application. Get them from the web, autogenerate them, whatever. 
2- Put them inside the JVM that is going to run your apps. If you have more, then puto all certificates in each JVM
3- If you have the typical information of the connection is not secure then probably you have done it wrong. 


# LDAP config and testing
There is the utility `ldapsearch` that you can use to easily send queries to a LDAP server. 

Here I have written a prompt that makes a search to the LDAP query using my user `ldapechempad`. Ommitted the password for security (careful, the password will go to bash history):

```shell
ldapsearch -v -x -D "CN=ldapechempad,CN=users,dc=ICIQ,dc=ES" -w "LDAP_passwd" -b "CN=users,dc=ICIQ,dc=ES" -H ldap://iciqdc01.iciq.es:389 -s sub "(userPrincipalName=amarine@iciq.es)"
```

Notice that userPrincipalName is a property that users have, where they have written their full email direction. We will use this filter to select a single user.

Also notice that it seems that LDAP does not make any distinction between uppercase and lowercase. 

Here the same command using `ldapsearch` but getting the password from an external file, so it is not in the historial:
```shell
ldapsearch -v -x -D "CN=ldapechempad,CN=users,dc=ICIQ,dc=ES" -W -b "CN=users,dc=ICIQ,dc=ES" -H ldap://iciqdc01.iciq.es:389 -s sub "(userPrincipalName=amarine@iciq.es)" < secret.txt
```

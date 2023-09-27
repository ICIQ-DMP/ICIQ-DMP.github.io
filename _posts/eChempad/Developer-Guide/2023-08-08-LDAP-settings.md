---
layout: default
title: LDAP settings
permalink: /eChempad/Developer-Guide/LDAP-settings/
parent: Developer Guide
grand_parent: eChempad
nav_order: 15
---

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

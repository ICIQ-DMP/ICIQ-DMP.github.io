---
layout: default
title:  Signals metadata
permalink: /eChempad/developer-guide/Signals-metadata/
categories: developer information signals
tags: developer guide
nav_order: 4
parent: Developer Guide
---

# Metadata in Signals
In this document we show the structure and format of the different JSONs obtained 
from scratching the API of the Signals notebook. 

## Journal 

#### Signals container metadata example
```json
{
  "links": {
    "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/entities?includeTypes=container&include=children, owner&page[offset]=7&page[limit]=1",
    "first": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/entities?includeTypes=container&include=children, owner&page[offset]=0&page[limit]=1",
    "prev": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/entities?includeTypes=container&include=children, owner&page[offset]=6&page[limit]=1",
    "next": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/entities?includeTypes=container&include=children, owner&page[offset]=8&page[limit]=1"
  },
  "data": [
    {
      "type": "Entity",
      "id": "container:ddac1092-5f55-4952-a5f1-7f2c553fef46",
      "links": {
        "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/entities/container:ddac1092-5f55-4952-a5f1-7f2c553fef46"
      },
      "attributes": {
        "id": "container:ddac1092-5f55-4952-a5f1-7f2c553fef46",
        "eid": "container:ddac1092-5f55-4952-a5f1-7f2c553fef46",
        "name": "Linear Acenes",
        "description": "",
        "createdAt": "2020-05-27T19:52:54.871Z",
        "editedAt": "2020-05-27T19:52:54.871Z",
        "type": "container",
        "digest": "43254827",
        "fields": {
          "Confidential": {
            "value": "No"
          },
          "Department": {
            "value": "Echavarren"
          },
          "Description": {
            "value": ""
          },
          "Name": {
            "value": "Linear Acenes"
          }
        }
      },
      "relationships": {
        "createdBy": {
          "links": {
            "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/users/183"
          },
          "data": {
            "type": "user",
            "id": "183"
          }
        },
        "editedBy": {
          "links": {
            "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/users/183"
          },
          "data": {
            "type": "user",
            "id": "183"
          }
        },
        "owner": {
          "links": {
            "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/users/183"
          },
          "data": {
            "type": "user",
            "id": "183"
          }
        },
        "children": {
          "links": {
            "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/entities/container:ddac1092-5f55-4952-a5f1-7f2c553fef46/children"
          }
        }
      }
    }
  ],
  "included": [
    {
      "type": "user",
      "id": "183",
      "links": {
        "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/users/183"
      },
      "attributes": {
        "userId": "183",
        "userName": "ostoica@iciq.es",
        "alias": "ostoica",
        "email": "ostoica@iciq.es",
        "firstName": "Otilia",
        "lastName": "Stoica"
      },
      "relationships": {
        "systemGroups": {
          "links": {
            "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/users/183/systemGroups"
          }
        }
      }
    }
  ]
}
```


#### Signals container metadata action 

```json
{
  "links": {
    "self": "IGNORED",
    "first": "IGNORED",
    "prev": "IGNORED",
    "next": "IGNORED"
  },
  "data": [
    {
      "type": "PARSED FOR CHECKS, it will be always an entity",
      "id": "KEPT structural metadata, for reference to the corresponding container in Signals",
      "links": {
        "self": "IGNORED (can be deduced using the id value)"
      },
      "attributes": {
        "id": "IGNORED, already present in the field data[0].id",
        "eid": "IGNORED, already present in the field data[0].id",
        "name": "KEPT, descriptive metadata",
        "description": "KEPT, descriptive metadata",
        "createdAt": "KEPT, descriptive metadata",
        "editedAt": "KEPT, descriptive metadata, is an extra field for signals or is the same field as in echempad?",
        "type": "PARSED FOR CHECKS, it will be always an entity",
        "digest": "IGNORED, we do not know units, algorithm of digest nor actual structure of the digested file(s). If we want it we will implement our own.",
        "fields": {
          "Confidential": {
            "value": "IGNORED BY NOW, it can be parsed to enforce extra privatization of data"
          },
          "Department": {
            "value": "KEPT, descriptive metadata"
          },
          "Description": {
            "value": "IGNORED, already present in the field data[0].attributes.description"
          },
          "Name": {
            "value": "IGNORED, already present in the field data[0].attributes.description"
          }
        }
      },
      "relationships": {
        "createdBy": {
          "links": {
            "self": "IGNORED, we will only be keeping the owner"
          },
          "data": {
            "type": "IGNORED, we will only be keeping the owner",
            "id": "IGNORED, we will only be keeping the owner"
          }
        },
        "editedBy": {
          "links": {
            "self": "IGNORED, we will only be keeping the owner"
          },
          "data": {
            "type": "IGNORED, we will only be keeping the owner",
            "id": "IGNORED, we will only be keeping the owner"
          }
        },
        "owner": {
          "links": {
            "self": "IGNORED, data present in the included section of the JSON"
          },
          "data": {
            "type": "IGNORED, data present in the included section of the JSON",
            "id": "IGNORED, data present in the included section of the JSON"
          }
        },
        "children": {
          "links": {
            "self": "PARSED FOR CHECKS, recursively parsed from the base Journal inorder to scratch all data from the container. "
          }
        }
      }
    }
  ],
  "included": [
    {
      "type": "PARSED FOR CHECKS, it should be always equal to user",
      "id": "IGNORED BY NOW, we may keep it in the future to keep a back reference to the id of the user in Signals",
      "links": {
        "self": "IGNORED, deducible from the id of the included section"
      },
      "attributes": {
        "userId": "IGNORED, deducible from the id of the included section",
        "userName": "IGNORED, not needed",
        "alias": "IGNORED",
        "email": "PARSED FOR CHECKS, it should be equal to the email of the user logged in eChempad if desired, in order to filter the scratching of resources to the ones that are owned",
        "firstName": "Otilia",
        "lastName": "Stoica"
      },
      "relationships": {
        "systemGroups": {
          "links": {
            "self": "https://iciq.signalsnotebook.perkinelmercloud.eu/api/rest/v1.0/users/183/systemGroups"
          }
        }
      }
    }
  ]
}
```
## Introduction ##

This write-up gives an overview of the architecture of the Esprit, which is a Social Networking Site (SNS) vis-à-vis php Shindig OpenSocial Reference implementation.


## Details ##

## Architecture Diagram ##






http://esprit.googlecode.com/svn/trunk/html/images/Esprit_Shindig_Rest_Server_Integration.GIF

Fig 1.1 Esprit and Shindig Rest Server integration

## Esprit with Shindig ##

To use Shindig as an opensocial container, esprit need to pass security token as a request parameter. For now, we have used the token generation model of Shindig, which can be modified further depending upon any SNS requirement.
Following files have been use from Shindig to form the security token:
  1. Crypto.php
  1. BlobCrypter.php
  1. SecurityToken.php
  1. BasicBlobCrypter.php
  1. BasicSecurityToken.php

Shindig container in ESPRIT can be implemented by using OpenSocial Restful component.

## OpenSocial Restful Component ##

> Esprit OpenSocial Restful component includes the following classes:

  1. espritPeopleService- espritPeopleService class implements all the methods to handle each kind of request (requesting, updating…) related to person/user’s personal information. espritPeopleService implement the Shindig’s PeopleService class which specifies all the possible methods and their prototypes which a container must follow.
  1. espritActivitiesService- espritActivitiesService class implements all the methods to handle each kind of request (requesting, updating…) related to person/user’s activities. espritActivitiesService implements the Shindig’s ActivitiesService class which specifies the all the possible methods and their prototypes which a container must follow.
  1. espritDataService- espritData class implements all the methods to handle each kind of request (requesting, updating…) related to person/user’s application related data. espritDataService implements the Shindig’s DataService class which specifies the all the possible methods and their prototypes which a container must follow.
  1. espritDBFetcher- espritDBFetcher is simply a Data Access Layer talking to ESPRIT database. All the services (espritPeopleService, espritDataService and espritActivitiesService) use this data access layer for creating, fetching, updating and deleting information into ESPRIT database which are coming from OpenSocial gadgets.
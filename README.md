# phpldapadmin autofs templates

phpldapadmin templates required for autofs configuration for openLdap Server.

Phpldapamdin provides a very nice web GUI to look into the directory entries for openLdap server. Admin can create and modify directory entries of the OpenLDAP server.

Phpldapamdin package does not have templates for autofs schemas, so user cannot create directory entries without adding new templates.

## What can it do?

It provides autofs template files for phpldapamdin.

## What it cannot do?

It cannot add schema to the OpenLDAP Server. You have to separately add schema to the OpenLDAP server.

## Download

```
git clone git://github.com/prasantjalan/phpldapadmin-autofs-templates
```

## Usage

* Add autofs.schema to the OpenLDAP Server
* Copy autofs templates (automount.xml & automountMap.xml) to the phpldapadmin templates directory (/etc/phpldapadmin/templates/creation/)
* It is recommended to restart the phpldapadmin machine.
* Try to add new entries, you will see options: "Generic: AutomountMap Unit" & "automount"

## LDAP Client side autofs setup

This step is not required for phpldapadmiin. It is provided only for ready reference.

Apart from other configurations in the LDAP Client, please add the following lines to the autofs configuration file : /etc/default/autofs <br/>
```
MAP_OBJECT_CLASS="automountMap"
ENTRY_OBJECT_CLASS="automount"
MAP_ATTRIBUTE="ou"
ENTRY_ATTRIBUTE="cn"
VALUE_ATTRIBUTE="automountInformation"
```

**Disclaimer** : The above was tested on Ubuntu 16.04 with the autofs schema in this repo.

# Custom role permissions
This repository contains a script and YAML files to create or update custom roles to use with Actifio GO or Google Cloud Backup and DR.

## Actifio GO

To add these roles, in your Google Console Cloud shell, run these three commands:

```
curl -o installActifioRoles.sh https://raw.githubusercontent.com/Actifio/rolepermissions/main/installActifioRoles.sh
chmod +x installActifioRoles.sh
./installActifioRoles.sh
```
Once the commands have run, close your Cloud Shell and refresh your browser window.

### New custom roles for Actifio GO

After running the script detailed below, you will have the  custom roles as follows.  Assign these to the relevant Service Accounts as required.

* **Actifio GO Full**: Use this for when you want to use a single Service Account for Actifio GO.  It has all the permissions of the other three roles.
* **Actifio GO OnVault**: Use this for adding a Google Cloud Storage bucket to Actifio GO
* **Actifio GO System Recovery**: Use this when adding a Credential to either create, expire, mount and delete GCP Instance snapshots and also System Recovery jobs.
* **Actifio GO Compute Engine VM Instance Snapshots**: Use this when adding a Credential to either create and use and delete GCP Instance snapshots.  It cannot be used for System Recovery jobs.  

**If you don't see the new roles, refresh your browser window.**

## Google Cloud Backup and DR

To add these roles, in your Google Console Cloud shell, run these three commands:

```
curl -o installGoogleCloudBDRRoles.sh https://raw.githubusercontent.com/Actifio/rolepermissions/main/installGoogleCloudBDRRoles.sh
chmod +x installGoogleCloudBDRRoles.sh
./installGoogleCloudBDRRoles.sh
```
Once the commands have run, close your Cloud Shell and refresh your browser window.

### New custom roles for Google Cloud Backup and DR

After running the script detailed below, you will have the  custom roles as follows.  Assign these to the relevant Service Accounts as required.

* **Backup and DR OnVault**: Use this for adding a Google Cloud Storage bucket to Google Cloud Backup and DR
* **Backup and DR Compute Engine Instance Backups**: Use this when adding a Credential to either create and use and delete GCP Instance snapshots. 

**If you don't see the new roles, refresh your browser window.**

## Deleting Custom Roles

If you delete a custom role then it does not automatically disappear and the Role Name cannot be reused for 30 days.   This means if you delete the role and then run the script, the install will fail because the role exists, but cannot be updated.   At this point either find the role in the IAM panel and un-delete it, or wait till the 30 day period is over.  More details can be found her:

https://cloud.google.com/iam/docs/creating-custom-roles#deleting-custom-role

## Maximum number of custom roles

There is a limit of 300 custom roles per Organization and/or Project.

## Contributing

Have a patch that will benefit this project? Awesome! Follow these steps to have
it accepted.

1.  Please sign our [Contributor License Agreement](CONTRIB.md).
1.  Fork this Git repository and make your changes.
1.  Create a Pull Request.
1.  Incorporate review feedback to your changes.
1.  Accepted!

## License

All files in this repository are under the
[Apache License, Version 2.0](LICENSE) unless noted otherwise.

## Oracle Database 12c Dockerfile
This directory must contain the Dockerfile for Oracle Database 12c along with the installer archives for the database software, OPatch, and any patches that must be applied.

Review the list of files to be downloaded and make them available in this location for the Dockerfile to create the image sucessfully.

### Required Files for the Database Image
The following files must be downloaded and made available in this directory. The links to download the files are also provided below. Make sure that you download the software for the Linux x86-64 platform.

- [linuxamd64_12102_database_1of2.zip][oradbdisk1]
- [linuxamd64_12102_database_2of2.zip][oradbdisk2]
- [p6880880_121010_Linux-x86-64.zip][opatch]
- [p21948354_121020_Linux-x86-64.zip][p21948354]
- [p22139226_121020_Linux-x86-64.zip][p22139226]

There is no need to extract the archives as the scripts will take care of that. Generally a combo patch is available that contains one or more patches. We do not use the combo patch as it adds more complexity.

[oradbdisk1]: http://download.oracle.com/otn/linux/oracle12c/121020/linuxamd64_12102_database_1of2.zip "Oracle Database 12c Disk 1"
[oradbdisk2]: http://download.oracle.com/otn/linux/oracle12c/121020/linuxamd64_12102_database_2of2.zip "Oracle Database 12c Disk 2"
[opatch]: https://support.oracle.com/epmos/faces/PatchResultsNDetails?patchId=6880880 "Latest OPatch"
[p21948354]: https://support.oracle.com/epmos/faces/PatchResultsNDetails?patchId=21948354 "Oracle Database 12c Patch 21948354"
[p22139226]: https://support.oracle.com/epmos/faces/PatchResultsNDetails?patchId=22139226 "Oracle Database 12c Patch 22139226"

## Oracle WebCenter Content 12c Dockerfile
This directory must contain the Dockerfile for Oracle WebCenter Content 12c along with the installer archives for the software, OPatch, and any patches that must be applied.

Review the list of files to be downloaded and make them available in this location for the Dockerfile to create the image sucessfully.

### Required Files for the WebCenter Content Image
The following files must be downloaded and made available in this directory. The links to download the files are also provided below. Make sure that you download the software for the Generic or Linux x86-64 platform.

- [jdk-8u74-linux-x64.tar.gz][jdk]
- [fmw_12.2.1.0.0_infrastructure_Disk1_1of1.zip][weblogic]
- [fmw_12.2.1.0.0_wccontent_Disk1_1of1.zip][wccontent]
- [p22331568_122100_Generic.zip][p22331568]
- [p22541322_122100_Generic.zip][p22541322]

There is no need to extract the archives as the scripts will take care of that.

[jdk]: http://download.oracle.com/otn-pub/java/jdk/8u74-b02/jdk-8u74-linux-x64.tar.gz "Oracle Java SE Development Kit 8"
[weblogic]: http://download.oracle.com/otn/nt/middleware/12c/1221/fmw_12.2.1.0.0_infrastructure_Disk1_1of1.zip "Oracle WebLogic Server 12c"
[wccontent]: http://download.oracle.com/otn/nt/middleware/12c/1221/fmw_12.2.1.0.0_wccontent_Disk1_1of1.zip "Oracle WebCenter Content 12c"
[p22331568]: https://support.oracle.com/epmos/faces/PatchDetail?patchId=22331568 "Oracle WebLogic Server 12c Patch 22331568"
[p22541322]: https://support.oracle.com/epmos/faces/PatchDetail?patchId=22541322 "Oracle WebLogic Server 12c Patch 22541322"

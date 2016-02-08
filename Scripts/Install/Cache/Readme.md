Cache Installation


Place the installer under the folder: Scripts/Install/Cache/installer/

The following files require adjustment when there is a new version of Cache to use:

install.sh
parameters.isc

Both files define the version within them that corresponds to files and file paths

install.sh
----------
Lines 49-50 of the 'install.sh' script are set as follows:
```
tempdir=/tmp/cachekit2015.2.2.805
```
parameters.isc
--------------
line 2: 
```
legacy_dist.source_dir: /tmp/cachekit2015.2.2.805/package/legacy_dist/../..
```
line 24:
```
server_location.ccontrol: /tmp/cachekit2015.2.2.805/package/legacy_dist/../../dist/Cache/bin/lnxrh5x64/shared/ccontrol
```
line 38:
```
installer.manifest_parameters: SourceDir=/tmp/cachekit2015.2.2.805/package/legacy_dist/../..,ISCUpgrade=0,
```

-------------
Instance Name
-------------
The default has been changed from OSEHRA to CACHEINV

This is set from the autoInstall.sh script under the Scripts/Install/RHEL/ folder.

lines 112-114:
```
if [[ -z $instance ]]; then
    instance=cacheinv
fi
```
-----------
Credentials
-----------
The parameters.isc file also defines the credentials for Cache

username: cacheusr
username: cacheusrprod
password: cacheprod!


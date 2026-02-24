# IBM Z® Open Debug Change Log


## 5.6.3
- Defect and security fixes.

## 5.0.0
- Added support for token authentication and Multi-Factor Authentication.

## 4.0.0
- IBM Z Open Debug v4 uses Zowe connection profiles to define connections to z/OS machines, replacing the connection details that were previously defined in the VS Code Settings. Existing connection details defined in the VS Code Settings can be automatically migrated to a new Zowe team configuration, or added to an existing Zowe team configuration.

- IBM Z Open Debug v4 uses a different internal format for storing debug profiles. Debug profiles in older formats can be automatically migrated.

- The separate *IBM Z Open Debug Profiles view* extension has been deprecated. All functionality related to debug profiles is now contained in the *IBM Z Open Debug* extension, and the *IBM Z Open Debug Profiles view* extension can be automatically uninstalled.

- A prompt will be displayed for each migration step. If desired, old artifacts may be retained after migration to allow continued backwards compatibility with older versions of IBM Z Open Debug.


## 3.0.0

- Added support for using 'Microsoft Visual Studio Code - Open Source' as the default browser-based editor/IDE in IBM Wazi for Dev Spaces. Support for Eclipse Theia has been deprecated as an editor/IDE choice in Red Hat OpenShift Dev Spaces and will be removed in a future release.
- Bugfixes

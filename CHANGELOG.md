# IBM Z® Open Debug Change Log

## 5.6.8

- After logging in to a connection in the **z/OS Debugger Profiles** view, Z Open Debug will now automatically connect to new parked debug sessions or code coverage sessions as they become available on the **Remote Debug Service**, replacing the requirement to manually trigger debug launches. The connection profile entry in the **z/OS Debugger Profiles** view shows the listening status for debug events and code coverage events separately.
- A new `zopendebug.autoAttachToParkedSessions` setting (enabled by default) controls whether parked debug sessions are attached to automatically. When disabled, a prompt is shown with the option to list available parked sessions, or they can be listed manually by running a launch configuration of type `attach`. Selecting a session from the list will attach to it.
- The `DETAIL` log level for the `zopendebug.logger.logLevel` setting has been renamed to `DEBUG`. The default log level has changed from `DETAIL` to `INFO`.
- IMS Isolation profiles can now be created in the **z/OS Debugger Profiles** view to isolate recording or debug sessions from other users by launching the z/OS Debugger in a private IMS region.

## 5.6.7
- Defect and security fixes.

## 5.6.6
- You can now specify Code Coverage Service connection details on the Z Open Debug Zowe connection profile using the `ccsPort` and `ccsSecured` attributes.
- Defect and security fixes.

## 5.6.5
- Defect and security fixes.

## 5.6.4
- Defect and security fixes.

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

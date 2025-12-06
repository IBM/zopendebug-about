# IBM Z® Open Debug

**IBM Z Open Debug is an extension for Visual Studio Code that provides interactive debugging support for debugging z/OS COBOL, PL/I and High Level Assembler applications in VS Code, in conjunction with IBM z/OS Debugger.**


> Go here for the full [Documentation](https://www.ibm.com/docs/en/developer-for-zos/latest?topic=code-debugging-applications) online. 

Simplify your installation experience by using newly bundled extension packs that contain Z Open Debug as well as other extensions available for [IDzEE](https://marketplace.visualstudio.com/items?itemName=IBM.developer-for-zos-on-vscode-extension-pack) and [ADFz](https://marketplace.visualstudio.com/items?itemName=IBM.application-delivery-foundation-for-zos-vscode-extension-pack) customers.


## Table of contents

- [Prerequisites](#prerequisites)
- [Migrating to IBM Z Open Debug v4 from earlier versions](#migrating-to-ibm-z-open-debug-v4-from-earlier-versions)
- [Configuring host connection](#configuring-host-connection)
- [Debug profiles](#debug-profiles)
- [Launching and debugging applications](#launching-and-debugging-applications)



## Prerequisites

Review the [IBM Z Open Debug License Agreement](https://github.com/IBM/zopendebug-about/raw/main/product-licenses/LICENSE.txt), terms and conditions for [separately licensed code](https://github.com/IBM/zopendebug-about/raw/main/product-licenses/NON_IBM_LICENSE.txt), and [Third Party Notices](https://github.com/IBM/zopendebug-about/raw/main/product-licenses/NOTICES.txt) before downloading.

- Client
  - [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) Visual Studio Code extension version 3.0.0 or later
  - [Visual Studio Code](https://code.visualstudio.com/download) version 1.48.2 or later
- Host
  - IBM z/OS Debugger [Remote Debug Service](https://www.ibm.com/docs/en/debug-for-zos/latest?topic=users-adding-support-remote-debug-service): for interactively debugging compiled applications running on z/OS
  - IBM z/OS Debugger [Debug Profile Service](https://www.ibm.com/docs/en/debug-for-zos/latest?topic=users-adding-support-debug-profile-service-apis): for creating debug profiles which can be used to trigger IBM z/OS Debugger in Batch, TSO, CICS and IMS environments
  - A valid host registration for [IBM Developer for z/OS Enterprise Edition (IDzEE)](https://www.ibm.com/products/developer-for-zos), [IBM Developer for z/OS Select](https://www.ibm.com/support/pages/ibm-developer-zos-select100) or [IBM Application Delivery Foundation for z/OS (ADFz)](https://www.ibm.com/products/app-delivery-foundation-for-zos) 



## Migrating to IBM Z Open Debug v4 from earlier versions

Starting with v4, IBM Z Open Debug uses Zowe connection profiles to define connections to z/OS machines, replacing the connection details that were previously defined in the VS Code Settings. Existing connection details defined in the VS Code Settings can be automatically migrated to a new Zowe team configuration, or added to an existing Zowe team configuration.

IBM Z Open Debug v4 uses a different internal format for storing debug profiles. Debug profiles in older formats can be automatically migrated.

The separate *IBM Z Open Debug Profiles view* extension has been deprecated. All functionality related to debug profiles is now contained in the *IBM Z Open Debug* extension, and the *IBM Z Open Debug Profiles view* extension can be automatically uninstalled.

A prompt will be displayed for each migration step. If desired, old artifacts may be retained after migration to allow continued backwards compatibility with older versions of IBM Z Open Debug.


## Configuring host connection

IBM Z Open Debug defines connections to remote z/OS hosts using [Zowe connection profiles](https://docs.zowe.org/stable/user-guide/ze-profiles/). A minimal Zowe team configuration file for Z Open Debug might look like:
```json
{
    "$schema": "./zowe.schema.json",
    "profiles": {
        "zOpenDebug": {
            "type": "zOpenDebug",
            "properties": {
                "host": "yourZhost.yourCompany.com",
                "dpsPort": 8143,
                "dpsContextRoot": "api/v1",
                "dpsSecured": true,
                "rdsPort": 8002,
                "rdsSecured": true,
            },
            "secure": [
                "user",
                "password"
            ]
        }
    },
    "defaults": {
        "zOpenDebug": "zOpenDebug",
    },
    "autoStore": true
}
```


## Debug profiles
IBM Z Open Debug provides a user interface in Visual Studio Code for creating and managing debug profiles, which can be used to dynamically trigger IBM z/OS Debugger on z/OS applications. Debug profiles can be created and managed through the *z/OS Debugger Profiles* view (*View* > *Open View...* > *z/OS Debugger Profiles*)



## Launching and debugging applications

IBM Z Open Debug provides several `launch.json` configuration types for working with z/OS Debugger sessions on a remote z/OS host. Launch configurations can be created and triggered through the *Run and Debug* view in order to:

* Launch a z/OS application via a client-side command line, and then automatically connect to it once it is parked on the z/OS host. Use a `launch` config that specifies an `applicationLaunch: commandLine` attribute.
```json
{
    "type": "zOpenDebug",
    "request": "launch",
    "name": "Launch and debug application",
    "connection": {
        "type": "zowe",
        "name": "myZoweConnection",
    },
    "applicationLaunch": {
        "commandLine": "zowe rse submit data-set \"MYUSER.SAMPLE.JCL(MYDBG)\""
    }
}
```
* List available parked z/OS Debugger debug sessions on a z/OS host (and optionally click to connect to one of them). Use an `attach` config.
```json
{
    "type": "zOpenDebug",
    "request": "attach",
    "name": "List and click to connect to available parked debug sessions",
    "connection": {
        "type": "zowe",
        "name": "myZoweConnection",
    }
}
```
* Connect to an available parked z/OS Debugger debug session on a z/OS host. Use a `launch` config.
```json
{
    "type": "zOpenDebug",
    "request": "launch",
    "name": "Connect to a parked debug session",
    "connection": {
        "type": "zowe",
        "name": "myZoweConnection",
    }
}
```


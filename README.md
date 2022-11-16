# IBM Z® Open Debug

**IBM Z Open Debug is a set of extensions for Visual Studio Code that provides interactive debugging support for debugging z/OS COBOL, PL/I and HLASM applications, when used in conjunction with IBM z/OS Debugger.**


## Table of contents

- [Prerequisites](#prerequisites)
- [Configuring host connection](#configuring-host-connection)
- [License](#license)



## Prerequisites

Review the IBM Z Open Debug License Agreement, and terms and conditions for separately licensed code.


## Configuring host connection

IBM Z Open Debug Profiles view extension utilizes VS Code Settings properties, which can be added to VS Code workspace or user settings, to configure the connection to a remote z/OS host. You can configure these settings by editing the `settings.json` file for your workspace or in the VS Code Settings page under `Extensions > IBM Z Open Debug`.


IBM Z Open Debug provides two `launch.json` configuration types for working with z/OS Debugger sessions on a remote z/OS host.

* Attach, to list parked z/OS Debugger debug sessions on a z/OS host.
* Launch, to connect to a parked z/OS Debugger debug session on a z/OS host.


## LICENSE

See LICENSE

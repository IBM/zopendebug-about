# IBM Z® Open Debug

**IBM Z Open Debug provides interactive debugging support in Visual Studio Code for z/OS applications written in COBOL, PL/I, or HLASM, when used in conjunction with IBM z/OS Debugger.**


## Table of contents

- [Prerequisites](#prerequisites)
- [Launching and debugging applications](#launching-and-debugging-applications)
- [License](#license)


## Prerequisites

- IBM Z Open Debug requires the Remote Debug Service of the IBM z/OS Debugger to be configured and running on the z/OS host.
- Review the IBM Z Open Debug License Agreement, and terms and conditions for separately licensed code.


## Launching and debugging applications

IBM Z Open Debug provides several `launch.json` configuration types for working with z/OS Debugger sessions on a remote z/OS host, and can be configured to launch and debug applications with a single click using the `applicationLaunch` attribute on the `launch` type of config. Alternately, applications or transactions can be launched using external methods, and Z Open Debug can attach to the resultant debug sessions using the `attach` type of launch config.


## LICENSE

SEE LICENSE IN LICENSE.txt

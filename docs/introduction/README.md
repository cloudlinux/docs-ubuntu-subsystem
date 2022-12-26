# Introduction

:::warning Disclaimer
* All mentioned in this documentation trademarks, logos, and copyrights are property of their respective owners and are only mentioned for informative purposes.
* [Ubuntu](https://ubuntu.com/) is a registered trademark of Canonical Ltd.
:::

CloudLinux subsystem on Ubuntu is a scope of deb-packages which allows using CloudLinux features on Ubuntu OS.
For the first beta release we were focusing on the major CloudLinux features for hosting providers: isolation of each customer into a separate “Lightweight Virtualized Environment” (LVE) and “caging” tenants from one another to avoid security breaches.

## Supported version of Ubuntu

We support Ubuntu 20.04 LTS.

## CloudLinux OS editions comparison


|**Features**|**CloudLinux OS Solo**|**CloudLinux OS Admin**|**CloudLinux OS Shared**|**CloudLinux OS Shared Pro**|**<font color="#2c98f0">CloudLinux Subsystem For Ubuntu</font>**|
|:-:|:-:|:-:|:-:|:-:|:-:|
|Maximum amount of hosting accounts|1|5|unlimited|unlimited|**<font color="#2c98f0">unlimited</font>**|
|Resource Limits (LVE)|No|**Yes***|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Cage FS|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|MySQL Governor|No|No|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|PHP Selector|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Other Selectors (Python, Node.js, Ruby)|No|No|**Yes****|**Yes****|**<font color="#2c98f0">No</font>**|
|HardenedPHP|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Apache mod_lsapi PRO|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|SecureLinks|No|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Website monitoring tool|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|Website monitoring alerts|**Yes**|No|No|No|**<font color="#2c98f0">No</font>**|
|Slow Site analyzer|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|PHP X-Ray|**Yes**|**Yes**|No|**Yes**|**<font color="#2c98f0">No</font>**|
|Centralized Monitoring|No|No|No|**Yes**|**<font color="#2c98f0">No</font>**|
|AccelerateWP|**Yes**|**Yes**|No|**Yes**|**<font color="#2c98f0">No</font>**|
|Support 24/7|**Yes**|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|

\* Limits are disabled by default.

\** Python/Node.js/Ruby Selectors are available only for cPanel, DirectAdmin servers, and servers with custom panel with own integration.

## Supported control panels

| **Panel** | **Supported** |
|:-:|:-:|
|[cPanel from v.102](https://blog.cpanel.com/ubuntu-lts-and-full-cpanel-support/) | Yes |
|Plesk| No |
|DirectAdmin| No |
|Other panels| Yes |
|No control panel| Yes |

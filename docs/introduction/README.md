# Introduction

:::warning Disclaimer
* All mentioned in this article trademarks, logos, and copyrights are property of their respective owners and are only mentioned for informative purposes.<br>
** [Ubuntu](https://ubuntu.com/) is a registered trademark of Canonical Ltd.
:::

CloudLinux subsystem on Ubuntu is a scope of deb-packages which allows using CloudLinux features on Ubuntu OS.
For the first beta release we were focusing on the major CloudLinux features for hosting providers: isolation of each customer into a separate “Lightweight Virtualized Environment” (LVE) and “caging” tenants from one another to avoid security breaches.

## Supported version of Ubuntu

We support Ubuntu 20.04 LTS.

## CloudLinux OS editions comparison

|**Features**|**CloudLinux OS Solo**|**CloudLinux OS Shared**|**CloudLinux OS Shared Pro**|**<font color="#2c98f0">CloudLinux Subsystem For Ubuntu</font>**|
|:-:|:-:|:-:|:-:|:-:|
|Maximum amount of hosting accounts|1|unlimited|unlimited|**<font color="#2c98f0">unlimited</font>**|
|Limits (CloudLinux Manager)|No|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Cage FS|No|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|MySQL Governor|No|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|Selectors (PHP, Python, Node.js, Ruby)|No|**Yes**|**Yes**|**<font color="#2c98f0">PHP Selector only</font>**|
|HardenedPHP|No|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Apache mod_lsapi PRO|No|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|SecureLinks|No|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Website monitoring tool|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|Website monitoring alerts|**Yes**|No|No|**<font color="#2c98f0">No</font>**|
|Slow Site analyzer|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">No</font>**|
|PHP X-Ray|**Yes**|No|**Yes**|**<font color="#2c98f0">No</font>**|
|Centralized Monitoring|No|No|**Yes**|**<font color="#2c98f0">No</font>**|
|AccelerateWP|**Yes**|No|**Yes**|**<font color="#2c98f0">No</font>**|
|Support 24/7|**Yes**|**Yes**|**Yes**|**<font color="#2c98f0">Yes</font>**|
|Priority support|No|No|**Yes**|**<font color="#2c98f0">No</font>**|

## Supported control panels

| **Panel** | **Supported** |
|:-:|:-:|
|[cPanel from v.102](https://blog.cpanel.com/ubuntu-lts-and-full-cpanel-support/) | Yes |
|Plesk| No |
|DirectAdmin| No |
|Other panels| Yes |
|No control panel| Yes |
# Introduction

:::warning Disclaimer
All mentioned trademarks, logos, and copyrights are property of their respective owners and are only mentioned for informative purposes.
:::

CloudLinux subsystem on Ubuntu is a scope of deb-packages which allows using CloudLinux features on Ubuntu OS.
For the first beta release we were focusing on the major CloudLinux features for hosting providers: isolation of each customer into a separate “Lightweight Virtualized Environment” (LVE) and “caging” tenants from one another to avoid security breaches.

## Supported version of Ubuntu

We support Ubuntu 20.04 LTS.

## CloudLinux OS editions comparison

|**Features**|**CloudLinux OS Solo**|**CloudLinux OS Shared**|**CloudLinux OS Shared Pro**|**CloudLinux Subsystem For Ubuntu**|
|:-:|:-:|:-:|:-:|:-:|
|Maximum amount of hosting accounts|1|unlimited|unlimited|unlimited|
|Limits (CloudLinux Manager)|No|**Yes**|**Yes**|**Yes**|
|Cage FS|No|**Yes**|**Yes**|**Yes**|
|MySQL Governor|No|**Yes**|**Yes**|No|
|Selectors (PHP, Python, Node.js, Ruby)|No|**Yes**|**Yes**|PHP Selector only|
|HardenedPHP|No|**Yes**|**Yes**|**Yes**|
|Apache mod_lsapi PRO|No|**Yes**|**Yes**|No|
|SecureLinks|No|**Yes**|**Yes**|**Yes**|
|Website monitoring tool|**Yes**|**Yes**|**Yes**|No|
|Website monitoring alerts|**Yes**|No|No|No|
|Slow Site analyzer|**Yes**|**Yes**|**Yes**|No|
|PHP X-Ray|**Yes**|No|**Yes**|No|
|Centralized Monitoring|No|No|**Yes**|No|
|AccelerateWP|**Yes**|No|**Yes**|No|
|Support 24/7|**Yes**|**Yes**|**Yes**|**Yes**|
|Priority support|No|No|**Yes**|No|

## Supported control panels

| **Panel** | **Supported** |
|:-:|:-:|
|[cPanel from v.102](https://blog.cpanel.com/ubuntu-lts-and-full-cpanel-support/) | Yes |
|Plesk| No |
|DirectAdmin| No |
|Other panels| Yes |
|No control panel| Yes |
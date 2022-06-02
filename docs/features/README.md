# Features

Below, you can find the list of supported features with the links to the documentation available.

## LVE limits

* [Understanding limits](https://docs.cloudlinux.com/limits/#understanding-limits)
* [SPEED limit](https://docs.cloudlinux.com/limits/#speed-limit)
* [Memory limit](https://docs.cloudlinux.com/limits/#memory-limit)
* [IO](https://docs.cloudlinux.com/limits/#io)
* [IOPS](https://docs.cloudlinux.com/limits/#iops)
* [Entry processes](https://docs.cloudlinux.com/limits/#entry-processes)
* [Number of processes](https://docs.cloudlinux.com/limits/#number-of-processes)
* [Inodes](https://docs.cloudlinux.com/limits/#inodes)
* [Network traffic bandwidth control and accounting system](https://docs.cloudlinux.com/limits/#network-traffic-bandwidth-control-and-accounting-system)
* [Limits validation](https://docs.cloudlinux.com/limits/#limits-validation)
* [Compatibility matrix](https://docs.cloudlinux.com/limits/#compatibility-matrix)
* [Reseller limits](https://docs.cloudlinux.com/limits/#reseller-limits)

## Inode limits

The documentation is available [here](https://docs.cloudlinux.com/limits/#inodes).

## Reseller limits

The documentation is available [here](https://docs.cloudlinux.com/limits/#reseller-limits).

## Administrator WEB interface (CloudLinux Manager)

The documentation is available [here](https://docs.cloudlinux.com/lve_manager/#cloudlinux-manager).

* [Dashboard](/features/#dashboard)
* [Current Usage](https://docs.cloudlinux.com/lve_manager/#current-usage)
* [Users](https://docs.cloudlinux.com/lve_manager/#users)
* [Statistics](https://docs.cloudlinux.com/lve_manager/#statistics)
* [Packages](https://docs.cloudlinux.com/lve_manager/#packages)
* [Options](https://docs.cloudlinux.com/lve_manager/#options)
* [PHP Selector](https://docs.cloudlinux.com/cloudlinux_os_components/#php-selector)
    * [Installation instructions](/features/#php-selector-installation-instructions)
    * [Selector tab](https://docs.cloudlinux.com/lve_manager/#selector-tab)
    * [Selector tab additional features (cPanel)](https://docs.cloudlinux.com/lve_manager/#selector-tab-additional-features) CloudLinux Manager 6.0.1-2
    * [PHP Selector troubleshooting (cPanel)](https://docs.cloudlinux.com/lve_manager/#php-selector-troubleshooting) CloudLinux Manager 6.0.1-2
    * [PHP Selector diagnostic tool and notifications](https://docs.cloudlinux.com/lve_manager/#php-selector-diagnostic-tool-and-notifications) CloudLinux Manager 6.0.1-2


### Dashboard

:::warning Attention!
MySQL Governor is not available in the current version. We're planning to add it in the upcoming releases.
:::

Dashboard provides a quick overview of statistics and all administrative information for server administrators.

Go to _CloudLinux Manager_ | _Dashboard_.

![](/images/Dashboard.png)


* End Users hitting limits — number of users reaching their limit in any kind of resource. Data is within the last 24 hours.
* Resellers hitting limits —  number of enrolled Resellers that are reaching their limit in any kind of resource. Data is within the last 24 hours.
* [PHP Selector](https://docs.cloudlinux.com/lve_manager/#php-selector-2) block displays the following information:
    * Default version — the default version of PHP binaries. Click _Manage_ to change the default version, enable or disable PHP Selector, change the list of supported versions, and choose default modules. You will be redirected to CloudLinux Manager | PHP Selector. PHP Selector (cPanel) has malfunctions warnings about [the most common issues](https://docs.cloudlinux.com/lve_manager/#errors).
* [CageFS](https://docs.cloudlinux.com/cloudlinux_os_components/#cagefs) block displays the following information:
    * CageFS status (Enabled/Disabled/Not installed). To manage CageFS, click _Manage_. You will be redirected to CloudLinux Manager | Options | CageFS. Click _Install_ to install CageFS.
    * Mode displays the current CageFS mode of operation.
    * End users — displays the number of users with CageFS enabled/all.

## Reseller WEB interface (CloudLinux Manager)

* [Current Usage](https://docs.cloudlinux.com/lve_manager/#current-usage-tab)
* [Historical Usage](https://docs.cloudlinux.com/lve_manager/#historical-usage-tab)
* [Users](https://docs.cloudlinux.com/lve_manager/#users-tab)
* [Statistics](https://docs.cloudlinux.com/lve_manager/#statistics-tab)
* [Packages](https://docs.cloudlinux.com/lve_manager/#packages-tab)

## User WEB interface

* [Resource Usage](https://docs.cloudlinux.com/lve_manager/#resource-usage-client-plugin)
* [PHP Selector](https://docs.cloudlinux.com/lve_manager/#php-selector-client-plugin)

## LVE Wrappers

The documentation is available [here](https://docs.cloudlinux.com/cloudlinux_os_components/#lve-wrappers).

* lve_wrapper
* lve_suwrapper

## CageFS and running commands inside

The documentation is available [here](https://docs.cloudlinux.com/control_panel_integration/#running-commands-inside-cagefs).

* cagefs_enter
* cagefs_enter_user

## Hardened PHP

* alt-php versions 5.6 - 8.0

## Mod_hostinglimits

LVE is a kernel level technology developed by the CloudLinux team. The technology has common roots with container based virtualization and uses cgroups in its latest incarnation. It is lightweight and transparent. The goal of LVE is to make sure that no single web site can bring down your web server.

Today, a single site can consume all CPU, IO, Memory resources or Apache processes - and bring the server to a halt. LVE prevents that. It is done via collaboration of Apache module, PAM module and kernel.

[mod_hostinglimits](https://docs.cloudlinux.com/cloudlinux_os_components/#hostinglimits-module-for-apache) is an Apache module that:
* detects VirtualHost from which the request came;
* detects if it was meant for CGI or PHP script;
* puts Apache process used to serve that request into LVE for the user determined via SuexecUserGroup directive for that virtual host;
* lets Apache to serve the request;
* removes Apache process from user's LVE.

The kernel makes sure that all LVEs get fair share of the server's resources, and that no customer can use more then the limits set for that customer. Today we can limit CPU , Memory (virtual and physical), IO, number of processes as well as the number of entry processes (concurrent connections to apache).

Each LVE limits amount of entry processes (Apache processes entering into LVE) to prevent single site exhausting all Apache processes. If the limit is reached, then mod_hostinglimits will not be able to place Apache process into LVE, and will return error code 508. This way very heavy site would slow down and start returning 508 errors, without affecting other users.

* If the site is limited by CPU or IO, then the site will start responding slower.
* If the site is limited by memory or number of processes limits, then the user will receive 500 or 503 errors that server cannot execute the script.

:::warning Attention! 
In the current version ONLY the following combinations are available: **ea-php81 with php-fpm** and **alt-php with suphp, cgi**
:::

#### ea-php81 with php-fpm

To install, run the following command:

```
# apt install ea-php81*
```

#### alt-php with suphp, cgi

To install, follow these steps:

1. Remove `mod-ruid2`:

   ![](/images/remove-mod-ruid2.png)

2. Install packages (with `alt-php74` as an example):

   ```
   # apt install ea-apache24-mod-suphp ea-apache24-mod-suexec
   # apt install alt-php74
   ```


#### PHP Selector installation instructions

The documentation is available [here](https://docs.cloudlinux.com/cloudlinux_os_components/#php-selector).

:::warning Attention!
Only the following handlers can be used:
* suphp
* cgi
:::

To install, run the following commands:

```
# apt install ea-apache24-mod-suphp ea-apache24-mod-suexec
# apt install cagefs
# cagefsctl –-init
```

## Symlink owner match protection

The documentation is available [here](https://docs.cloudlinux.com/cloudlinux_os_kernel/#fs-enforce-symlinksifowner).

* [fs.enforce_symlinksifowner](https://docs.cloudlinux.com/cloudlinux_os_kernel/#fs-enforce-symlinksifowner)
* [fs.symlinkown_gid](https://docs.cloudlinux.com/cloudlinux_os_kernel/#fs-symlinkown-gid)
* [fs.process_symlinks_by_task](https://docs.cloudlinux.com/cloudlinux_os_kernel/#fs-process-symlinks-by-task)

## Link traversal protection

* [fs.protected_symlinks_create](https://docs.cloudlinux.com/cloudlinux_os_kernel/#link-traversal-protection)
* [fs.protected_hardlinks_create](https://docs.cloudlinux.com/cloudlinux_os_kernel/#link-traversal-protection)

## Tuned profiles

The documentation is available [here](https://docs.cloudlinux.com/cloudlinux_os_kernel/#tuned-profiles-cloudlinux).


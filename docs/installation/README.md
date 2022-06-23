# Installation

For the current release, installation from the ISO images is not available.

:::warning Attention!
This is a beta version! We strongly don't recommend using it on the production servers!
:::

To install the CloudLinux subsystem, run the following command:

```
# apt install python3
# wget https://repo.cloudlinux.com/cloudlinux-ubuntu/sources/cln/ubuntu2cloudlinux.py
# python3 ubuntu2cloudlinux.py
# reboot
```

No registration required! You can start working right after the installation.

## Ubuntu2Cloudlinux explained

The `ubuntu2cloudlinux.py` script gives an opportunity to install CloudLinux Subsystem For Ubuntu. It is much more simplier script than the CLdeploy script for CentOS and AlmaLinux. For example, it doesn't replace the linux kernel, only adds a dynamic module to it. Here is a list of actions done by the `ubuntu2cloudlinux`:

* It checks that you are running the latest available version of the `ubuntu2cloudlinux.py script`, and updates itself if necessary.
* Upgrades all installed packages to the latest versions (unless the `--skip-full-update` option is passed).
* Adds to your system CloudLinux repositories for Ubuntu and a corresponding gpg key.
* Installs a minimum set of CloudLinux OS components: lve, kernel module kmodlve-dkms, lve-utils, lve-stats, alt-python.
* Installs CloudLinux Manager (currently works with cPanel on Ubuntu).
* Installs the mod_hostinglimits Apache module.
* Asks you to manually reboot the system to load a new kernel module.

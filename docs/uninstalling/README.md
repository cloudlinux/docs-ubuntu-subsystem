# Uninstalling

### Deleting the CloudLinux Subsystem For Ubuntu

You can uninstall CloudLinux Subsystem For Ubuntu by running the following command:

```
./ubuntu2cloudlinux.py --uninstall
```

In that case the script will:

* Remove the CloudLinux OS components which are installed on your system, choosing from the following list: lve, kmodlve-dkms, lve-utils, lve-stats, lvemanager, cagefs, alt-python, alt-php, db-governor.
* Remove configs for CloudLinux repositories for Ubuntu.
* Ask you to check for remaining packages from CloudLinux and manually reboot your system.

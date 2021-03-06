# WordPress Optimization Suite

Also called WP Optimization Suite.

## Introduction

Performance has a great impact on the site attendance and efficiency. We know that many customers want an auto tool to resolve problems with site performance. Many sites are built with WordPress CMS. So, we decided to find and implement some complex solution – the “WordPress Optimization Suite” to help our customers increase their site performance.

We introduce the first functionality for the optimization suite called “Object cache module”.

### Object caching explanation

Caching is a mechanism of accessing frequently used data quickly. This mechanism is really helpful in case your site needs to process multiple pages per second as requests come in. If data is stored in cache the server does not need to process it time after time because such data can be obtained from the cache. So, visitors get it faster – it is really fantastic!

And one more interesting thing is that there are different types of caching.

* One type of caching is already used by your browser (client-side).
* And another type of caching (one of server-side) is used to store database queries data and is called the Object cache.

The speed of processing queries to the database is very important for WordPress CMS, because all content data is stored in the WordPress database. So, if you activate (turn on) the Object cache module it means that you activate some storage to cache queries from your clients to the WordPress database. Every time users of your site request some content for the web page it makes a request to the WordPress database.

### Our solution for the Object cache module

The solution is based on the Redis Object cache [https://wordpress.org/plugins/redis-cache/](https://wordpress.org/plugins/redis-cache/) and automatically sets up the Redis key-value storage and configures it appropriately.

The storage is located in the RAM of the server which stores data from the WordPress database queries. It caches objects between multiple page loads. But restarting the Object cache module daemon (very rare situation) will erase the data in the storage, and some period of time is needed to collect the data again.

When we recommend to use Object cache module:

* Websites used for extremely active exchange of information (forums, blogs, etc..)
* Websites with too many requests running at the same time
* Websites having important pages that cannot be cached entirely and exclude from the "whole page caching" due to any reason


#### How can we monitor the state of the Object cache module?

* Status of the storage (or Object cache database)
* Cache memory usage (or memory usage by the Object cache module)
* Max Memory usage limit (or limit for memory using by the Object cache module)


### Limitations

For the first beta release, there are the following limitations:

* Recommended WordPress version 3.7 and higher.
* Object Cache module conflicts with other WordPress Caching plugins.
* Object Cache module conflicts with the [Snuffleupagus](https://snuffleupagus.readthedocs.io/) php-extension.
* Object Cache module does not work with WordPress Multisite mode.

Let’s go to the interface and see how to use the WP Optimization Suite.


## WP Optimization Suite User Interface

1. Go to the list of software on your control panel and find the WP Optimization Suite icon:

![](/images/WPOptimizationSuiteIcon.png)

2. Open plugin interface

![](/images/WPPluginInterface.png)

1. Find a website for which you want to apply the Object Cache plugin and turn it on

![](/images/ObjectCachePluginTurnOn.png)

### Object Cache plugin information panel

On the Object Cache plugin information panel you can find the following statuses.

* **Object Cache module Database status**

It will be offline if there is no sites using the Object Cache plugin.

![](/images/ObjectCacheModuleDatabaseStatus.png)

* **Amount of memory used by the Object Cache database**
  
![](/images/CacheMemoryUsage.png)

:::warning Attention!
In the first beta release this memory usage includes memory usage by the inner Object Cache plugin structures.
So, it cannot be zero.
:::

* **Limit for the Object Cache database**

![](/images/MaxCacheMemoryLimit.png)


Click on the ![](/images/EditLimitPen.png) to change the limit.

:::warning Attention!
There is the value limitation for the Max Cache Memory: from 16 MB to 16 GB.
:::

![](/images/CacheMemoryLimitation.png)

Use the ![](/images/PurgeAllCache.png) button to clear cache for all websites.

### Verifying and changing PHP version for the website

#### Verifying PHP version for the website

It is important to use `ea-php`/`alt-php` version 7.4 and 8.0 for your website to turn ON Object Cache Module. Here is a small instruction on how to determine the current version of a particular website.

* If you can not open CloudLinux PHP Selector
    (you have no such link ![](/images/SelectPHPVersion.png) or you cannot manage PHP versions when CageFS is disabled)

    Open ![](/images/MultiPHPManager.png) and find your domain, the `PHP version` column contains needed information.

    ![](/images/PHPVersionChecked.png)

* If you can open CloudLinux PHP Selector, you can find the actual PHP version in the `version` column.

    ![](/images/PHPVersionChecked2.png)


#### Changing PHP version for the website

* To use ea-php (7.4 or 8.0), use Multi PHP Manager. Make sure that in CloudLinux PHP selector (if it is available) the current PHP version is `Native`. 
* If you want to use alt-php (7.4 or 8.0), use CloudLinux PHP Selector (if it is available) to change the version.
	

### Error messages

#### No compatibility message

Causes of the "No compatibility" message are always [Limitations](/wpos-plugin/#limitations). Each message has a small "how to", so you can try to fix them by yourself via cPanel or WordPress Admin interface.

![](/images/WPNoCompatibility.png)

#### Misconfiguration message

The misconfiguration message can appear in the following cases:

* Redis process cannot be started for some period of time. **Resolution**: [contact our support team](https://cloudlinux.zendesk.com/hc/en-us/requests/new) for further investigation.
* WordPress Redis Object Cache plugin is disabled via WordPress Admin Gui/Plugins. **Resolution** You can resolved it by yourself via the WordPress Admin Gui.
* Version of PHP is incompatible or does not have all needed modules installed.

![](/images/WPMisconfiguration.png)

#### Post check issues

If you have some Post check issue after turning On the Object Cache module, you can leave them as disabled (in that case the engine reverts all changes). Or you can ignore the issue and continue working with the enabled Object Cache module.

#### General errors and warnings during activation plugin

If you get something like "Unexpected WordPress error" you can do the following:

![](/images/UnexpectedError.png)

* As the first step, verify that [Limitations](/wpos-plugin/#limitations) are not broken.
* As the second step, [contact our support team](https://cloudlinux.zendesk.com/hc/en-us/requests/new) for further investigation.


### Object Cache module Known Issues

If you open the WordPress admin panel and find Redis Object cache plugin, open Settings for it, you can find the following:

**Port: 6379**

It is incorrect (will be fixed soon), it works via the **file socket**.

## FAQ

### How to measure the speed of the website?

You can measure the speed of your website before turning On the Object Cache module and after.

The popular tools:

* [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
* [Pingdom Website Speed Test](https://tools.pingdom.com/)

### Where the WP optimization tool log files are located?

Login via SSH, find in your home directory  `~/.clwpos/main.log`. Or you can open it using the control panel file manager.

### I already use the WordPress Redis object cache plugin. Will the WP Optimization Suite be useful for me?

No, in the current version we suggest the same optimization as you already have. But we include other useful modules in the next versions, so let’s stay in touch.

### I already use the WordPress Redis object cache PRO plugin. Will the WP Optimization Suite be useful for me?

No, in the current version we suggest the same optimization as you already have. But we include other useful modules in the next versions, so let’s stay in touch.







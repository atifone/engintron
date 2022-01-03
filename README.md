### root@cpanelsrv [~]#   *Engintron v2.0 (Build 20220103) updated on January 3rd, 2022*

**Have a look at the [CHANGELOG](https://engintron.com/docs/#/pages/Changelog) for more information on this latest release**

***
![Engintron](https://engintron.com/assets/logo/Engintron_Logo_316x98_24_black.png)

_Engintron for cPanel/WHM is the easiest way to integrate Nginx on your cPanel/WHM server. Engintron will improve the performance & web serving capacity of your server, while reducing CPU/RAM load at the same time. It does that by installing & configuring the popular Nginx webserver to act as a reverse caching proxy for static files (like CSS, JS, images etc.) with an additional micro-cache layer to significantly improve performance of dynamic content generated by CMSs like WordPress, Joomla or Drupal as well as forum software like vBulletin, phpBB, SMF or e-commerce solutions like Magento, OpenCart, PrestaShop and others._

***
##### Quick Navigation
* [engintron.com](https://engintron.com)
* [Documentation](https://engintron.com/docs)
* [FAQ](https://engintron.com/docs/#/pages/FAQ)
* [Get support & report bugs (Issues)](https://github.com/engintron/engintron/issues)
* [Join the Engintron Newsletter / Mailing List](https://tinyletter.com/engintron)
* Engintron on [Facebook](https://www.facebook.com/engintron/) & [Twitter](https://twitter.com/engintron_sh)
* [Rate and/or review Engintron in the cPanel Applications Directory](https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel)
* [Donate & Support the development of Engintron](https://engintron.com/?donate)

![Engintron v2 WHM App (kudos to Anthony Boyd Graphics for the IBM Desktop mockup)](https://user-images.githubusercontent.com/1301787/147956182-e2e11894-32e9-4b45-92b4-b85e47e52a7e.jpg)


***
## Engintron is Nginx on cPanel, done right!
[Nginx®](https://nginx.org/) is a powerful open source web server that was built to scale websites to millions of visitors. cPanel® is the leading hosting control panel worldwide.

Engintron integrates Nginx into cPanel so you can enjoy amazing performance for your sites, without having to sacrifice important hosting features found in cPanel.

_And best of all? Engintron is totally free to use!_


### But why should you use Nginx in your cPanel server?
cPanel uses the Apache webserver to serve websites by default. Apache however is not known to perform well under heavy web traffic (especially traffic spikes) and it's also CPU/RAM hungry. So how can you mitigate these issues? The answer is simple: by deploying Nginx, another popular web server software, in front of Apache. Nginx acts as a web traffic proxy, directly serving all static assets like CSS, JS, images etc. by default, instead of Apache. This drops significantly the CPU/RAM resources consumed by Apache, leaving your server with more available resources for other tasks or, better still, with room for more websites to host.

The way Engintron sets up Nginx inside your cPanel is a lot like how the popular CloudFlare CDN works. Nginx (like CloudFlare) directly serves all static content like CSS, JS, images etc. instead of your actual web server, thus lowering the load on your cPanel server. But unlike CloudFlare which requires that all your domains are set up with that service, you do everything inside your cPanel server. And better still? You also have an additional caching layer for when your traffic spikes, not just on one website, but entirely for your server. This additional caching layer is referred to as a "micro cache" and it only caches GET & HEAD requests (never POST requests) which means that it is possible to use it on any type of website, either a small dynamic Joomla corporate website or WordPress blog to a more complex news portal or forum or e-commerce website, that requires users to log in and handle personalized content or even generate content. Engintron's 1 second "micro cache" solution setup with Nginx is therefore ideal for any type of website and it can raise the number of concurrent requests served by your cPanel server from a few hundred per second (using just Apache) to thousands (using Nginx in front of Apache).

Not only will your serving capacity increase, but the load on your server will also significantly drop :)

If you are facing performance issues with your cPanel server, Engintron is your go-to solution. And in fact it's really a "set & forget" solution as you'll set it up once and then it will just run on your server without any additional maintenance on your side.

If you can sign up for a cPanel/WHM server on any hosting company and work your way through WHM, then setting up Engintron should be a piece of cake for you. If you don't manage your cPanel server, then you can always (kindly) ask your hosting company or system administrator to have a look at Engintron and deploy it on your cPanel server. It really only takes a few minutes and there is zero configuration afterwards to get the standard optimizations offered by Nginx.


### OK, I'm sold! How do I install Engintron on my cPanel server?
Installation is a process that lasts only a few minutes.

You'll need root SSH access to your cPanel server. Also check the current requirements (listed lower).

If everything is ok, log in as root and type the following command:

```
curl -sSL https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh | bash -s -- install
```

If cURL is not available on your system, you can use wget like so:

```
wget --no-check-certificate -O - https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh | bash -s -- install
```

The process will take a couple of minutes to complete and after that, Engintron will be installed on your cPanel server. Engintron has a nice & simple user interface which is activated inside WHM, under the Plugins section. After installation, refresh WHM in your browser and you should see Engintron in the Plugins section (it's the absolute last section in WHM's sidebar).

In there, you'll find basic options to control Nginx, Apache and MySQL, all in one convenient place. Additionally, you can edit all of Nginx's configuration files (as well as some from Apache & MySQL) to get even more from Engintron (e.g. configure Engintron for use with CloudFlare). If however all you want is to accelerate both static & dynamic content delivery, then Engintron is already setup for you and you don't need to do anything more.

Inside the Engintron app dashboard you'll also find some handy utilities to monitor things like your Nginx access & error logs, check processes on your server, run database diagnostics or list active connections on ports 80 & 443 (for HTTP & HTTPS traffic respectively).

_For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: [https://engintron.com/docs](https://engintron.com/docs)_


### Why is Engintron a better solution compared to other Nginx (or performance related) plugins for cPanel
There are 10 key differences when comparing Engintron with other Nginx installers for cPanel.

First and foremost, caching actually works with Engintron. It works as it should and it works universally. You install it and ALL your cPanel websites will get accelerated, even the slowest ones. Not only that, your serving capacity will increase tremendously. Simple Apache Benchmark (ab) tests reveal a phenomenal increase in concurrent requests served per second, from just 3-300 in Apache to 15,000-20,000 or even more using Nginx via Engintron. It's our carefully crafted Nginx proxy configuration that does all the magic. And it requires literally almost zero maintenance.

Second, Engintron is a single shell script (weighing only a few KBs) that installs all required software (to make Nginx work as intended) from the official software package vendors' repositories. Both installation and updates are very fast (they take only a few seconds).

Third, since we're using the official repositories for Nginx, all Engintron software is updated whenever cPanel (or the server's software) is updated. So you essentially set it and forget it. Whenever you perform "yum update" or "dnf update" from the terminal or upgrade the server's software from within WHM, Nginx will be updated if a new release is available. If something is changed on Engintron and you need to re-install it or a new version of Engintron is released, you simply install it on top of the previous installation, either from the terminal or using the Engintron WHM app. You don't need to uninstall it first like other Nginx plugins for cPanel require you to do so before upgrading!

Fourth, you can safely uninstall Engintron and it will *revert* your entire system to how it was before you installed Engintron. Simple as that. Which means you can try Engintron and if you don't like it or you find it doesn't fit your needs, you can simply uninstall it. Your system will revert to how it was before. Period.

Fifth, it has an amazingly simple yet practical app dashboard inside WHM with all the basic controls for Nginx, Apache, MySQL, the option to edit all important configuration files for these services and even some handy utilities that make Engintron the dashboard in cPanel for your day-to-day sysadmin tasks. Think of it as your cPanel server's mission control. And did we mention you can easily update Engintron from within WHM? Yeap! You even get update notifications when a new version is available.

Sixth, it's CloudFlare friendly. Because both CloudFlare and Engintron use Nginx as a reverse caching proxy, unless we configure Nginx in cPanel to properly act as the secondary proxy (after CloudFlare of course), chances are that CloudFlare will freak out and serve your sites with 10xx errors. So, if you have any domains hosted on your cPanel server that use CloudFlare for their CDN, you just set your server IPs inside your "custom_rules" Nginx configuration file (the file is commented for your help) and just restart Nginx for the changes to take effect. All this is done entirely inside WHM of course.

Seventh, it doesn't require manual Nginx/Apache vhost synchronization when adding new domains via cPanel. That's why you essentially "set it and forget it". Have a look at the other Nginx plugins for cPanel... 'Nough said ;)

Eighth, Engintron allows for both HTTP and HTTPS traffic to flow through Nginx entirely, as of version 1.8.0.

Ninth, Engintron is 100% open source. You can easily examine its code here on GitHub, tear it apart, customize it, fork it, knife it or contribute back to its development. Do whatever you want with it :)

And finally, Engintron (which was originally launched in April 2014) is nowadays a mature project, one of the most popular cPanel plugins and the defacto Nginx installer for cPanel. It is by far [the most reviewed plugin on the cPanel Applications Directory](https://applications.cpanel.net/listings#/listings/index/sort:Listing.review_count/direction:desc) and [the cPanel plugin/addon with most stars on GitHub](https://github.com/topics/cpanel?o=desc&s=stars). According to simplified analytics from the Engintron WHM app (added in February 2016), it is actively used by dozens of thousands of sysadmins in 150+ countries around the world. According to [BuiltWith](https://trends.builtwith.com/framework/Engintron), more than 300,000 sites worldwide are powered by Engintron optimized cPanel servers. BuiltWith also reports around 1,5 million sites powered by cPanel. In other words, 1 in 5 cPanel servers worldwide has Engintron installed. The actual numbers may differ of course, but statistically speaking, it's an interesting fact nevertheless...


### Not so fast buddy... cPanel officially added support for Nginx in 2021. Why should I use Engintron?
cPanel indeed added support for Nginx back in 2021. In fact, they integrate Nginx in 2 ways: as a proxy (like Engintron) and as a direct replacement for Apache.

Engintron is different for 3 + 1 reasons really:

* Engintron has a kick-ass, flexible proxy configuration for Nginx, which has powered hundreds of thousands of sites worldwide since 2014, unlike any other system, even cPanel's own proxy option in Nginx. The latter also follows an entirely different logic to Engintron. We'd like to think Engintron's is more flexible and also truly plug-n-play. Performance wise, Engintron's proxy configuration for Nginx is also faster compared to cPanel's (not our word, cPanel's... have a look [here](https://web.archive.org/web/20210420034851/https://blog.cpanel.com/how-to-install-and-manage-nginx-on-cpanel/) or [here](https://archive.ph/NOI2v)...).
* Engintron uses the official Nginx packages, provided by Nginx.org. So you get instant Nginx updates and don't have to wait for cPanel to bundle Nginx separately.
* Because of Engintron's kick-ass proxy configuration for Nginx, you can continue using Apache as your main web server. That's a huge plus for existing webhosts. The alternative of using cPanel's Nginx as a direct Apache replacement opens up all kinds of issues, as Nginx was never really built to support shared hosting environments for which Apache is more suitable.
* And finally, Engintron has a cool WHM dashboard (and CLI interface) which is not tied exclusively to Nginx. Instead you get additional options and utilities to make managing your cPanel server much more efficient. And these options and utilities are regularly updated and expanded. Once you use Engintron for a while, it'll become your go-to dashboard in WHM.


### FAQ
The FAQ section has been moved in the Engintron Docs: https://engintron.com/docs/#/pages/FAQ


### Changelog
The Changelog section has been moved in the Engintron Docs: https://engintron.com/docs/#/pages/Changelog


### Compatibility & Requirements
Engintron is tested only on platforms that are actively supported by cPanel itself.

As such, as of January 2022, Engintron is fully compatible with CentOS 6 with CloudLinux (the only actively supported Enterprise Linux variant by cPanel as CentOS 6 is officially EOL since 2020), CentOS 7 and all EL 8 variants such as AlmaLinux, Rocky Linux & CentOS 8 (for which support by Red Hat stopped at the end of 2021).

Engintron should also work on other EL 8 variants (e.g. Oracle Linux, Amazon Linux etc.) that can run cPanel (albeit "unofficially")...

Additionally, once cPanel is officially released to also support Ubuntu (in the near future), Engintron will also be released to support Ubuntu as well.


### License
Engintron is released under the GNU/GPL license. For more info, have a look here: [https://www.gnu.org/copyleft/gpl.html](https://www.gnu.org/copyleft/gpl.html)


### Documentation
For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's documentation pages at: [https://engintron.com/docs](https://engintron.com/docs)


### Feedback, bugs, feature requests & rating
Please post your feedback and any issues or feature requests/suggestions in the project's issue tracker at: https://github.com/engintron/engintron/issues

If you use Engintron, please take a moment to post a review and/or rating in the cPanel Applications Directory at: https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel


### Join the Engintron Newsletter / Mailing List
It's easy to miss an Engintron update on social media. If you want to know for sure when the latest version of Engintron is released, sign up to get notified directly to your inbox. We will never spam you.

Sign up here https://tinyletter.com/engintron or here https://engintron.com


### Donate & support the development of Engintron
Does Engintron bring value to your business? If so, you can donate & support the development of Engintron at: https://engintron.com/?donate


## Commercial support & server optimization services
Engintron will greatly improve your cPanel server's performance, but it will only get you halfway through to what your hardware can actually support, especially when all crucial server components like Apache, MySQL/MariaDB or PHP use "stock" configurations (or worse, badly optimized configurations), unsuitable for your server's hardware specifications.

And although we do provide optimization guides in the Engintron documentation site (see "BEYOND ENGINTRON - OPTIMIZATION GUIDES" here [https://engintron.com/docs](https://engintron.com/docs)), it takes experience to fine tune any configuration to match a server's specifications.

The performance optimization package we offer involves tuning the most essential services:
* Apache, MySQL/MariaDB and PHP
* the system's network throughput and disk I/O
* installing a new optimized EasyApache 4 profile with support for PHP versions 5.6, 7.x and 8.x & switching the server to PHP-FPM exclusively while setting up caching options like APCu, Opcache & Memcached (with support for PHP code)
* properly configuring the server's firewall for basic DoS protection

At the end you get a full report of what has been optimized.

So, if you wish to go the "extra mile" and optimize your cPanel server both through Engintron as well as through the services that directly affect the server's performance, feel free to use the contact options from within Engintron's WHM app to get in touch with us. Or you can simply email us at: engintron [at] gmail [dot] com


***

Copyright &copy; 2018 - 2022 [Kodeka OÜ](https://kodeka.io)

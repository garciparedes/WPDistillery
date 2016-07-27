## Setup
To setup a new project running Scotch Box, WordPress and WooCommerce simply follow these steps:

1. Run the following command inside your project root to install both Scotch Box & WPDistillery:
```bash
git clone https://github.com/scotch-io/scotch-box.git && mv scotch-box/public public && mv scotch-box/Vagrantfile Vagrantfile && rm -rf scotch-box && git clone --depth 1 git@github.com:garciparedes/WooCommerceDistillery.git && mv WooCommerceDistillery/config.yml config.yml && mv WooCommerceDistillery/setup.sh setup.sh && rm -rf WooCommerceDistillery
```
2. add environment variables and your preferred options into `config.yml` (see [configuration file documentation](README_CONFIG.md) for additional info on `config.yml`)
4. `vagrant up` then `vagrant ssh`
5. update wp cli `sudo wp cli update --allow-root` see [Known Issues](https://github.com/flurinduerst/WPDistillery#known-issues)
6. execute setup.sh `cd ../../var/www/ && bash setup.sh`


## Known Issues
* Currently Scotch Box comes with `WP-CLI 0.20.3` The WP-CLI released compatibility updates for WordPress 4.4 and now requires Version `0.20.4+`. Please update wp cli on the VM with `sudo wp cli update --allow-root`. See [issue#158](https://github.com/scotch-io/scotch-box/issues/158)
* When using Wordmove (install it with `gem install wordmove` on the VM) you have to complete the locale settings by adding them to `.bashrc`:
```
echo "export LANGUAGE=en_US.UTF-8">>~/.bashrc
echo "export LC_ALL=en_US.UTF-8 ">>~/.bashrc
```
then `exit` and `vagrant ssh` and you're good to go. (This is a ScotchBox issue but I wanted to clarify this for everyone using Wordmove.)

## About
### Author: Flurin Dürst
* Contact: [flurin@flurinduerst.ch](mailto:flurin@flurinduerst.ch)
* Twitter: [@flurinduerst](https://twitter.com/flurinduerst)


### Author: Sergio García
* Contact: [sergio@garciparedes.me](mailto:sergio@garciparedes.me)
* Facebook: [garciparedes](https://facebook.com/garciparedes)
* Twitter: [@garciparedes](https://twitter.com/garciparedes)
 
##### Contribution
Feel free to contact me or add issues/pull-requests.

#### License
WPDistillery is released under the terms of the [GNU General Public License, Version 3](https://www.gnu.org/licenses/gpl)

## Like it? Awesome!
If you find this tool useful, consider supporting WP Distillery or [buying me a beer](https://www.paypal.me/garciparedes/5) respectively [a glass of single malt scotch whiskey](https://www.paypal.me/garciparedes/10) :)

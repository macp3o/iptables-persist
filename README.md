
# Persistent iptables and Autoloader

`iptables-autoload` is an `initd` service that automatically persists and reloads `iptables` rules during power cycles.

With `iptables-autoload`, `iptables` rules are automatically restored after power on to the value they had before halting the system.


## How It Works

The service works in two steps:

1. It saves `iptables` configuration changes on power down, and
2. It reloads the saved rules on power up.

Rules are saved to and reloaded from `/etc/iptables.autoload`

The rules can be saved to disk at any other time by running:

> service iptables-autoload restart


## Installation

### Requirements

 * `iptables` should be installed.
 * The current version was tested on Debian Wheezy.

### Setup

To setup the script:

1. Run `iptables-save > /etc/iptables.autoload` to save the current `iptables` rules.
2. Copy the `iptables-autoload` script into `/etc/init.d/`
3. Run `update-rc.d iptables-autoload defaults`

Enjoy!


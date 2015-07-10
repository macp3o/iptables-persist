
# iptables-autoload

### Persistent iptables Rules During Power Cycles

`iptables-autoload` is an `initd` service that automatically persists `iptables` rules during power cycles. `iptables` rules are automatically restored after power on to the value they had before halting the system.


## How It Works

The service works in two steps:

1. It saves `iptables` configuration changes on power down, and
2. It reloads the saved rules on power up.

Rules are saved to and reloaded from `/etc/iptables.autoload`

Rules can be saved to disk at any other time by running:

> service iptables-autoload restart


## Requirements

 * `iptables` should be installed.
 * The current version was tested on Debian Wheezy.


## Installation

To setup the script:

1. Run `iptables-save > /etc/iptables.autoload`. This saves the current `iptables` rules.
2. Copy the `iptables-autoload` script into `/etc/init.d/`
3. Run `update-rc.d iptables-autoload defaults`

Enjoy!


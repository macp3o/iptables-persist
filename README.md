
# iptables-autoload

This `initd` service automatically persists `iptables` rules during power cycles.

The service works in two steps:
1. It saves `iptables` configuration changes on power down, and
2. Reloads `iptables` rules on power up.

Settings can be saved to disk at any time by running:

> service iptables-autoload restart

Settings are saved in `/etc/iptables.autoload`

---

### Installation

To setup the service script:

1. Run `iptables-save > /etc/iptables.autoload`
2. Copy the `iptables-autoload` script into `/etc/init.d/`
3. Run `update-rc.d iptables-autoload defaults`

Enjoy!


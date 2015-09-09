# Persistent iptables

`iptables-persist` is an `init.d` service that automatically persists and reloads `iptables` rules during power cycles.

With `iptables-persist`, `iptables` rules are automatically saved when the system shutdowns and restored to the saved value after powering up.


## Installation

To install the script:

1. Run as root: `iptables-save > /etc/iptables.persist` to save the current `iptables` rules.
2. Copy the `iptables-persist` script into `/etc/init.d/`
3. Run `update-rc.d iptables-persist defaults`


## Usage

The rules are persisted in `/etc/iptables.persist`

To force saving the rules, for instance after making changes:
~~~
	# service iptables-autoload restart
~~~


## License

MIT license. See the [LICENSE](https://raw.githubusercontent.com/p3o/iptables-persist/master/LICENSE) file. 

Enjoy!


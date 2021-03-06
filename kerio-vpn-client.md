# Kerio VPN Client

How to connect to Kerio VPN from Ubuntu

## Installation

Download VPN client from VPN tab at http://www.kerio.com/support/kerio-control.

Note: download will be done over `http://`, there is no `https://` option. There is no checksum to verify downloaded file. _Private_ in _Virtual Private Network_ ends here.

Installation via Ubuntu Software (`/usr/bin/gnome-software`) does not work,
presumable because of configuration step, as there was stuck debconf frontend
and `kerio-control-vpnclient.config` program.

Read [installation instructions][doc] and install using `dpkg -i [.deb]`. It
works just fine and runs configuration during installation.

[doc]: http://download.kerio.com/dwn/kerio-control-vpnclient-linux.deb.readme

## Configuration

To change connection use `dpkg-reconfigure kerio-control-vpnclient`. It would allow to change only one connection, but based on content of configuration file, it could be assumed that multiple connections could be configured. Use `sudo cat /etc/kerio-kvc.conf` to see raw configuration file.

## Usage

Kerio VPN Client is very sticky, once installed it is constantly on. Following commands will prevent it's startup on every boot and would require manual start.

```
sudo update-rc.d kerio-kvc disable 5
sudo service kerio-kvc stop
```

## Troubleshooting

See [common recipes][common-receipes] for troubleshooting VPN client connection issues.

- `tail -f /var/log/kerio-kvc/error.log`

[common-receipes]: https://github.com/irnc/ubuntu-vpn-clients/blob/master/common-troubleshooting-recipes.md

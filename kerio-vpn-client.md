# Kerio VPN Client

## Configuration

To change connection use `dpkg-reconfigure kerio-control-vpnclient`. It would allow to change only one connection, but based on content of configuration file, it could be assumed that multiple connections could be configured. Use `sudo cat /etc/kerio-kvc.conf` to see raw configuration file.

## Troubleshooting

See [common recipes][common-receipes] for troubleshooting VPN client connection issues.

- `tail -f /var/log/kerio-kvc/error.log`

[common-receipes]: https://github.com/irnc/ubuntu-vpn-clients/blob/master/common-troubleshooting-recipes.md

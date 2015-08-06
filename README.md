# How to setup IPSec VPN via IKEV1

The script and config files will help you setup **IPSec VPN via IKEV1**, supporting
two authentication methods:

- XAuth and certificates
- PSK (Preshared Key)

Note: only tested on Ubuntu 14.04.

## Setup on server

1. Edit `etc/ipsec.secrets`, set your preshared key and add user.
2. Run `./setup.sh <server name or ip>`.

Take a look at the end of `setup.sh` for a few useful ipsec command.

## Setup on client

It's much easier to setup client for PSK authentication, all you need on the
client is the preshared key and user & password.

For XAuth and certificates, please refer to 
[install
certificates](https://wiki.strongswan.org/projects/strongswan/wiki/IOS_(Apple)#Install-certificates)
section in the reference.

Caveats for OS X Key Chain import:

- Use the import menu item in Key Chain app, so you can choose where to import
  certificate
- To set access control for the private key, you must first unlock the System
  key chain

# References

- Mainly based on https://wiki.strongswan.org/projects/strongswan/wiki/IOS_(Apple)
- For PSK settings https://wiki.strongswan.org/issues/218


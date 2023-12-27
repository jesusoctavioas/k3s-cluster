# Cluster

Cluster related tasks.

## Troubleshooting

Analyze services:

```shell
systemd-analyze blame
```

List package reversed dependencies:

```shell
apt rdepends --installed --recurse git
```

List service dependencies:

```shell
systemctl list-dependencies snapd
systemctl list-dependencies --reverse snapd.socket
```

## Postfix

- `postfix` configuration: `/etc/postfix/main.cf`
- `debconf` database: `/var/cache/debconf/config.dat`
- `postfix` `dpkg` confguration: `/var/lib/dpkg/info/postfix.config`

Show `debconf` configuration settings:

```shell
debconf-show postfix
```

Show `postfix` default configuration setting:

```shell
postconf -d smtp_sasl_auth_enable
```

Reconfigure `postfix`:

```shell
dpkg-reconfigure postfix
```

Uninstall `postfix``:

```shell
apt remove --purge -y postfix ssl-cert mailutils
apt autoremove
apt clean
rm -f /etc/aliases /etc/aliases.db /etc/mailname
```

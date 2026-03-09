# Xray-core OpenWrt packages feed

Opkg feed of xray-core for OpenWrt users.

Packages for different platforms contain init scripts and other default files.

## Supported OpenWrt versions

| OpenWRT | xray-core |
|---------|-----------|
| 24.10.5 | 26.2.6    |

## How to install

```
grep -q xray-core /etc/opkg/customfeeds.conf || echo src/gz xray-core https://github.com/cherts/xray-core-openwrt/raw/$(. /etc/openwrt_release && echo "$DISTRIB_RELEASE") >> /etc/opkg/customfeeds.conf
wget https://github.com/cherts/xray-core-openwrt/raw/main/xray-core.pub -O /tmp/xray-core.pub && opkg-key add /tmp/xray-core.pub
opkg update
opkg install v2ray-geoip xray-core
```
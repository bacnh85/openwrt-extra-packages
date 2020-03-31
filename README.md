## Description

This is my OpenWrt "custom"-feed containing my build scripts, options and patches for applications, modules and libraries used for my router which are not available in the upstream OpenWrt package.

Installation of pre-built packages is handled directly by the opkg utility within your running OpenWrt system or by using the OpenWrt SDK on a build system. Repo URL is located at https://pub.bacnh.com/openwrt/

## List of packages

[paho.mqtt.c](libs/paho.mqtt.c) - An Eclipse Paho C client library for MQTT for Windows, Linux and MacOS. https://eclipse.org/paho

## Usage

Add this feed into your feeds.conf
```
src-git custom https://github.com/ngohaibac/openwrt-extra-packages
```

This feed is enabled by default. To install all its package definitions, run:

```
./scripts/feeds update custom
./scripts/feeds install -a -p custom
```
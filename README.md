# Image builder of GL-AR300M Nor, GL-AR150, GL-MiFi, GL-USB150 and GL.iNet6416

This is the image builder for AR300M Nor, AR150, GL-MiFi and GL-6416. You can use this image builder to build a firmware quickly.

## System Requirement
1. x86_64 platform
2. ubuntu or other linux
3. You need to install necessary software
```
$ sudo apt-get update
$ sudo apt-get install subversion build-essential git-core libncurses5-dev zlib1g-dev gawk flex quilt libssl-dev xsltproc libxml-parser-perl mercurial bzr ecj cvs unzip git wget
```

## Download the source code

First, download this image builder
```
git clone https://github.com/domino-team/imagebuilder-cc-ar71xx.git
cd imagebuilder-cc-ar71xx
```
You need to make some default configuration. We have stored some configurations in our githug and you can just clone them.
```
https://github.com/domino-team/openwrt-files.git files
```
Now there are some default settings in files folder

## Build the firmware

Here is some examples to build a working firmware for your router.

For example, if you want to build a clean firmware with luci, do the following/

For GL-AR150
```
make image PROFILE=GL-AR150 PACKAGES="luci" FILES=files/files-clean-ar/
```
For GL-AR300M
```
make image PROFILE=GL-AR300M PACKAGES="luci" FILES=files/files-clean-ar/
```
For GL-MiFi
```
make image PROFILE=GL-MIFI PACKAGES="luci" FILES=files/files-clean-ar/
```
For GL-USB150 Microuter
```
make image PROFILE=GL-USB150 PACKAGES="luci" FILES=files/files-clean-ar/
```
For GL.iNet6416
```
make image PROFILE=GLINET PACKAGES="luci" FILES=files/files-clean-ar/
```

If you want to build a Tor firmware for AR150, do this following:
```
make image PROFILE="GL-AR150" PACKAGES="uhttpd ethtool blkid iwinfo block-mount curl gnupg iw jshn kmod-fs-ext4 kmod-fs-ntfs kmod-fs-vfat kmod-fs-ext4 ntfs-3g kmod-fs-hfs kmod-fs-hfsplus kmod-fs-reiserfs kmod-fuse kmod-loop kmod-gpio-button-hotplug kmod-leds-gpio kmod-ledtrig-default-on kmod-ledtrig-netdev kmod-ledtrig-timer kmod-ledtrig-usbdev kmod-lib-crc-ccitt kmod-lib-crc16 kmod-nls-cp437 kmod-nls-iso8859-1 kmod-nls-utf8 kmod-usb-storage kmod-usb-uhci kmod-usb2 kmod-usb-ohci kmod-usb-net kmod-usb-net-cdc-ether kmod-usb-net-rndis kmod-usb-serial kmod-usb-serial-cp210x kmod-usb-serial-option kmod-usb-serial-wwan kmod-usb-acm usb-modeswitch comgt chat luci luci-lib-json luci-lib-nixio uhttpd-mod-lua uhttpd-mod-tls uhttpd-mod-ubus usbutils wget tor tor-geoip tor-resolve tor-gencert" FILES=files/files-tor-ar/
```
If you want to build a Tor firmware for AR300M Nor flash, do this following:
```
make image PROFILE="GL-AR300M" PACKAGES="uhttpd ethtool blkid iwinfo block-mount curl gnupg iw jshn kmod-fs-ext4 kmod-fs-ntfs kmod-fs-vfat kmod-fs-ext4 ntfs-3g kmod-fs-hfs kmod-fs-hfsplus kmod-fs-reiserfs kmod-fuse kmod-loop kmod-gpio-button-hotplug kmod-leds-gpio kmod-ledtrig-default-on kmod-ledtrig-netdev kmod-ledtrig-timer kmod-ledtrig-usbdev kmod-lib-crc-ccitt kmod-lib-crc16 kmod-nls-cp437 kmod-nls-iso8859-1 kmod-nls-utf8 kmod-usb-storage kmod-usb-uhci kmod-usb2 kmod-usb-ohci kmod-usb-net kmod-usb-net-cdc-ether kmod-usb-net-rndis kmod-usb-serial kmod-usb-serial-cp210x kmod-usb-serial-option kmod-usb-serial-wwan kmod-usb-acm usb-modeswitch comgt chat luci luci-lib-json luci-lib-nixio uhttpd-mod-lua uhttpd-mod-tls uhttpd-mod-ubus usbutils wget tor tor-geoip tor-resolve tor-gencert" FILES=files/files-tor-ar/
```

**Current Tor firmware requires the usage of hardware switch, which is not available in MiFi, 6416 and USB150. So the current tor firmware build guide is not applicable.

You can try to test your firmware. You can make more configurations and put them in the files folder to change the default setting of your firmware.

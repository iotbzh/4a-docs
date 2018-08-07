# **Change HAL**

Your HAL are known as json files in 4a, they are stored in
*/usr/libexec/agl/4a-hal*. Unused HAL are stored in
*etc.available/* and used HAL in *etc/*.

To change you HAL, move your current one from *etc/* to *etc.available/*
and your wanted one from *etc.available/* to *etc/*.

Example:

```bash
$ ls etc etc.available/
etc:
hal-4a-csl-cm106-8ch-usb.json

etc.available/:
hal-4a-2ch-generic-usb.json  hal-4a-intel.json			hal-4a-rcar-m3.json
hal-4a-ensoniq.json	     hal-4a-jabra.json			hal-4a-rcar-m3kf.json
hal-4a-intel-minnow.json     hal-4a-m3ulcbkf-radio-to-2ch.json
hal-4a-intel-qemu.json	     hal-4a-raspberry-pi-3.json
$ mv etc/hal-4a-csl-cm106-8ch-usb.json  etc.available/.
$ mv etc.available/hal-4a-2ch-generic-usb.json etc/.
$ ls etc etc.available/
etc:
hal-4a-2ch-generic-usb.json

etc.available/:
hal-4a-csl-cm106-8ch-usb.json  hal-4a-intel.json		  hal-4a-rcar-m3.json
hal-4a-ensoniq.json	       hal-4a-jabra.json		  hal-4a-rcar-m3kf.json
hal-4a-intel-minnow.json       hal-4a-m3ulcbkf-radio-to-2ch.json
hal-4a-intel-qemu.json	       hal-4a-raspberry-pi-3.json
$ sync
$ reboot
```

As you can see in the exemple, I wanted to have *hal-4a-2ch-generic-usb.json*
enabled, so I swapped the hals. After it dont forget to sync and reboot.
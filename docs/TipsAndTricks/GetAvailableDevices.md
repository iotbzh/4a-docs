# **Get available devices**

Here you have two methodes, one using aplay and another using the infoget verb of the
alsacore api.

## **Using aplay**

```bash
$ aplay -l
**** List of PLAYBACK Hardware Devices ****
card 0: Loopback [Loopback], device 0: Loopback PCM [Loopback PCM]
  Subdevices: 8/8
  Subdevice #0: subdevice #0
  Subdevice #1: subdevice #1
  Subdevice #2: subdevice #2
  Subdevice #3: subdevice #3
  Subdevice #4: subdevice #4
  Subdevice #5: subdevice #5
  Subdevice #6: subdevice #6
  Subdevice #7: subdevice #7
card 0: Loopback [Loopback], device 1: Loopback PCM [Loopback PCM]
  Subdevices: 8/8
  Subdevice #0: subdevice #0
  Subdevice #1: subdevice #1
  Subdevice #2: subdevice #2
  Subdevice #3: subdevice #3
  Subdevice #4: subdevice #4
  Subdevice #5: subdevice #5
  Subdevice #6: subdevice #6
  Subdevice #7: subdevice #7
card 1: Intel [HDA Intel], device 0: Generic Analog [Generic Analog]
  Subdevices: 0/1
  Subdevice #0: subdevice #0
```

In this list you get the available devices with their subdivices.

## **Using alsacore api**

```bash
$ 4a-api api alsacore infoget
Detected systemd unit file!
Port detected: 1025
ON-REPLY 1:alsacore/infoget: OK
{
  "response":[
    {
      "devid":"hw:0",
      "name":"Loopback",
      "driver":"Loopback",
      "info":"Loopback 1"
    },
    {
      "devid":"hw:1",
      "name":"HDA Intel",
      "driver":"HDA-Intel",
      "info":"HDA Intel at 0xfebf0000 irq 28"
    }
  ],
  "jtype":"afb-reply",
  "request":{
    "status":"success"
  }
}
```
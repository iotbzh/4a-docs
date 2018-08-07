# **Get HALs status**

```4a-api hals``` gives you the ready-to-use hal(s) on your system.

Following, an example of this command on my system:

```bash
$ 4a-api hals
Detected systemd unit file!
Port detected: 1025
ON-REPLY 1:4a-hal-manager/loaded: OK
{
  "response":[
    "4a-hal-intel-qemu"
  ],
  "jtype":"afb-reply",
  "request":{
    "status":"success",
    "info":"Requested data"
  }
}
```

And now an example when an error happened during service startup:

```bash
Detected systemd unit file!
Port detected: 1025
ON-REPLY 1:4a-hal-manager/loaded: OK
{
  "response":[
  ],
  "jtype":"afb-reply",
  "request":{
    "status":"success",
    "info":"Requested data",
    "uuid":"magic"
  }
}
```

In my case, I have only one hal that can be used.

To get more information about this HAL you can use this command:

```4a-api api <api_name> info```

In this case my api name is "4a-hal-intel-qemu", so the command will be

```bash
$ 4a-api api 4a-hal-intel-qemu info
Detected systemd unit file!
Port detected: 1025
ON-REPLY 1:4a-hal-intel-qemu/info: OK
{
  "response":{
    "streams":[
      {
        "name":"multimedia",
        "cardId":"hw:0,0,2"
      },
      {
        "name":"navigation",
        "cardId":"hw:0,0,3"
      },
      {
        "name":"emergency",
        "cardId":"hw:0,0,4"
      }
    ],
    "playbacks":[
      {
        "name":"playback",
        "mixer-name":"INTEL-QEMU:playback"
      }
    ],
    "captures":[
      {
        "name":"capture",
        "mixer-name":"INTEL-QEMU:capture"
      }
    ]
  },
  "jtype":"afb-reply",
  "request":{
    "status":"success",
    "info":"Requested data"
  }
}
```

>**NOTE** This is usefull for versions before FF.RC3, as you can see here you can get
the cardId that matches with the corresponding role.
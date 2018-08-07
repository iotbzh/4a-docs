# **Check that an api is responding**

You might want to test if an api has not crashed or is running, to do so use the command:

4a-api api <api_name> ping

For exemple :

```bash
$ a4-api api smixer ping
Detected systemd unit file!
Port detected: 1025
ON-REPLY 1:smixer/ping: OK
{
  "response":3,
  "jtype":"afb-reply",
  "request":{
    "status":"success"
  }
}
```

Softmixer is responding !

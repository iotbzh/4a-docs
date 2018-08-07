# **Get roles list**

```4a-api roles``` gives you the list of different roles in a json format.

```bash
$ 4a-api roles
Detected systemd unit file!
Port detected: 1025
ON-REPLY 1:ahl-4a/get_roles: OK
{
  "response":[
    "radio",
    "multimedia",
    "emergency",
    "navigation"
  ],
  "jtype":"afb-reply",
  "request":{
    "status":"success"
  }
}
```

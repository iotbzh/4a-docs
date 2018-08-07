# **Get service status**

4a-status gives you the 4a status.

Here is an example when the service is running fine:

```bash
$ 4a-status
---- Audio cards detected ----
card 0: Loopback
card 1: Intel

---- snd-aloop driver availability ----
SUCCESS: Built into the kernel

---- 4a service status ----
SUCCESS: Service is currently running!
```

And now an example when an error happened during service startup:

```bash
---- Audio cards detected ----
card 0: Loopback
card 1: Intel

---- snd-aloop driver availability ----
SUCCESS: Built into the kernel

---- 4a service status ----
WARNING: Service is not currently running!
It can be started using the following command:
systemctl restart *agl-service-audio-4a*.service

```
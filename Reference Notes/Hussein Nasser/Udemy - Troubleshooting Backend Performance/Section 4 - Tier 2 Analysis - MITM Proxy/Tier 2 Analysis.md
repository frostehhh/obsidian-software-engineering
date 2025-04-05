---
tags:
  - reference-notes
  - backend
  - troubleshooting
---

# MITM Setup
![[Pasted image 20250405181621.png]]
Use a manual proxy set to loopback address and port 8181

> [!note]
> Based on the video, which was done a Mac, we need to set the Web proxy. We can do this in Windows as well. Applications will usually follow the system-configured proxy(excluding curl)


## Extra configuration
Update `listen_port=8181`
`mitmproxy --set listen_port=8181`

## Launching MITM
###### Default
```
mitmproxy
```
###### Verbose
```

```
# Using curl
For windows, use `curl.exe` in Powershell/Command Prompt

###### Client to Server
`curl.exe -x http://localhost:8181 http://localhost:8080`

> [!note]
> -x flag is for setting the proxy

# Tier 2 Analysis
usage of MITM Proxy for intercepting client to server connection.

# References
https://docs.mitmproxy.org/stable/
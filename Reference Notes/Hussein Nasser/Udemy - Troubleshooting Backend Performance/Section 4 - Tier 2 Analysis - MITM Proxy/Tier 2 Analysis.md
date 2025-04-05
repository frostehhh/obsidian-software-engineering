---
tags:
  - reference-notes
  - backend
  - troubleshooting
Draft: true
---

# MITM
## Setup
![[Pasted image 20250405181621.png]]
Use a manual proxy set to loopback address and port 8181

> [!note]
> Based on the video, which was done a Mac, we need to set the Web proxy. We can do this in Windows as well. Applications will usually follow the system-configured proxy(excluding curl)


### Extra configuration
Update `listen_port=8181`
`mitmproxy --set listen_port=8181`

## Launching MITM
###### Default
```
mitmproxy
```

# Using curl
For windows, use `curl.exe` in Powershell/Command Prompt

###### Client to Server
`curl.exe -x http://localhost:8181 http://localhost:8080`

> [!note]
> -x flag is for setting the proxy

# Tier 2 Analysis
Usage of MITM Proxy for intercepting client to server connection.
## Slow processing of requests
![[Pasted image 20250405233525.png]]
## Slow download of response
![[Pasted image 20250405233653.png]]

## Simulate Reverse proxy
```
mitmweb --mode reverse:http://localhost:9002 -p 9000
```
- Can be used to setup a MITM between 2 services
- Make it so that a service will target the proxy that will forward requests to the `-p` port value


> [!NOTE] Title
> Useful for testing services especially when you have no access to the source code

# References
https://docs.mitmproxy.org/stable/
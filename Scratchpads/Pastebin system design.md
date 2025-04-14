https://github.com/donnemartin/system-design-primer/blob/master/solutions/system_design/pastebin/README.md

### Use cases
#### We'll scope the problem to handle only the following use cases
- **User** enters a block of text and gets a randomly generated link
    - Expiration
        - Default setting does not expire
        - Can optionally set a timed expiration
- **User** enters a paste's url and views the contents
- **User** is anonymous
- **Service** tracks analytics of pages
    - Monthly visit stats
- **Service** deletes expired pastes
- **Service** has high availability

#### Out of scope

- **User** registers for an account
    - **User** verifies email
- **User** logs into a registered account
    - **User** edits the document
- **User** can set visibility
- **User** can set the shortlink
### Constraints and assumptions
#### State assumptions

- Traffic is not evenly distributed
- Following a short link should be fast
- Pastes are text only
- Page view analytics do not need to be realtime
- 10 million users
- 10 million paste writes per month
- 100 million paste reads per month
- 10:1 read to write ratio

# Draft

## Paste DB structure
```
short_link varchar[8] 8 bytes
created_at datetime 8 bytes
expires_at datetime 8 bytes null
path text 50 bytes
```

74 bytes per write
content size X

![[Pastebin system design 2025-04-15 01.24.21.excalidraw]]





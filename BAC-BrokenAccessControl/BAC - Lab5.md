# BAC Vulnerability - HTTP Headers


### What is ```X-Original-URL``` && ```X-Rewrite-URL``` Headers

- non-standard HTTP
- These Headers lets users override the path in the request URL via the **X-Original-URL** or **X-Rewrite-URL** HTTP request header and **allows a user to access one URL but have web application return a different one** which can bypass restrictions on higher level caches and web servers.

Checking ```Cookies``` 

![****](/BAC-BrokenAccessControl/Screenshots/bac5.PNG)

![****](/BAC-BrokenAccessControl/Screenshots/bac1-2.PNG)


## Rules

- Some applications enforce access controls at the platform layer by restricting access to specific URLs and HTTP methods based on the user's role. 

```
DENY: POST, /admin/deleteUser, managers
```
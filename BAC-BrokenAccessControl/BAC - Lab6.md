# BAC Vulnerability - HTTP headers


![****](/BAC-BrokenAccessControl/Screenshots/bac6.PNG)

![****](/BAC-BrokenAccessControl/Screenshots/bac1-2.PNG)

```js
GET /admin-roles?username=wiener&action=upgrade HTTP/1.1
```

## Takeaways

- The front-end controls above restrict access based on the URL and HTTP method. Some web sites are tolerant of alternate HTTP request methods when performing an action. 

- Changing the Request method from POST to POSTX && GET, we was able to perform the user upgrade!
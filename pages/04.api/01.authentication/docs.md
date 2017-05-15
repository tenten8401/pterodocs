---
title: Authentication
---

[ui-tabs position="top-left" active="0" theme="lite"]
[ui-tab title="PHP"]
```php
<?php

$public = 'JkAFq7M47kLN0xVD';
$private = 'E6X9FyZvMFeJbqtq.IwjlTuR.MKDoicB';

$url = 'https://pterodactyl.local/api/admin/users';
$body = '';

$hmac = hash_hmac('sha256', $url . $body, $private, true);

return $public . '.' . base64_encode($hmac);

// Should return the string below:
//
// JkAFq7M47kLN0xVD.wgIxj+V8RHgIetcQg2lRM0PRSH/y5M21cPz9zVhfFaQ=
```

[/ui-tab]
[ui-tab title="golang"]
```golang
This is still on progress...
```

[/ui-tab]
[/ui-tabs]
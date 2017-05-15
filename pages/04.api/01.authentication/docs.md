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
[ui-tab title="Second Tab"]

In tempor sed sapien **eu porttitor**. Aliquam cursus facilisis ante. Etiam neque nunc, blandit vel lacus et, faucibus accumsan lacus. Proin posuere varius purus quis faucibus. [Quisque et enim](#) vitae orci placerat tincidunt id ac eros. Fusce et gravida libero. 

Phasellus cursus odio ex, in mattis lorem tincidunt vel. [Donec nibh odio](#), dapibus non ligula a, semper ornare massa. Nulla consectetur eu nunc sed ultrices. Integer at turpis dolor.

[/ui-tab]
[/ui-tabs]
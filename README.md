## CodeIgniter Boilerplate :+1:

This is starter template for codeignter with assets folder, which is holding **css, javascript, images and etc** files.

### Procedure of Creating this Boilerplate

1. Create .htaccess file in the root directory.

2. Add utility_helper.php file to helpers folder.

3. Add url and utility to autoload helper.

4. Add route to access assets folder


### How to access assets folder

We can use `<?php echo asset_url();?>` to access assets folder.


### .htaccess file

```apache
RewriteEngine on
RewriteCond $1 !^(index\.php|assets|fonts|images|js|css|uploads|favicon.png)
RewriteCond %(REQUEST_FILENAME) !-f
RewriteCond %(REQUEST_FILENAME) !-d
RewriteRule ^(.*)$ ./index.php/$1 [L]
```

### utility_helper.php

```php
if(! defined('BASEPATH')) exit ('No direct script access allowed');

if(! function_exists('asset_url()')) {
    function asset_url() {
        return base_url().'assets/';
    }
}
```

### autoload.php
```php
$autoload['helper'] = array('url','utility');
```

### routes.php

```php
$route['assets/(:any)'] = 'assets/$1';
```



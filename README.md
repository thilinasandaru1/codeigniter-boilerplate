## CodeIgniter Boilerplate :+1:

This is starter template for codeignter with assets folder, which is holding **css, javascript, images and etc** files.

### procedure of this Boilerplate

1. Create .htaccess file in the root directory.

2. Add utility_helper.php file to helpers folder.

3. Add url and utility to autoload helper.


### How to access assets folder

We can use `<?php echo asset_url();?>` to access assets folder.


### .htaccess file

```apache
RewriteEngine on
RewriteCond $1 !^(index\.php|assests|images|assets|js|css|uploads|favicon.png)
RewriteCond %(REQUEST_FILENAME) !-f
RewriteCond %(REQUEST_FILENAME) !-d
RewriteRule ^(.*)$ ./index.php/$1 [L]
```

### utility_helper.php

```php
<?php
if(! defined('BASEPATH')) exit ('No direct script access allowed');

if(! function_exists('asset_url()')) {
    function asset_url() {
        return base_url().'assets/';
    }
}
```

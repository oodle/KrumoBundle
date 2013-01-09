KrumoBundle
===========

Hooks for using krumo within Symfony

Krumo is basically a cascading visual var dump tool.  If you don't know what it is, you can peruse some documentation here: http://krumo.sourceforge.net/

Relies on this fork of krumo: https://github.com/oodle/krumo

Installation:
-------------
Add these two lines to your composer.json "require" section:

### composer.json
```json
    "require": {
       ...
       "oodle/krumo": "*",
       "oodle/krumo-bundle": "*"
```

Add this to your AppKernel.php (in the registerBundles() section):

### app/AppKernel.php
```php
new Oodle\KrumoBundle\OodleKrumoBundle()
```

### app/config/routing.yml
```yaml
KrumoBundle:
    resource: "@OodleKrumoBundle/Resources/config/routing/routing.yml"
    prefix:   /
```	

Configuration:
--------------

### config.yml
```yaml
oodle_krumo:
    skin:
        selected: schabalon.com
    css:
        url: /krumo/
    display:
        show_version: true
        show_call_info: true
```

### skin / selected
Skin to use for krumo

### css / url
URL for accessing the krumo assets.  Don't modify unless you know what you are doing

#### display / show_version
Whether or not to show the krumo version (and link back) at the bottom

### display / show_call_info
Whether or not to show the line number / call info at the bottom

Usage:
------

### php
```php
krumo($something); // Dumps krumo output of that variable from that point
```

### twig
```twig
{{ someVar | krumo }}
```
# SimpleSAMLphp basic installation project

This packages create a new SimpleSAMLphp installation based on its latest stable
version.

## Installation with Composer

Just run this to create a new installation:

```console
composer.phar create-project sgomez/simplesamlphp-base simplesamlphp
```

## Configuring simpleSAMLphp

Please, read the [official documentation](https://simplesamlphp.org/docs/stable/).

## Requirements

You need to configure the enviroment variable __SIMPLESAMLPHP_CONFIG_DIR__ with the _/config_
directory path. If you don't do this, simpleSAMLphp will search the config directory inside
_/vendor_. Ex.:

```
SIMPLESAMLPHP_CONFIG_DIR=/var/simplesamlphp/config
```

You will find the usual template folders _config-templates_ and _metadata-templates_ as links
to the original folders (inside vendors). Inside the _config_ folder you can see a 
_config.php.dist_ file. You should use this template to create your own _config.php_ instead
the one inside _config-template_. Basically this file its configured to search the metadata
and other config files from the root installation path instead the vendor simpleSAMLphp
installation. The changes you fill find are:

```php
$config = array(
    //...
    'certdir' => __DIR__.'/../cert/',
    'loggingdir' => __DIR__.'/../var/log/',
    'datadir' => __DIR__.'/../var/data/',
    //...
    'metadata.sources' => array(
        array('type' => 'flatfile', 'directory' => __DIR__ . '/../metadata'),
    ),
    //...
);
```
## Updating simpleSAMLphp

If a new version of simpleSAMLphp is released, all you need to do is this:

```console
composer.phar update
```

You are free to install new simpleSAMLphp modules as usual without restore the
_composer.json_ before updating, because you are using it as a library.


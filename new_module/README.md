# Zend Framework Album Module

This is a sample Album module for use with
[zend-mvc](https://docs.zendframework.com/zend-mvc) applications.

## Installation

First, decide on a namespace for your new module. For purposes of this README,
we will use `Album`.

Clone this repository into your application:

```bash
$ cd module
$ git clone 
$ cd Album
```

If you wish to version the new module with your application, and not as a
separate project, remove the various Git artifacts within it:

```bash
$ rm -Rf .git .gitignore
```

If you want to version it separately, remove the origin remote so you can
specify a new one later:

```bash
$ git remote remove origin
```

The next step will be to change the namespace in the various files. Open each
of `config/module.config.php`, `src/Module.php`, and
`src/Controller/AlbumController.php`, and replace any occurence of
`Album` with your new namespace.

> ### find and remplace
>Remplace Album for you NameModule
>Remplace AlbumController for you NameController
>Remplace name of view's and Name Foldel of Module

Next, we need to setup autoloading in your application. Open the `composer.json`
file in your application root, and add an entry under the `autoload.psr-4` key:

```json
"autoload": {
    "psr-4": {
        "Album\\": "module/Album/src/"
    }
}
```

When done adding the entry:

```bash
$ composer dump-autoload
```

Finally, notify your application of the module. Open
`config/modules.config.php`, and add it to the bottom of the list:

```php
return [
    /* ... */
    'Album',
]
```

> ### application.config.php
>
> If you are using an older version of the Album application, you may not
> have a `modules.config.php` file. If that is the case, open `config/application.config.php`
> instead, and add your module under the `modules` key:
>
> ```php
> 'modules' => [
>     /* ... */
>     'Album',
> ],
> ```

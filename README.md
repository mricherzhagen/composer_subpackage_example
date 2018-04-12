Composer subpackage bug example
===============================


This repository shows a bug in composer.

To reproduce:
```
#Clone repository
rm -rf vendor/ #if exists
git checkout master
composer install # Runs without error
git checkout add_subpackage
composer install # Runs without error, installs subpackage
git checkout master
composer install # Runs without error - does "something"?
git checkout add_subpackage
composer install # Error
```

```
  [RuntimeException]
  Package mricherzagen/composer_subpackage_example_subpackage cannot install to "[...]/composer_subpackage_example/subpackage" inside its source at  "[...]/composer_subpackage_example/subpackage"
```
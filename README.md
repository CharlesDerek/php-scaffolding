# PHP Scaffolding

[![MIT Software License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE.md)

This is a scaffolding for PHP projects using Docker. In this repository you will find:

* Latest `PHP` (currently [7.4](https://en.wikipedia.org/wiki/PHP#Release_history))
* Latest `PHPUnit` (currently [9](https://phpunit.de/announcements/phpunit-9.html))
* PHP style checker (from [FriendsOfPHP](https://github.com/FriendsOfPHP/PHP-CS-Fixer))
* Psalm static analysis tool (from [Vimeo](https://github.com/vimeo/psalm))
* Basic dockerfile ready to use from your `docker-compose.yml`
* Basic structure to start coding in `src` and `tests`

## Custom Installation

### Clone this repository

> git clone https://github.com/Chemaclass/PhpScaffolding YourProjectName

#### Using the installer script to set-up the new project

To run the installation script you will need to have a `PHP 7.1+` in your local:

> php install.php

Using the installer script `install.php` it will replace the Project & Container names
to customized values and prepare everything you need to start working in your project.

#### Installing the dependencies manually

To set up the container and install the composer dependencies:

```bash
docker-compose up -d
docker-compose exec your_project_name composer install
```

### Getting the bash from your project

If you want to go inside the docker container:

```bash
docker exec -ti -u dev your_project_name bash
```

## Composer Scripts

```bash
composer test-all     # run test-quality and test-unit
composer test-quality # run psalm
composer test-unit    # run phpunit

composer psalm  # run Psalm coverage
composer csfix  # run the code fixer (`.php_cs`)
```

## Git hooks

There are some git hooks

* `./tools/scripts/git-hooks/pre-commit.sh`
* `./tools/scripts/git-hooks/pre-push.sh`

In order to create a soft-symlink:

```bash
ln -s tools/scripts/git-hooks/pre-commit.sh .git/hooks/pre-commit
ln -s tools/scripts/git-hooks/pre-push.sh .git/hooks/pre-push
```

## Contributions

Feel free to open any PR with your ideas, suggestions or improvements.

### Installing it locally

```bash
docker-compose up -d
docker-compose exec php_scaffolding composer install
docker exec -ti -u dev php_scaffolding bash
```

Check out your code via the web browser creating a development server:

```
docker-compose exec php_scaffolding php -S 0.0.0.0:8080 public/index.php
```

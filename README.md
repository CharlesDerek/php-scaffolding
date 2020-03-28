# PHP Scaffolding

[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/Chemaclass/php-scaffolding/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/Chemaclass/php-scaffolding/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/Chemaclass/php-scaffolding/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/Chemaclass/php-scaffolding/?branch=master)
[![MIT Software License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE.md)

This is is a scaffolding for PHP projects using Docker. In this repository you will find:

* Latest `PHP` (currently [7.4](https://en.wikipedia.org/wiki/PHP#Release_history))
* Latest `PHPUnit` (currently [9](https://phpunit.de/announcements/phpunit-9.html))
* PHP style checker (from [FriendsOfPHP](https://github.com/FriendsOfPHP/PHP-CS-Fixer))
* Basic dockerfile ready to use from your `docker-compose.yml`
* Basic structure to start coding in `src` and `tests`
* Some make tasks to execute commands inside the docker container such:
  * `make bash` -> access into the bash
  * `make csfix` -> run the code style fixer (`.php_cs`)
  * `make composer ARGS="require phpunit/phpunit"` -> run composer
  * `make tests ARGS="tests/DomainTests/Unit/AnyLogicTest"` -> run PHPUnit

## Requirements

* GNU Make 4.3 (for Makefile)
 [Install for Mac](https://stackoverflow.com/questions/43175529/updating-make-version-4-1-on-mac) | Optional

## Installation

1. Clone (or fork) this repository
2. Modify the [dockerfile](devops/dev/php.dockerfile) in order to adjust the `WORKDIR` to your needs
   * Update the [docker-compose.yml](docker-compose.yml) file (`container_name` and `volumes` values)
3. Build & start the image using `docker-compose up`
4. Install the dependencies
   1. Go inside the image and run: `composer install`
   2. or just from your local: `make composer ARGS="install"`

## Contributions

Feel free to open any PR with your suggestions or improvements.

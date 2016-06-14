Yo! Symfony dev machine
-----------------------
* OS: Ubuntu Trusty Tahr (14.0.4) 64 bits.
* Hostname: yosymfony-dev (http://192.168.33.99/).
* Shared folder (Vbox default) inside VM: `/vagrant`.

This VM has been created using [Phansible](http://phansible.com/).

## Require

* VirtualBox >= 4.3.x
* Vagrant >= 1.7.4

## Included software

* PHP 5.6 (php5-cli, php5-intl, php5-mcrypt, php5-curl)
* Xdebug.
* Blackfire.
* MongoDB.
* MariaDB.
* Sqlite.
* NodeJS with NPM.
* [Git](https://git-scm.com/) 1.9.1
* [Composer](https://getcomposer.org/).
* [PHPUnit](https://phpunit.de/).
* [PHP-CS fixer](http://cs.sensiolabs.org/).
* [Phing](https://www.phing.info/).
* [Git Subsplit](https://github.com/dflydev/git-subsplit).
* [PHP Git Hooks](https://github.com/intaro/php-git-hooks.git) cloned at `/vagrant/infrastructure/php-git-hooks`.

## How to install the VM?

```bash
$ git clone https://github.com/yosymfony/Dev-machine.git
$ cd Dev-machine/
$ vagrant up
```

## Bash aliases

Bash aliases used for provisioning the VM are detailed at `./ansible/roles/tasks/templates/.bash_aliases.tpl`.

Yo! Symfony dev machine
-----------------------
* OS: Ubuntu Trusty Tahr (14.0.4) 64 bits.
* Hostname: yosymfony-dev (http://192.168.33.99/).
* Shared folder (Vbox default) inside VM: `/vagrant`.

This VM runs on any Linux, Mac or Windows system and has been
created using [Phansible](http://phansible.com/).

## Require

* VirtualBox >= 4.3.x
* Vagrant >= 1.7.4

**Note**: If you are using Windows, you may need to enable hardware virtualization (VT-x).
It can usually be enabled via your BIOS. If you are using Hyper-V on a UEFI system you
may additionally need to disable Hyper-V in order to access VT-x.

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
* [Git Subsplit](https://github.com/dflydev/git-subsplit) cloned at `/vagrant/infrastructure/git-subsplit`.
* [PHP Git Hooks](https://github.com/intaro/php-git-hooks.git) cloned at `/vagrant/infrastructure/php-git-hooks`.

## How to install the VM?

```bash
$ git clone https://github.com/yosymfony/Dev-machine.git
$ cd Dev-machine/
$ vagrant up
```

### dotfiles
This VM contains a set of predefined dotfiles (`.bash_aliases`, `.bashrc` and `.gitconfig`)
that will be copied during initial startup. They are located at `./ansible/roles/tasks/templates/`.

## PHP Git Hooks installation
The Git pre-commit hooks for applying in the local repository of the PHP project.
Open a ssh session with `vagrant ssh` and go to `/vagrant/infrastructure/php-git-hooks`.
Then install its dependencies runing `composer install` command.
Finally, you only need to make a symbolic link to the `pre-commit` file in your PHP project:

```bash
$ cd some/php/project/.git/hooks
ln -s /vagrant/infrastructure/php-git-hooks/pre-commit pre-commit
```

**Note that in Windows system you'll get an error** bacause the host filesystem
doesn't support for symbolic links. Check [Stackoverflow](http://stackoverflow.com/questions/17895256/creating-symbolic-link-protocol-error).

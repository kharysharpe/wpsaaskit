# Experimental 

WP SaaS Kit is built upon Bedrock. Designed to take care of the essential pieces of running a SaaS business.

## Use Cases

* Marketing Site Management
* Registration
* User Management
* Subscription Management
* Access Control

## Wordpress Plugins

* Tailor Page Builder
* Easy Pricing Pages
* Simple Membership
* User Role Editor
* Herbert Framework

## WebApp Packages

* Herbert (getherbert/framework)
* Laravel Blade Template Engine (jenssegers/blade)
* Valitron (vlucas/valitron)
* Monlolog (monolog/monolog)


## Features

* Better folder structure
* Dependency management with [Composer](http://getcomposer.org)
* Easy WordPress configuration with environment specific files
* Environment variables with [Dotenv](https://github.com/vlucas/phpdotenv)
* Autoloader for mu-plugins (use regular plugins as mu-plugins)
* Enhanced security (separated web root and secure passwords with [wp-password-bcrypt](https://github.com/roots/wp-password-bcrypt))

Use [Trellis](https://github.com/roots/trellis) for additional features:

* Easy development environments with [Vagrant](http://www.vagrantup.com/)
* Easy server provisioning with [Ansible](http://www.ansible.com/) (Ubuntu 14.04, PHP 7, MariaDB)
* One-command deploys


## System Requirements

* PHP >= 7.0
* Composer - [Install](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)

## Wordpress Installation

1. Install required files 

  `composer install`

2. Copy `.env.example` to `.env` and update environment variables:
  * `DB_NAME` - Database name
  * `DB_USER` - Database user
  * `DB_PASSWORD` - Database password
  * `DB_HOST` - Database host
  * `WP_ENV` - Set to environment (`development`, `staging`, `production`)
  * `WP_HOME` - Full URL to WordPress home (http://example.com)
  * `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
  * `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT`

  If you want to automatically generate the security keys (assuming you have wp-cli installed locally) you can use the very handy [wp-cli-dotenv-command][wp-cli-dotenv]:

      wp package install aaemnnosttv/wp-cli-dotenv-command

      wp dotenv salts regenerate

  Or, you can cut and paste from the [Roots WordPress Salt Generator][roots-wp-salt].

3. Add theme(s) in `public/app/themes` as you would for a normal WordPress site.

4. Set your site vhost document root to `/path/to/site/public/` (`/path/to/site/current/public/` if using deploys)

5. Access WP admin at `http://example.com/wp/wp-admin`

## Deploys

There are two methods to deploy Bedrock sites out of the box:

* [Trellis](https://github.com/roots/trellis)
* [bedrock-capistrano](https://github.com/roots/bedrock-capistrano)

Any other deployment method can be used as well with one requirement:

`composer install` must be run as part of the deploy process.

## Web App Installation

1. cd public/app/plugins/webapp

2. composer install

3. Login to wordpress and activate WebApp plugin



## Documentation

TODO

## Contributing

TODO

## TODO

* Find a Team Management (sub accounts) plugin.
* Enforce PHP 7
* Look at using AdminLTE for WebApp
* Write CRUD for WebApp


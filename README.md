# How to use the drw-framework
## The full meaning of drw is Don’t Reinvent the Wheel
# Requirements:
*	PHP7.2
*	Gitbash
*	Curl(Windows users, should come with gitbash, if not install)

## Packages (that come with drw or you can install from cli):
### Asterisks packages are preinstall packages 
*	PHPUnit*
*	Marpher*
*	Peterkahl/universal-php-mailer*
*	Matthiasmullie/scrapbook*
*	Phing*
*	Brandonwambolt/utilphp*
*	Psy/psysh*
*	Phplint*
*	Xdebug
*	Jenkins
*	Gearman
*	Redis
*	Varnish
*	Memcached

## What set the framework apart:
With this framework, you can install memcached, redis, varnish, xdebug, phpsh, Jenkins, gearman etc with just a command.
## Supported OS:
This framework does not support all OS available in the world for the installation of the packages mentioned above(I don’t think it is possible to see a program that will support every OSs in the world) but it does have support for some major OSs.

The supported Oss are Windows, mac OS, Linux ->Ubuntu, Debian, fedora, redhat, centOS, Open BSD, free BSD.
### What does that mean:
It means  to install memcached  for example, if you are any of the above OS user, all what you need to do is run php dry cache:memcache and the magic begins as the framework will detect the kind of OS you are using and if it is part of the supported Oss, it will download memcached for php, extract it to php/ext folder, install it, update php.ini file,  download memcached, extract it(if necessary), install it and start it.
### Note:
I only tried them on windows 8.1 and it worked perfectly. Then how did I know or write the code for others(Linux, mac OS etc)? Well, I followed either the package protocol of installation on each specific platform or follow the platform protocol of installing packages e.g. on Open BSD, I mostly use pkg_add and the package name. 
## Usage:
Like most of the frameworks, drw framework also comes with a scaffold. 
## What does that mean:
It means you can easily start building with some infrastructures on ground for you.
### Generating a scaffold:
To generate a scaffold, open `gitbash` and type `php dry generate:scaffold `(dry means Don’t Repeat Yourself)
### Creating a controller:
To create a controller, type `php dry create:controller`
### Creating an api controller:
Type `php dry create:api`
### Creating a controller with parameter:
As of now, the only supported parameter is the `--api` that will be used to generate the api with the same name
### Creating a model:
You can only generate a model class (as at now) through the `db` command
### Creating a db table:
Type `php dry create:table  tablename(assuming you have created a db)` column(for the column use spaces to separate the field)
e.g. `php dry create:table apple “name s: (50) nn:” “type string: (100) nn:”`.
The above command will create a table named apple, with the following columns, `name varchar(50) not null,`
`Type varchar(100) not null`.
A model class names Apple will be generated (noticed that the “a” is now capitalized)
### Creating a controller with the same name as db table and model:
Type php dry create:table tablename  column –controller
### Creating a db:
Type `php dry create:db database name`
The `create:db` also come with 2 parameters and they are the `--user` and `--pw` used for creating a user and password. If not provided, a default one will be created with value of `secret` for both options
Reversing the command:
E.g. delete a db use, `php dry destroy:db dbname`.
All the above command have their respective destroy command.

## Installing Packages:
This are the packages you can install from the command line using drw framework. XDebug, Jenkins, Memcached, Redis, Gearman, Varnish.

## Cache:
To install memchached, Redis or Varnish, use php dry install:cache-package name e.g. `php dry install:cache-redis` to install redis
## Debugger:
To install XDebugger, use `php dry install:debugger xdebug`
## Continuous Intergration (ci):
To install Jenkins use `php dry install:ci-jenkins`

## Generating the site url
To generate the site urls use `php dry generate:route`. This command will craw your controller to generate the site url

## Framework structure:
There are 6 folders in the root file and they are
*	App
	* Controllers
	* Templates(view)
	* Model
*	Assets
*	Config
*	Db
*	Public
*	Storage

### NB: More still to come on the project.
* Validating and sanitizing
* Adding more to the app folder like mail, notifications etc
* Request and response
* Middleware etc.

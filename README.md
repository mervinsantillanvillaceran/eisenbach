# Project Test #

### What is this repository for? ###

* Eisenbackh Consulting Project Test

### How do I get set up?

* Clone this repo
* Run `npm i` and `composer install`
* Build project `npm run dev`
* Copy `.env-example` to `.env` for environment configuration
* Change `config/database.php` file - default value to `mysql` or any database you are using (I used pgsql just for heroku)
* Run `php artisan key:generate`
* Migrate database `php artisan migrate`
* Run php server `php artisan serve`
* To build for production, just run `npm run prod`

### API

* `/api/users` - List of all users
* `/api/user/{id}` - User details

### Who do I talk to? ###

* Mervin Villaceran

# Console Commands for Vue.js:

### How to create a Vite-Vue project:

`npm create vite@latest project-name -- --template vue`

### General package installation:

`npm i`

### Start the development server:

`npm run dev`

### How to install Sass:

`npm i -D sass`

### How to install Axios:

`npm i axios`

### How to install Bootstrap:

`npm i bootstrap` -> import Bootstrap in `main.js` -> (see below)

```javascript
import "bootstrap/dist/css/bootstrap.min.css";

// If you use SCSS, also import
("bootstrap/dist/scss/bootstrap.min.scss");
```

### How to install FontAwesome:

`npm i --save @fortawesome/fontawesome-svg-core`

`npm i --save @fortawesome/free-solid-svg-icons`  
`npm i --save @fortawesome/free-regular-svg-icons`  
`npm i --save @fortawesome/free-brands-svg-icons`  
(the last three lines depend on the icons you need)

`npm i --save @fortawesome/vue-fontawesome@latest-3`

```javascript
import { library } from "@fortawesome/fontawesome-svg-core";
import { FaUser as ExampleFaUser } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(ExampleFaUser);

// Between createApp and mount
app.component("FontAwesomeIcon", FontAwesomeIcon);
```

### How to install Vue Router:

`npm i vue-router@4`

<div style="margin-top: 70px;"></div>

# Console Commands for Laravel:

### Install Laravel:

`composer create-project laravel/laravel:^10 project-name`  
(version number = Laravel version)

### Install general dependencies:

`composer i`

### Install specific libraries:

`composer require LibraryName`

### How to start a Laravel server:

`php artisan serve` OR `php -S localhost:8000 -t public`  
`npm run dev`

### How to remove Tailwind and add Bootstrap:

`composer require pacificdev/laravel_9_preset`  
`php artisan preset:ui bootstrap`  
`npm i`  
Remove the line (type: 'module', line 3) in `package.json`  
Add the following to `app.scss`

```javascript
@import '~bootstrap/scss/bootstrap';

// Add the following in the input object in `app.js`
'resources/scss/app.scss', 'resources/js/app.js',

// In the general layout, add in the head
@vite(['resources/js/app.js'])
```

`npm run dev`

### How to create a model:

`php artisan make:model ModelName`
If you want to add options, append `-rmsf` indicating which ones with the letters:

- r = resource
- m = migration
- s = seeder
- f = factory

### How to create a migration:

`php artisan make:migration create_example_table`

### How to interact with the database:

`php artisan migrate`  
This command reads migrations and creates the database if it doesn’t exist.

### How to refresh the database:

`php artisan migrate:refresh`
To seed the database along with the refresh, add `--seed` at the end.

### How to rollback the database:

`php artisan migrate:rollback`

### How to reset the database:

`php artisan migrate:reset`

### How to create a seeder:

`php artisan make:seeder ModelNameSeeder`
To directly import the model into the seeder, append:  
`--model=ModelName`

Then, call the seeder in `DatabaseSeeder`.

### How to seed the database:

`php artisan db:seed`

### How to create a factory:

`php artisan make:factory ModelNameFactory`
To directly import the model into the factory, append:  
`--model=ModelName`

### How to create a controller:

`php artisan make:controller ModelNameController`
For a pre-configured resource controller, append `-r`  
`r = resource`

### How to install Laravel Breeze (Laravel with authentication):

`composer require laravel/breeze --dev`  
`php artisan breeze:install`  
`composer require pacificdev/laravel_9_preset` (do not change the 9)  
`php artisan preset:ui bootstrap --auth`  
`npm i`  
`npm run dev`

### How to create views:

`php artisan make:view ViewName`
To create a folder along with the view, specify the folder name followed by a dot and the view name.

### How to create CRUD views with one command:

`composer require lanciweb/laravel-make-view`  
`php artisan make:view ModelName --crud`

### How to link storage (for using assets):

Set `FILESYSTEM_DISK = public`  
Edit `filesystems.php` at line 16:

```php
 'default' => env('FILESYSTEM_DISK', 'public')
```

`php artisan storage:link`

### How to create an API controller:

`php artisan make:controller Api/ModelNameController --api`  
`--model=ModelName`

### How to list all routes created:

`php artisan route:list`
To filter, append `--path=api`

### How to create a mail:

`php artisan make:mail CustomMailName`  
`php artisan make:view mails.contacts.message`

---

# Laravel 5 Portugal Cities

Laravel Portufal Cities is a bundle for Laravel.

**Please note that the dev-master version is for Laravel 5 only**

## Installation

Run `composer require renshipt/laravel-portugal-cities dev-master` in your Laravel root directory to install the latest version.

Or add `renshipt/laravel-portugal-cities` to `composer.json`.

    "renshipt/laravel-portugal-cities": "dev-master"

Run `composer update` to pull down the latest version of City List.

Edit `app/config/app.php` and add the `provider` and `filter`

    'providers' => [
        Renshipt\Cities\CitiesServiceProvider::class,
    ]

Now add the alias.

    'aliases' => [
        'Cities' => Renshipt\Cities\CitiesFacade::class,
    ]


## Model

You can start by publishing the configuration. This is an optional step, it contains the table name and does not need to be altered. If the default name `cities` suits you, leave it. Otherwise run the following command

    $ php artisan vendor:publish

Next generate the migration file:

    $ php artisan cities:migration

It will generate the `<timestamp>_setup_cities_table.php` migration and the `CitiesSeeder.php` seeder. To make sure the data is seeded insert the following code in the `seeds/DatabaseSeeder.php`

    //Seed the cities
    $this->call('CitiesSeeder');
    $this->command->info('Seeded the cities!');

You may now run it with the artisan migrate command:

    $ php artisan migrate --seed

After running this command the filled cities table will be available

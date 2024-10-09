# Country Phone Codes Migration and Seeder

This repository includes migrations and seeders for managing country phone codes in a Laravel application. The purpose of this data is to provide a reference for country names along with their respective international dialing codes.

## Table of Contents

- [Installation](#installation)
- [Migrations](#migrations)
- [Seeders](#seeders)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```

2. Install the dependencies:
    ```bash
    composer install
    ```

3. Set up your `.env` file:
    ```bash
    cp .env.example .env
    php artisan key:generate
    ```

4. Update your database configuration in the `.env` file.

5. Run the migrations:
    ```bash
    php artisan migrate
    ```

6. Seed the database with country phone codes:
    ```bash
    php artisan db:seed --class=CountryPhoneCodesSeeder
    ```

## Migrations

### Country Phone Codes Migration

- **Migration Filename**: `xxxx_xx_xx_xxxxxx_create_country_phone_codes_table.php`
- **Description**: This migration creates the `country_phone_codes` table with the following fields:
    - `id`: Primary key.
    - `country_name`: Name of the country.
    - `code`: International dialing code for the country.
    - `timestamps`: Created and updated timestamps.

### Migration Example
```php
Schema::create('country_phone_codes', function (Blueprint $table) {
    $table->id();
    $table->string('country_name');
    $table->string('code');
    $table->timestamps();
});
```

## Seeders

### Country Phone Codes Seeder

- **Seeder Filename**: `CountryPhoneCodesSeeder.php`
- **Description**: This seeder populates the `country_phone_codes` table with data for various countries and their corresponding phone codes.

### Seeder Example
```php
public function run()
{
    DB::table('country_phone_codes')->insert([
        ['country_name' => 'United States', 'code' => '+1'],
        ['country_name' => 'United Kingdom', 'code' => '+44'],
        // Add other countries...
    ]);
}
```

## Usage

Once the migrations and seeders have been run, you can access the `country_phone_codes` table in your database. This data can be used in forms for validating user input, displaying dropdown lists for country selection, or any other functionality requiring country code references.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue if you have any suggestions or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
```

Feel free to replace placeholders like `<repository-url>` and `<repository-name>` with your actual repository details, and modify any sections to better fit your project!

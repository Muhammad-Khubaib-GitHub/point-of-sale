# Laravel Project

This project is built using **Laravel**. Below is the complete list of commands to set up, run locally, and expose the project using **ngrok**
**100 % working module's**, POS, Customer's, Orders, Inventory, Report's and Analytics, DB Backup, Permissions Module etc.

- **PHP**      `=> 8.1`
- **Laravel**  `=> 10.0`

---

## 🔥 How to Get Started


#### 1. Clone repository
```bash
git clone https://github.com/Muhammad-Khubaib-GitHub/point-of-sale.git
cd point-of-sale
```

#### 2. Set Up the Project

Once you’ve cloned the repository, navigate to the project directory and install dependencies:

```bash
cd point-of-sale
composer install
```

Open the project in your preferred code editor:

```bash
code .
```

#### 3. Configure the Environment

Rename the `.env.example` file to `.env`:

```bash
cp .env.example .env
```

Generate the application key:

```bash
php artisan key:generate
```

#### 4. Set Faker Locale (Optional)

To set the Faker locale, add the following line at the end of your `.env` file:

```bash
FAKER_LOCALE="id_ID"
```

#### 5. Set Up the Database

Configure your database credentials in the `.env` file.

#### 6. Seed the Database

Run the following command to migrate and seed the database:

```bash
php artisan migrate:fresh --seed
```

**Note**: If you encounter any errors, try rerunning the command.

#### 7. Create Storage Link

Create a symbolic link for storage:

```bash
php artisan storage:link
```

#### 8. Start the Server

To run the application locally, start the Laravel development server:

```bash
php artisan serve
```

#### 9. Log In

Use the following credentials to log in:

- **Username**: `admin`
- **Password**: `password`


## 🚀 Configuration

#### 1. Configure Cart Settings

Open the `./config/cart.php` file to configure settings like tax rates, number formats, and more.

For more details, check out the [hardevine/shoppingcart documentation](https://packagist.org/packages/hardevine/shoppingcart).



## Set up Ngrok for Remote Access `( Optional )`

#### 1. Install 
Download zipfile for windows and extract and execute it. 

#### 2. After Execution of the ngrok 
Terminal is open for ngrok


#### 3. Stop and run your project

```bash
php artisan serve --port=8000
```

#### 4. Expose project with ngrok
```bash
ngrok http 8000
```

#### 5. Update the `.env` file with ngrok url with
Example
```
APP_URL = https://unpredaceous-diamond-nonmedically.ngrok-free.dev
```

#### 6. Update `Service Provider ` file
```
App\Providers\AppServiceProvider

in boot method 

    if ($this->app->environment('local')) {
        // Always force https when using ngrok
        URL::forceScheme('https');
    }
```

#### 7. Update `Trusted Proxies` file 
Add or update propertie
```
protected $proxies = '*'; // Trust all proxies (ngrok included)

```

#### 8. Clear Config 

Clear application cache
```
php artisan cache:clear
```

Clear config cache
```
php artisan config:clear
```

Cache config
```
php artisan config:cache
```



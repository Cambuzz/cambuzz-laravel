# cambuzz-laravel
Prerequisites for setup : LAMP Stack and phpmyadmin

Clone the repository in /var/www/html folder.

#Installing composer:

curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer

# Giving proper permissions.

sudo chown -R www-data.www-data /var/www/html/cambuzz-laravel
sudo chown -R www-data:www-data 
/var/www/html/cambuzz-laravel/app/storage
chmod -R 755 /var/www/html/cambuzz-laravel
chmod -R 777 /var/www/html/cambuzz-laravel/app/storage


sudo composer update --no-scripts 



#Generating the app key:

php artisan key:generate
Sample output: 
Application key [zQ3lypUtSHrlYVdpxj0YZpvl0x53Yl43] set successfully.

Add the obtained app key into .env file.

sample .env file
APP_KEY = zQ3lypUtSHrlYVdpxj0YZpvl0x53Yl43

Export cambuzz.sql file.
Setup your config/app/database.php

# cambuzz-laravel
Prerequisites for setup : [LAMP Stack](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-14-04) and [phpmyadmin](https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-phpmyadmin-on-ubuntu-14-04)

Clone the repository in /var/www/html folder.

#Installing composer:

```
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
```

# Giving proper permissions.
```
sudo chown -R www-data.www-data /var/www/html/cambuzz-laravel
sudo chown -R www-data:www-data /var/www/html/cambuzz-laravel/app/storage
chmod -R 755 /var/www/html/cambuzz-laravel
chmod -R 777 /var/www/html/cambuzz-laravel/app/storage
```

`sudo composer update --no-scripts` 



#Generating the app key:

`php artisan key:generate`
Sample output: 
Application key [zQ3lypUtSHrlYVdpxj0YZpvl0x53Yl43] set successfully.

Add the obtained app key into .env file.

sample .env file
APP_KEY = zQ3lypUtSHrlYVdpxj0YZpvl0x53Yl43

#Removing index.html from the url

`sudo vim /etc/apache2/apache2.conf`
Change Allow none to Allow all in <Directory />

Enable rewrite module in apache
`sudo a2enmod rewrite`

Restart the server
`sudo service apache2 restart`

Export cambuzz.sql file.
Setup your config/app/database.php

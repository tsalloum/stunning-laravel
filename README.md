sudo apt-get install apache2
sudo apt-get install mysql-server
sudo apt-get install php-mysql
sudo apt-get install php
sudo apt-get install libapache2-mod-php
sudo apt-get install php-mcrypt
sudo apt-get install php-pear
sudo apt-get install curl
sudo apt-get install php-curl
sudo apt-get install php-cli
sudo apt-get install git

cd /var/www/html
pwd
sudo git clone https://github.com/tsalloum/stunning-laravel

curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
cd stunning-laravel/
sudo composer install

pwd
sudo cp .env.example .env
sudo vim .env
sudo php artisan key:generate

apache2 -v
which apache2
cd /usr/sbin
ls
cd /etc/apache2
sudo vim apache2.conf
cd sites-enabled
sudo vim 000-default.conf
sudo systemctl restart apache2

cd /var/www/html/stunning-laravel
sudo chgrp -R www-data storage bootstrap/cache
sudo chmod -R ug+rwx storage bootstrap/cache

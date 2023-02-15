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

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

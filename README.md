# laravel 12 + Breeze + Rreact

- Project Laravel Breeze React

# Update DDEV
- brew upgrade ddev
- ddev poweroff
- ddev start

# Start Docker

- ddev config --project-type=laravel --docroot=public

- Edit .ddev/config.yaml

- ddev start

- ddev describe
- - https://laravel.ddev.site 

- Move the .git folder to .ddev/git folder

- ddev composer create laravel/laravel .
- ddev composer require laravel/breeze --dev
- ddev artisan breeze:install react
- ddev npm install
- ddev npm run dev
- ddev artisan migrate:fresh

- Move back the .git folder to the ./

- ddev npm install @mui/material @emotion/react @emotion/styled
- ddev npm install @mui/icons-material
- ddev npm install @mui/x-data-grid
- ddev npm install @mui/x-date-pickers
- ddev npm install dayjs

# laravel 11 + Breeze + Rreact

- mkdir laravel11

- ddev config
- ddev start
- Edit .ddev/config.yaml

name: laravel11
type: php
docroot: public
php_version: "8.2"
webserver_type: apache-fpm
router_http_port: "80"
router_https_port: "443"
use_https: true
xdebug_enabled: false
additional_hostnames: []
additional_fqdns: []
database:
    type: mariadb
    version: "10.11"
use_dns_when_possible: true
composer_version: "2"
web_environment: []
corepack_enable: false
nodejs_version: "20.13.1"
web_extra_exposed_ports:
  - name: vite
    container_port: 5173
    http_port: 5172
    https_port: 5173

- ddev composer create laravel/laravel:^11.0 .

- Edit .env file

APP_NAME=Laravel
APP_URL=https://laravel11.ddev.site

DB_CONNECTION=mysql
DB_HOST=ddev-laravel11-db
DB_PORT=3306
DB_DATABASE=db
DB_USERNAME=root
DB_PASSWORD=root

- ddev exec php artisan migrate:fresh
- ddev exec php artisan db:seed

- ddev composer require laravel/breeze --dev
- ddev exec artisan breeze:install react

- ddev npm install @mui/material @emotion/react @emotion/styled
- ddev npm install @mui/icons-material
- ddev npm install @mui/x-data-grid
- ddev npm install @mui/x-date-pickers
- ddev npm install dayjs

- Edit vite.config.js

    server: {
        host: '0.0.0.0',
        port: 5173,
        strictPort: true,
        origin: 'https://laravel11.ddev.site:5173',
        cors: true,
        hmr: {
            protocol: 'wss',
            host: 'laravel11.ddev.site',
            clientPort: 5173,
        },
    },

- ddev exec npm run dev

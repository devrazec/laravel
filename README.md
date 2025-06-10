# laravel-breeze-react

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



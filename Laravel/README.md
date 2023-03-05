# **Lession 1**

### Setup environment for Laravel 9.x version


## **Requirements & Tools**
- **PHP** version **8.0+**.
- PHP **Composer**.
- **Webserver** Nginx.
- **MySQL 5.7+ / MariaDB 10.3+ / PostgreSQL 10.0+**...
- DB UI management **Adminer**.

## Setup
**Step1** : Create **Dockerfile**
+ Use docker image config for **Dockerfile**
+ Install **PHP Composer**
+ Copy root folder data to **WORKDIR**

**Step2** : Create **.env** and **.dockerignore**

**Step3** : Create **docker-compose.yml**
+ Webserver **Ngimx** service.
+ **Mysql** database service.
+ **Adminer** DB UI management service.

**Step4** : Create **.docker** folder, store db data and services config files
+ config webserver nginx.
+ create folder for database mount volumn data.
   
**Step5** : Run project
+ Clone source code.
+ Copy **.env** file:
    ```
    cp .env.example .env
    ```
   Change code in **.env** file:

    ```
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=laravel
    DB_USERNAME=laraveluser
    DB_PASSWORD=laraveluserpass

    APP_PORT=4444
    ADMINER_PORT=8080
    ```
+ Run docker build:
    ```
    docker-compose up -d --build
    ```
+ Run composer install:
  ```
  docker-compose exec php composer install
  ```
+ Generate key:
  ```
  docker-compose exec php artisan key:generate
  ```

**Step6** :
+ Project address:
    ```
    http://localhost:4444/
+ Database management address:
    ```
    http://localhost:8080/
    ```
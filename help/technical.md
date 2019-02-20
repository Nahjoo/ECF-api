# Ecf-api-admin
    project was made with symfony 4.2

## Install

### Pré-requisite

    * composer
    * symfony 4.2
    * php 7.2


### Installation guide


    * Clone this repository


    In the .env file, modify
    DATABASE_URL=mysql://username:password@127.0.0.1:3306/ecf_api_admin


    don't forget to change username and password with your phpmyadmin access
    port 3306 for mysql
    in windows : mariadb default used so the port 3307 will be used


    * When it's done, open a terminal then type
    composer install


    * then:
        > php bin/console do:da:cr


    * then:
        > php bin/console make:migration


    * finally:
        > php bin/console do:mi:mi



### Admin password


    Open a terminal:
        > php bin/console security:encode-password


    Type the password you want, the tool will encode it, you will only have to copy the new code displayed


    To modify the admin passwordof the api go in the file config/packages/security.yml


    Paste the new code
    **providers:
        in_memory:
            memory:
                users:
                    admin:
                        password: PASTE HERE
                        roles: 'ROLE_ADMIN'**


    Now, when you will go in the admin interface you will be invited to enter your username and password if you want to continue



### Functionnal Tests


    Generate the functionnal test template
    php bin/console make:functional-test


#### install
    composer require --dev symfony/phpunit-bridge


    then
    composer require --dev symfony/browser-kit symfony/css-selector


    to launch it:
    php bin/phpunit
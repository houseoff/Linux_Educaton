# Запуск веб-приложения из контейнера

Установка Docker

    $ sudo apt install docker-compose docker

Просмотр запущенных контейнеров

    $ sudo docker ps

Просмотр всех контейнеров

    $ sudo docker ps -a

Просмотр всех образов

    $ sudo docker images

Поиск образа Nginx в Docker

    $ sudo docker search nginx

Добавление образа Nginx

    $ sudo docker pull nginx

Запуск контейнера Nginx с параметрами

    $ sudo docker run --name my_nginx -p 80:80 -d -v /var/www/html:/usr/share/nginx/html --restart always nginx

Параметры:
- --name - имя контейнера
- -p - указывается перенаправление портов. Подключение к основной ОС по 80 порту передаётся контейнеру на 80 порт
- -d - запуск в режиме демона (работа в фоновом режиме)
- -v - подключение раздела: раздел основной ОС передаётся контейнеру
- --restart - политики рестарта в случае "падения" контейнера

Остановка работы контейнера

    $ sudo docker stop my_nginx

Удаление контейнера

    $ sudo docker rm my_nginx

Удаление образа

    $ sudo docker rmi nginx

Развертывание WordPress с помощью Docker Compose: 
https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-with-docker-compose
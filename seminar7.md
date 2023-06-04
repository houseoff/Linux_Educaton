# Настройка Nginx

**sudo apt install nginx** - установка nginx

**sudo service nginx stop** - остановка сервиса

**sudo service nginx start** - старт сервиса

**sudo service nginx status** - просмотр статуса

**sudo service nginx restart** - перезапуск сервиса

Конфиги nginx лежат в каталоге /etc/nginx/. Главный конф. файл nginx.conf

**sudo apt install apache2** - установка apache2

Проксирование запроса

![proxy](/img/proxy.png "Проксирование запроса")

Что происходит? У нас установлено два сервера: apache и nginx. Если nginx принимает URL адрес, в котором нет прямой ссылки на файл, удовлетворяющий регулярному выражению во втором location, то запрос отправляется на обработку apache. В противном случае nginx обработает запрос самостоятельно

**sudo apt install mysql-server** - установка mysql server


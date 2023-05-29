# Подключение сторонних репозиториев, ручная установка пакетов

## Установка пакетов deb из репозиториев. Работа с apt

Обновить все установленные пакеты

    sudo apt update && sudo apt upgrade -y

Ключ -y отвечает на все запросы команды apt "Да"

Открывает файл sources.list, в котором хранятся источники для получения пакетов менеджером apt

    sudo appt edit-sources

Файл sources.list находится по пути /etc/apt/sourses.list. В директории /etc/apt также находится директория sources.list.d, в которой хранятся пользовательские файлы источников пакетов

Создаем файл my_vbox_repo.list в директории /etc/apt/sources.list.d со следующим содержимым

    deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtual-box-2016.gpg] https://download.virtualbox.org/virtualbox/debian jammy contrib

deb - формат пакета. deb - для семейтсва Debian
arch - архитектура процессора
signed-by - файл подписи пакета. Без данного файла пакет работать не будет. На сайте загрузки Oracle Virtual Box имеется доп. информация об установке данного ключа, если по какой-то причине он не установился вместе с пакетом
jammy - кодовое название ОС. Инфу о системе можно посмотреть с помощью screenfetch (sudo apt install screenfetch)

После добавления нового репо необходимо выполнить команду

    sudo apt update

Для удаления своего репо необходимо удалить файл my_vbox_repo.list и после выполнить команду sudo apt update

    sudo rm /etc/apt/sources.list.d/my_vbox_repo.list
    sudo apt update
---
## Подключение PPA-репозитория

PPA-репозиторий - это облачное хранилище собственных репозиториев. На серверах Ubuntu выделяется место под Ваш аккаунт для хранение собственных репо

Подключается с помощью команды (репо PHP)

    sudo add-apt-repository ppa:ondrej/php
    sudo apt update

После подключения также создается файл .list в папке /etc/apt/sources.list.d/ с данным репо

Команда watch позволяет повторять запуск команду с определенным интервалом

    watch -n 0.5 cat file

Каждые 0.5 сек. читается файл file

Сайт: crontab.guru: помощь по работе с задачами в Ubuntu. Задача создается с помощью 

    crontab -e

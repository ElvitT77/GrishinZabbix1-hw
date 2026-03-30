# GrishinZabbix1-hw
## Задание 1

Установите Zabbix Server с веб-интерфейсом.
Процесс выполнения

    Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
    Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.
    Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.
    Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.

Требования к результатам

    Прикрепите в файл README.md скриншот авторизации в админке.
    Приложите в файл README.md текст использованных команд в GitHub.

<img width="974" height="553" alt="изображение" src="https://github.com/user-attachments/assets/ae68ac22-70b1-46ec-8697-fd19ceeead35" />

<img width="974" height="74" alt="изображение" src="https://github.com/user-attachments/assets/d486d3bf-1b82-4e9c-9480-1ca37086d810" />

<img width="974" height="135" alt="изображение" src="https://github.com/user-attachments/assets/293f1a3a-6ef8-4b08-9e7b-3c99bcee8a66" />

<img width="974" height="56" alt="изображение" src="https://github.com/user-attachments/assets/c63a19ca-cc50-4c2c-8ff4-3339da5b9418" />

<img width="974" height="59" alt="изображение" src="https://github.com/user-attachments/assets/30e902b4-ae70-4726-983a-b7f90d38c2c9" />

<img width="974" height="426" alt="изображение" src="https://github.com/user-attachments/assets/a5c2f5a8-2bd2-4465-a4f6-353e41592572" />

<img width="974" height="204" alt="изображение" src="https://github.com/user-attachments/assets/366ef4d1-31f6-4334-8d73-e09a58d6b317" />

<img width="974" height="598" alt="изображение" src="https://github.com/user-attachments/assets/18f89ff2-b235-4c6f-b257-07292bcdaf80" />

<img width="974" height="589" alt="изображение" src="https://github.com/user-attachments/assets/625b55f5-6dd8-41ea-9dea-11175e3404c8" />

<img width="974" height="589" alt="изображение" src="https://github.com/user-attachments/assets/2b747edd-c3a3-4b08-8af4-d0559ae66c14" />

<img width="974" height="179" alt="изображение" src="https://github.com/user-attachments/assets/fa7ff816-6387-4c6b-9aa9-63cad37c32b6" />

Команды:

1) sudo -s
2) apt install postgresql
3) wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb
4) dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
5) apt update
6) apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-script
7) su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'1234567890\'';"'
8) su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
9) nano  /etc/zabbix/zabbix_server.conf
10) systemctl restart zabbix-server apache2
11) systemctl enable zabbix-server apache2


## Задание 2

Установите Zabbix Agent на два хоста.
Процесс выполнения

    Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
    Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.
    Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.
    Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
    Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.

Требования к результатам

    Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
    Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
    Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
    Приложите в файл README.md текст использованных команд в GitHub

<img width="974" height="410" alt="изображение" src="https://github.com/user-attachments/assets/58d0e645-5ca5-4b4c-8979-10d6ef72297f" />

<img width="974" height="548" alt="изображение" src="https://github.com/user-attachments/assets/fda1aadb-ed3e-459c-82dc-1d54c120b8e9" />

<img width="974" height="579" alt="изображение" src="https://github.com/user-attachments/assets/39d00564-672c-400c-a5ab-ead75889f5bd" />

Команды:

1) dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
2) apt install zabbix-agent
3) systemctl restart zabbix-agent
4) systemctl enable zabbix-agent
5) + добавление IP в zabbix_agentd.conf



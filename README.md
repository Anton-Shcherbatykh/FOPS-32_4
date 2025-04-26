# Домашнее задание к занятию "Система мониторинга Zabbix" - `Щербатых А.Е.`

## Задание 1

### Процесс выполнения
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.
   ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_1_2.jpg)
3. Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.
4. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.

### Требования к результатам
1. Прикрепите в файл README.md скриншот авторизации в админке.
   ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_1_1.jpg)

2. Приложите в файл README.md текст использованных команд в GitHub.

   **Установика PostgreSQL** `sudo apt install postgresql`
   
   **Установка последней стабильной версии Zabbix с поддержкой PostgreSQL и Apache** (есть версия 7.4, но стабильный релиз только 7.2)
   `apt install zabbix-server-pgsql zabbix-frontend-php php8.2-pgsql zabbix-apache-conf zabbix-sql-scripts`


## Задание 2
### Процесс выполнения
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.
    ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_2_2.jpg)
3. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.
4. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
    ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_2_3.jpg)
5. Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.
  
### Требования к результатам
1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
    ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_2_5_2.jpg)
2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
   ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_2_5_1.jpg)
3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
    ![alt text](https://github.com/Anton-Shcherbatykh/FOPS-32_4/blob/main/img/%D0%97%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_2_5.jpg)
4. Приложите в файл README.md текст использованных команд в GitHub
   Установка zabbix агента `sudo apt install zabbix-agent`
   Делаем возможным запуск агента при запуске ОС `sudo systemctl enable zabbix-agent`
   Запуск агента `sudo systemctl start zabbix-agent`
   Попадаем в админку по адресу `http://192.168.0.101/zabbix`

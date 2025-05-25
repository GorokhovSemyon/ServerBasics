## Part 1. Установка ОС

- ``Проверка версии Ubuntu после установки ``<br>
![Alt text](./imgs/1.png "Optional Title")<br>


---

## Part 2. Создание пользователя
- ``Создаём пользователя и назначаем ему группу adm``<br>
![Alt text](./imgs/2.1.png "Optional Title")<br>


- ``Вывод списка пользователей (добавленный в конце)``<br>
![Alt text](./imgs/2.2.png "Optional Title")<br>


---

## Part 3. Настройка сети ОС

- ``Задали название машине вида user-1``<br>
 ![Alt text](./imgs/3.4.png "Optional Title")<br>

- ``Установили актуальную временную зону и вывели информацию в терминал``<br>
![Alt text](./imgs/3.5.png "Optional Title")<br>

- ``Установили набор сетевых инструментов``<br>
![Alt text](./imgs/3.6.png "Optional Title")<br>
``Вывели информацию о сетевых интерфейсах``<br>
![Alt text](./imgs/3.7.png "Optional Title")<br>
**lo (loopback device)** – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине. С этим интерфейсом всегда связан адрес 127.0.0.1. У него есть dns-имя – localhost.

- ``Используя консольную команду получить ip адрес устройства, на котором вы работаете, от DHCP сервера``<br>
![Alt text](./imgs/3.8.png "Optional Title")<br>
**DHCP - Dynamic Host Configuration Protocol** - автоматический предоставляет IP адреса и прочие настройки сети (маску сети, шлюз и т.п) компьютерам и различным устройствам в сети.

- ``Узнали внешний IP-адрес``<br>
![Alt text](./imgs/3.9.png "Optional Title")<br>

- ``Узнали внутренний IP-адрес шлюза, он же ip-адрес по умолчанию``<br>
![Alt text](./imgs/3.10.png "Optional Title")<br>

- ``Изменили файл /etc/netplan/*.yaml, применили изменения в netplan, перезагрузились``<br>
![Alt text](./imgs/3.11.png "Optional Title")<br>
![Alt text](./imgs/3.12.png "Optional Title")<br>
- ``Проверяем, что адреса соотсветствуют заданным в предыдущем пункте``<br>
![Alt text](./imgs/3.13.png "Optional Title")<br>
- ``Успешно пропинговали удаленные хосты 1.1.1.1 и ya.ru``<br>
![Alt text](./imgs/3.14.png "Optional Title")<br>

---

## Part 4. Обновление ОС
- ``Успешно обновили системыне пакеты``<br>
![Alt text](./imgs/4.1.png "Optional Title")<br>

---

## Part 5. Использование команды sudo
- **sudo** - позволяет временно поднимать привилегии и выполнять задачи администрирования системы с максимальными правами<br>
``Добавили пользователя в группу с привилегиями sudo, переключились на этого пользователя и поменяли hostname``<br>
![Alt text](./imgs/5.1.png "Optional Title")<br>

---

## Part 6. Установка и настройка службы времени
- ``Вывод команды с корректным временем``<br>
![Alt text](./imgs/6.1.png "Optional Title")<br>

---

## Part 7. Установка и использование текстовых редакторов
![Alt text](./imgs/7.1_VIM.png "Optional Title")<br>
![Alt text](./imgs/7.2_VIM.png "Optional Title")<br>
![Alt text](./imgs/7.3_VIM.png "Optional Title")<br>
![Alt text](./imgs/7.4_VIM.png "Optional Title")<br>
``1) vim test_VIM.txt;``

``2) Режим редактирования: I;``

``3) Выйти из режима редактирования: esc;``

``4) Выход с cохранением: :wq;``

``5) Выход без сохранения: :q;``

``6) Поиск: /текст, который хотим найти;``

`` 7)Замена: :s/<что хотим изменить>/<на что хотим заменить>;``

![Alt text](./imgs/7.1_NANO.png "Optional Title")<br>
![Alt text](./imgs/7.2_NANO.png "Optional Title")<br>
![Alt text](./imgs/7.3_NANO.png "Optional Title")<br>
![Alt text](./imgs/7.4_NANO.png "Optional Title")<br>
``1) nano test_NANO.txt;``

``2) Выход с cохранением: CTRL + x, затем y и enter;``

``3) Выход без сохранения: CTRL + x, затем n;``

``4) Поиск: CTRL + W, затем enter (alt + w для перехода к след. вхождению, ctrl + c для преращения поиска);``

``5) Замена: CTRL + \ + <что хотим изменить + enter> + <на что хотим заменить + enter> + A(для замены все вхождения) или y и n по отдельности;``

![Alt text](./imgs/7.1_JOE.png "Optional Title")<br>
![Alt text](./imgs/7.2_JOE.png "Optional Title")<br>
![Alt text](./imgs/7.3_JOE.png "Optional Title")<br>
![Alt text](./imgs/7.4_JOE.png "Optional Title")<br>
``1) joe test_JOE.txt;``

``2) Для выхода без сохранения ^C -> y;``

``3) Для поиска: ^K F -> что ищем -> I;``

``4) Для замены: ^K F -> что заменить -> R -> чем -> Y;``

## Part 8. Установка и базовая настройка сервиса SSHD
- ``Установка cлужбу SSHd``<br>
*__sudo apt-get install ssh__*<br>
*__sudo apt install openssh-server__*<br>
![Alt text](./imgs/8.1.png "Optional Title")<br>
- ``Добавление автостарта службы при загрузке системы``<br>
*__-sudo systemctl enable ssh__*<br>
*__systemctl status ssh__*<br>
![Alt text](./imgs/8.2.png "Optional Title")<br>
- ``Перенастройка cлужбы SSHd на порт 2022``<br>
*__sudo vim /etc/ssh/sshd_config__*<br>
![Alt text](./imgs/8.3.png "Optional Title")<br>
*__systemctl status ssh__*<br><br>
- ``Команда PS, предназначена для представления о наличии процесса sshd. Флаги приведены ниже``<br>
**ps** - показывает запущенные процессы, выполняемые пользователем в окне терминала<br>
**-e или -А** -показывает все процессы, кроме лидеров сессии<br>
**-d -N** -можно инвертировать вывод с помощью переключателя -N. Например, если хочу вывести только лидеров сеансов<br>
**-T** -увидеть только процессы, связанные с этим терминалом<br>
**-r** -просмотреть все работающие (running) процессы<br>
**-p 'pid'** -если вы знаете идентификатор процесса PID, вы можете просто использовать следующую команду, для вывода процесса с этим 'pid'<br>
**-p 'pid1' 'pid2'**<br>
**U 'userlist'** -найти все процессы, выполняемые конкретным пользователем<br>
![Alt text](./imgs/8.4.png "Optional Title")<br>
- ``Перезагружаем систему``<br><br>
- ``netstat -tan``<br>
![Alt text](./imgs/8.5.png "Optional Title")<br>
**-tan**: <br>
-a -	Показывать состояние всех сокетов; обычно сокеты, используемые серверными процессами, не показываются.<br>
-n - Показывать сетевые адреса как числа. netstat обычно показывает адреса как символы.<br>
-t - Отображать TCP подключения<br>
**Proto** - Содержит тип протокола<br>
**Recv-Q** - Счётчик байтов не скопированных программой пользователя из этого сокета.<br>
**Send-Q** - Счётчик байтов, не подтверждённых удалённым узлом.<br>
**Local Address** - Адрес и номер порта локального конца сокета.<br>
**Foreign Address** - Адрес и номер порта удалённого конца сокета.<br>
**State** - Состояние сокета.<br> 
LISTEN Сокет ожидает входящих подключений.<br> 
SYN_SENT Сокет, находящийся в режиме активной попытки установки подключения.<br>
0.0.0.0 -  это немаршрутизируемый адрес IPv4, который используется в качестве адреса по умолчанию или адреса-заполнителя.

---

## Part 9. Установка и использование утилит top, htop
- Uptime: 5 min<br>
- 1 user<br>
- Общая загрузка системы: 0.00, 0.00, 0.00<br>
- Общее количество процессов: 96 total<br>
- Загрузка CPU: 0.1%<br>
- Загрузка MEM: 160/3920<br>
- PID процесса, занимающего больше памяти - 1<br>
- PID процесса, занимающего больше всего процессорного времени - 1361<br>

-- ``сортировка по PID``<br>
![Alt text](./imgs/9.1.png "Optional Title")<br>
-- ``сортировка по PERCENT_CPU``<br>
![Alt text](./imgs/9.2.png "Optional Title")<br>
-- ``сортировка по PERCENT_MEM``<br>
![Alt text](./imgs/9.3.png "Optional Title")<br>
-- ``сортировка по TIME``<br>
![Alt text](./imgs/9.4.png "Optional Title")<br>
-- ``фильтр по процессу sshd``<br>
![Alt text](./imgs/9.5.png "Optional Title")<br>
-- ``поиск процесса syslog``<br>
![Alt text](./imgs/9.6.png "Optional Title")<br>
-- ``с добавленным выводом hostname, clock и uptime``<br>
![Alt text](./imgs/9.7.png "Optional Title")<br>

---

## Part 10. Использование утилиты fdisk
- Disk /dev/sda, size: 10 GiB, 10737418240 bytes, 20971520 sectors<br>
![Alt text](./imgs/10.1.png "Optional Title")<br>
- Размер swap равен нулю<br>
![Alt text](./imgs/10.2.png "Optional Title")<br>

---

## Part 11. Использование утилиты df
- bytes
![Alt text](./imgs/11.1.png "Optional Title")<br>
- ext4
![Alt text](./imgs/11.2.png "Optional Title")<br>

---

## Part 12. Использование утилиты du
- ``du command:``<br>
![Alt text](./imgs/12.1.png "Optional Title")<br>
- ``Вывести размер папок /home, /var, /var/log (в байтах):``<br>
![Alt text](./imgs/12.2.png "Optional Title")<br>
- ``Вывести размер папок /home, /var, /var/log (в человекочитаемом виде):``<br>
![Alt text](./imgs/12.3.png "Optional Title")<br>
- ``Вывести размер всего содержимого в /var/log (не общее, а каждого вложенного элемента, используя *):``<br>
![Alt text](./imgs/12.4.png "Optional Title")<br>

---

## Part 13. Установка и использование утилиты ncdu
- ``Установка``<br>
![Alt text](./imgs/13.1.png "Optional Title")<br>
- ``/home``<br>
![Alt text](./imgs/13.2.png "Optional Title")<br>
- ``/var``<br>
![Alt text](./imgs/13.3.png "Optional Title")<br>
- ``/var/log``<br>
![Alt text](./imgs/13.4.png "Optional Title")<br>

---

## Part 14. Работа с системными журналами
- ``/var/log/dmesg``<br>
![Alt text](./imgs/14.1.png "Optional Title")<br>
- ``/var/log/syslog``<br>
![Alt text](./imgs/14.2.png "Optional Title")<br>
- ``Последняя авторизация``<br>
![Alt text](./imgs/14.3.png "Optional Title")<br>
- ``Перезапуск OpenSSH Server``<br>
![Alt text](./imgs/14.4.png "Optional Title")<br>

---

## Part 15. Использование планировщика заданий CRON
- ``Создание задачи в cron``<br>
![Alt text](./imgs/15.1.png "Optional Title")<br>
- ``uptime каждые 2 минуты``<br>
![Alt text](./imgs/15.2.png "Optional Title")<br>
- ``Вывели список задач``<br>
![Alt text](./imgs/15.3.png "Optional Title")<br>
- ``Удалили все задачи вывели список``<br>
![Alt text](./imgs/15.4.png "Optional Title")<br>

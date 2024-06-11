# S21_Linux. First Project

## Part 1
![img1.png](img%2Fimg1.png)

Смотрим версию Ubuntu после установки

(Команда: "cat /etc/issue")

## Part 2
![img2.png](img%2Fimg2.png)
![img2.1.png](img%2Fimg2.1.png)

Добавляем пользователя testuser и добавляем его в группу adm
- "sudo useradd testuser -d /home/user -m -G adm -s /bin/bash"

Проверяем добавление:
- "cat /etc/passwd"
- "groups testuser"

## Part 3
### Part 3.1 Part 3.2
![img3.png](img%2Fimg3.png)

Зададим название машины вида user-1
- "sudo hostnamectl set-hostname user-1"

Установим время соответсвующее местному времени
- "sudo timedatectl set-timezone Europe/Moscow"

### Part 3.3
![img3.1.png](img%2Fimg3.1.png)

lo (loopback device) – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине. С этим интерфейсом всегда связан адрес 127.0.0.1. У него есть dns-имя – localhost.

### Part 3.4
![img3.2.png](img%2Fimg3.2.png)

DHCP - Dynamic Host Configuration Protocol, сетевой протокол, позволяющий сетевым устройствам автоматически получать IP-адрес и другие параметры, необходимые для работы в сети TCP/IP. Данный протокол работает по модели «клиент-сервер».

### Part 3.5
![img3.3.png](img%2Fimg3.3.png)

Определяем внешний IP-адрес шлюза, который используется для взаимодействия с внешним сервером Google (8.8.8.8).
- "ping -c 1 8.8.8.8 | grep PING | awk '{print $3}' | tr -d '()'"

Определяем внешний ip адрес шлюза сети линукс
- "ip route | grep default | awk '{print $3}'"

- ip route - для показа и манипуляций таблиц маршрутизации
- awk '{print $3}" - команда awk, которая указывает на вывод третьего поля из строки, разделенной пробелами.

### Part 3.6
![img3.4.png](img%2Fimg3.4.png)

- "sudo nano /etc/netplan/00-installer-config.yaml"
- "sudo netplan apply"

### Part 3.7
- "sudo reboot"

![img3.5.png](img%2Fimg3.5.png)

- Проверили внешний и локальный ip шлюза(значения сошлись)
- Успешно пропинговали 1.1.1.1 и ya.ru без потерь

![img3.6.png](img%2Fimg3.6.png)

## Part 4
![img4.png](img%2Fimg4.png)

## Part 5

Sudo – это утилита для операционных систем семейства Linux, позволяющая пользователю запускать программы с привилегиями другой учётной записи, как правило, суперпользователя.

![img5.png](img%2Fimg5.png)

- "su testuser" переключение на пользователя
- "sudo usermod -aG sudo testuser" добавление в группу sudo tester'a

![img5.1.png](img%2Fimg5.1.png)

## Part 6
![img6.png](img%2Fimg6.png)

- sudo apt install systemd-timesyncd

- "sudo systemctl start systemd-timesyncd"
- "sudo systemctl enable systemd-timesyncd"

Запуск службы и её автоматический запуск при каждом старте системы

![img6.1.png](img%2Fimg6.1.png)

"sudo systemctl status systemd-timesyncd"
 Убедитесь, что служба работает без ошибок.

  ## Part 7
![img7vim.png](img%2Fimg7vim.png)

- Чтобы выйти из vim сохраняя изменения, нужно нажать клавиши Esc, затем :wq и Enter.

![img7.1nano.png](img%2Fimg7.1nano.png)

- Чтобы выйти из nano сохраняя изменения, нужно нажать клавиши Ctrl+X, затем Y и Enter.

![img7.2joe.png](img%2Fimg7.2joe.png)

- Чтобы выйти из Joe сохраняя изменения, нужно нажать клавиши Ctrl+K, затем X и Enter.

![img7vim1.png](img%2Fimg7vim1.png)
- Чтобы выйти из vim не сохраняя изменения нужно нажать клавиши Esc, затем :q! и Enter.

![img7nano1.png](img%2Fimg7nano1.png)
- Чтобы выйти из nano не сохраняя изменения нужно нажать клавиши Ctrl+X, затем N и Enter.

![img7joe1.png](img%2Fimg7joe1.png)
- Чтобы выйти из Joe не сохраняя изменения нужно нажать клавиши Ctrl+K, затем Q и выбрать n и Enter.

>VIM:
>Нужно нажать клавишу / и ввести слово, которое вы хотите найти. Чтобы перейти к следующему совпадению, нужно нажать клавишу n. Чтобы перейти к предыдущему совпадению, нужно нажать клавишу N.

![vimfind.png](img%2Fvimfind.png)

>Чтобы заменить слово в VIM, нужно нажать клавиши : и ввести команду %s/old_word/new_word/g, где old_word Чтобы заменить все вхождения слова, нужно добавить флаг g в конце команды.

![vimrep.png](img%2Fvimrep.png)

>NANO:
>Чтобы в NANO найти слово, нужно нажать клавиши Ctrl+W и ввести слово и нажать  которое вы хотите найти. Чтобы перейти к следующему совпадению, нужно нажать клавишу Alt+W. Чтобы перейти к предыдущему совпадению, нужно нажать клавишу Alt+V.

![nanofind.png](img%2Fnanofind.png)

>Для замены слова в NANO нужно нажать клавиши Ctrl+\ и ввести слово, которое вы хотите заменить, а затем новое слово. Чтобы заменить все вхождения слова, нужно нажать клавишу A.

![nanorep.png](img%2Fnanorep.png)

>JOE:
>Чтобы в JOE найти слово, нужно нажать клавиши Ctrl+K F и ввести слово, которое вы хотите найти. Чтобы перейти к следующему совпадению, нужно нажать клавишу Ctrl+K. Чтобы перейти к предыдущему совпадению, нужно нажать клавишу Ctrl+Shift+K.

![joefind.png](img%2Fjoefind.png)

>Для замены слова в JOE нужно нажать клавиши Ctrl+K, F, R, и ввести слово, которое вы хотите заменить, а затем новое слово. Чтобы заменить все вхождения слова, нужно нажать клавишу Ctrl+K и ввести слово, которое вы хотите заменить, а затем новое слово и нажать клавишу Alt+Shift+K.

![joerep.png](img%2Fjoerep.png)

## Part 8

![sshenable.png](img%2Fsshenable.png)
- sudo systemctl enable ssh - запуск системы ssh
- sudo nano /etc/ssh/sshd_config - Port 2022
- sudo systemctl restart sshd

![pssshd.png](img%2Fpssshd.png)
- Отображение процесса
<b>ps</b> - выводит сведения о процессах в статическом виде
<b>-е</b> - выбор всех процессов
<b>| grep sshd</b> - поиск через pipe как вывод грепа для ввода ps

- ``sudo reboot``
- netstat -tan
![netstat.png](img%2Fnetstat.png)
<b>-tan:</b>
- t - отабражает TCP подключения
- a - Показать состояние всех сокетов; обычно сокеты, используемые серверными процессами не показываются
- n - Показать сетевые адреса как числа. netstat обычно показывает адреса как символы

| Атрибут       | Описание                |
| ------------- |:------------------|
| Proto     | Содержит тип протокола    |
| Recv-Q     | Счетчик байтов не скопированных программой пользователя их этого сокета |
| Send-Q  | Счетчик байтов, не подтвержденных удалленым узлом         |
| Local address  | Адрес и номер порта локального конца сокета        |
| Foreign address  | Адрес и номер порта удаленного конца сокета        |
| State  | Состояние сокета        |

LISTEN - Сокет ожидает входящих подклчений<br>
SYN_SENT - Сокет находящийся в режиме активной попытки установки подключения<br>
0.0.0.0 - это немаршрутизируемый адрес IPv4, который используется в качестве адреса по умолчанию или адреса-заполнителя

## Part 9
![top.png](img%2Ftop.png)

Вывод команды top:

- Uptime: 2.46
- Пользователей: 1
- Загрузка системы: 0,02, 0,01, 0,00
- Процессы: 103 (1 запущенный, 102 в ожидании)
- Загрузка CPU: 0,0% пользовательского времени, 0,2% системного времени, 99,8% простаивание
- Память: 3920 MiB всего, 3403.4 MiB свободно, 152 MiB использовано
- Использование команды **htop**<br>
FN+F6-открыть поле сортировки
    - отсортированному по PID
  
     ![PIDsort.png](img%2FPIDsort.png)
- 
    - отсортированному по PERCENT_CPU

     ![cpusort.png](img%2Fcpusort.png)

    - отсортированному по PERCENT_MEM
  
     ![memsort.png](img%2Fmemsort.png)

    - отсортированному по TIME
  
     ![timesort.png](img%2Ftimesort.png)

    - отфильтрованному для процесса sshd
  
     ![filtersshd.png](img%2Ffiltersshd.png)

    - с процессом syslog, найденным, используя поиск
  
    ![syslog.png](img%2Fsyslog.png)

    - с добавленным выводом hostname, clock и uptime<br>
    FN+F2(Setup)
  
    ![htopsetup.png](img%2Fhtopsetup.png)

## Part 10
Жесткий диск:

- Название: /dev/sda
- Размер: 25 ГБ (гигабайт), что равно 26843545600 байтам.
- Количество секторов: 52428800. 

Разделы:
- /dev/sda1:
Размер: 1 МБ (мегабайт).
Начальный сектор: 2048, Конечный сектор: 4095.
- /dev/sda2:
Размер: 2 ГБ (гигабайт).
Начальный сектор: 4096, Конечный сектор: 4198399.
- /dev/sda3:
Размер: 23 ГБ (гигабайт).
Начальный сектор: 4198400, Конечный сектор: 52426751.

![fdisk.png](img%2Ffdisk.png)
![swapon.png](img%2Fswapon.png)

## Part 11

Из вывода команды df для корневого раздела (/) следующая информация:

- Размер раздела: 11758760 (12 гигабайт)
- Размер занятого пространства: 5110600 (4.9 гигабайт)
- Размер свободного пространства: 6029052 (5.8 гигабайт)
- Процент использования: 46%.
- Единица измерения в выводе - 1k-blocks.
![df.png](img%2Fdf.png)

Для корневого раздела (/) из df -Th следующие данные:

- Размер раздела: 12 гигабайт
- Размер занятого пространства: 4.9 гигабайт
- Размер свободного пространства: 5.8 гигабайт
- Процент использования: 46%.
- Тип файловой системы: ext4

![dfth.png](img%2Fdfth.png)

## Part 12
- ``du``

![du.png](img%2Fdu.png)

 - ``du -h``

 Чтобы вывод не был большим из-за установленного vscode server для работы с виртуалкой через vscode

![duh.png](img%2Fduh.png)

 - ``du /home -h``

![duhome.png](img%2Fduhome.png)

 - ``du /var -h``

![duvar.png](img%2Fduvar.png)

 - ``sudo du /var/log -h``

![duvarlog.png](img%2Fduvarlog.png)

 - ``sudo du /var/log/* -h``

![duvar*.png](img%2Fduvar*.png)

## Part 13

  - ``ncdu ``

![ncdu.png](img%2Fncdu.png)

  - ``ncdu /home``

![ncduhome.png](img%2Fncduhome.png)

  - ``ncdu /var``

![ncduvar.png](img%2Fncduvar.png)

 - ``ncdu /var/log``

![ncduvarlog.png](img%2Fncduvarlog.png) 

## Part 14
- ``Последняя авторизация``<br>

![login.png](img%2Flogin.png)

- ``Перезапуск OpenSSH Server``<br>

![ressshd.png](img%2Fressshd.png)

## Part 15
- ``crontab -e``<br>
![crone.png](img%2Fcrone.png)
- ``grep CRON /var/log/syslog``<br>
![cron.png](img%2Fcron.png)
 - ``crontab -r``<br>
![crondel.png](img%2Fcrondel.png)
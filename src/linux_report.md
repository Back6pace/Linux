# S21_Linux. First Project

## Part 1
![img1.png](img%2Fimg1.png)

Смотрим версию Ubuntu после установки

(Команда: "cat /etc/issue")

## Part 2
![img2.png](img%2Fimg2.png)
![img2.1.png](img%2Fimg2.1.png)

Добавляем пользователя TestAdmUser
- "sudo useradd TestAdmUser"

Добавляем в группу
- "sudo usermod -aG adm TestAdmUser"


Проверяем добавление:
- "cat /etc/passwd"
- "groups newuser"

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



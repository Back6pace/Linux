# S21_Linux. First Project

## Part 1
![img1.png](img%2Fimg1.png)

Смотрим версию Ubuntu после установки

(Команда: "cat /etc/issue")

## Part 2
![img2.png](img%2Fimg2.png)
![img2.png](img%2Fimg2.1.png)

Добавляем пользователя TestAdmUser
- "sudo useradd TestAdmUser"

Добавляем в группу
- "sudo usermod -aG adm TestAdmUser"


Проверяем добавление:
- "cat /etc/passwd"
- "groups newuser"

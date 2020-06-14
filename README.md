# 1. Jenkins - Автоматизация CI/CD

# 2. Jenkins - Установка на Linux Ubuntu
![Debian/Ubuntu install manual from jenkins.io](https://www.jenkins.io/doc/book/installing/#debianubuntu) <br>
 <br>
install Java first <br>
\$ sudo apt-get update <br>
\$ sudo apt-get install openjdk-8-jre <br>
<br>
\$ wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add - <br>
\$ sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \ <br>
    /etc/apt/sources.list.d/jenkins.list'<br>
\$ sudo apt-get update <br>
\$ sudo apt-get install jenkins <br>
 <br>
Проверяем jenkins <br>
\$ sudo service jenkins status <br>
Останавливаем jenkins <br>
\$ sudo service jenkins stop <br>
Запускаем jenkins <br>
\$ sudo service jenkins stop <br>
$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword <br>

# 3. Jenkins - Администрирование Jenkins
## Обновление Jenkins<br>
## Возврат на предыдущую версию Jenkins<br>
/usr/share/jenkins/ - место для копирования новых версий. предварительно сделать резервную копию старой версии<br>
jenkins.war - имя файла рабочей версии<br>
подменяя файл, jenkins.war, делаем активной ту версию, которая нам нужна.<br>
<br>
перезагрузка сервера<br>
IPaddress:8080/restart<br>
\$ sudo service jenkins restart <br>

# 4. Jenkins - Управление Plugins
Plugin Manager в GIU.<br>
![Plugins на сайте plugins.jenkins.io](https://plugins.jenkins.io/)<br>

# 5. Jenkins - Простейшие Jobs включая Deployment
## Создание простейших Jenkins Jobs<br>
## Директории Jobs и Build на Jenkins Server<br>
## АвтоУдаление старых Build-ов<br>
## Простейший пример доставки Artifact на удаленный сервер<br>
![BuildShellCommand](https://github.com/zuFrost/Jenkins/blob/master/BuildShellCommand)<br>
![TestShellCommand](https://github.com/zuFrost/Jenkins/blob/master/TestShellCommand)<br>
Deploy with Plugin 
![Publish Over SSH](https://plugins.jenkins.io/publish-over-ssh/)<br>

# 6. Jenkins - Добавление Slave/Node
## &#9679;Снизить нагрузку с Jenkins Master
## &#9679;Больше одновременных Build'ов
## &#9679;Build разных платформ на разных сереверах
### &#160; &#9679;Node1 - для .Net
### &#160; &#9679;Node2 - для JAVA
### &#160; &#9679;Node3 - для Ansible
### &#160; &#9679;Node4 - для Chef

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


$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword

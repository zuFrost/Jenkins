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
установка Java 8 на Ubuntu на Slave машинах<br>
\$ sudo apt-get update<br>
\$ sudo apt install openjdk-8-jdk<br>
\$ java -version<br>
2 Plugins for adding Slave Servers to Jenkins:<br>
&#160; &#9679; ![SSH Agent](https://plugins.jenkins.io/ssh-agent/)<br>
&#160; &#9679; ![SSH Slaves renamed to SSH Build Agents](https://plugins.jenkins.io/ssh-slaves/)<br>

# 7. Jenkins - Удалённое и локальное управление через Jenkins CLI Client
CLI - Command Line Interface<br>
&#160; &#9679; Позволяет управлять Jenkins из коммандной строки<br>
&#160; &#9679; Позволяет писать скрипты для Jenkins<br>
&#160; &#9679; Позволяет управлять Локально из командной строки самого Jenkins сервера<br>
&#160; &#9679; Позволяет управлять Удаленно из командной строки вашего компьютера<br>
Jenkins CLI Client file: jenkins-cli.jar<br>
скачать с вашего же Jenkins сервера {$JENKINS_URL}/jnlpJars/jenkins-cli.jar<br>
\$ java -jar jenkins-cli.jar -auth username:password -s http://localhost:8080 who-am-i<br>

### Регистрация переменных среды Linux. Логин и Токен.<br>
\$ export JENKINS_USER_ID=myserviceuser<br>
\$ export JENKINS_API_TOKEN=1160cc424290ef477696b1d0a41a90a9d3<br>
Просмотр переменных среды<br>

\$ env | grep JENKINS<br>
После регистрации переменных среды, комманда выглядит следующим образом:<br>
\$ java -jar jenkins-cli.jar -s http://localhost:8080 who-am-i<br>

### Регистрация переменных среды Windows. Логин и Токен.<br>
\$env:JENKINS_USER_ID="myserviceuser"<br>
\$env:JENKINS_API_TOKEN="1160cc424290ef477696b1d0a41a90a9d3"<br>
<br>
java -jar .\jenkins-cli.jar -s http://18.197.145.215:8080 who-am-i<br>
&#160; &#9679; команда get-job	позволяет скачать параметры указанного Job в XML формате.<br>
\$ java -jar jenkins-cli.jar -s http://localhost:8080 get-job MyJob-20200614 > myjob.xml <br>
&#160; &#9679; команда create-job	позволяет создать Job из XML<br>
\$ java -jar jenkins-cli.jar -s http://localhost:8080 create-job MyJob-20200616-fromCLI < myjob.xml<br>

# 8. Jenkins - Deployment from GitHub
используй ssh!<br>

# 9. Jenkins - Автоматизация запуска Build Job - Jenkins Build Triggers
## Jenkins Job Triggers
### &#160; &#9679; Trigger builds remotely (e.g., from scripts)
from browser line
http://52.59.192.101:8080/job/Build-AutoTrigger-1/build?token=asdarggADRGREGwserrgeqwar3432134j43kg23ug4i<br>
from command line and Authentification via Token
curl http://login:11e4e06f5072dfb0c51353cf8027c7f25c@52.59.192.101:8080/job/Build-AutoTrigger-1/build?token=asdarggADRGREGwserrgeqwar3432134j43kg23ug4i<br>
### &#160; &#9679; Build after other projects are built
### &#160; &#9679; Build periodicaly
### &#160; &#9679; Poll SCM
### &#160; &#9679; Triggers from installed Plugins

# 10. Jenkins - Автоматизация запуска Build из GitHub - Jenkins trigger from GitHub, Jenkins webhook
GitHub hook trigger for GITScm pooling (GitHub Plugin)<br>
![GitHub plugin](https://plugins.jenkins.io/github/)<br>
and in GitHub add Webhook. Payload URL = http://18.156.171.122:8080/github-webhook/<br>
Content type change to Application/Json<br>

# 11. Jenkins - Build с Параметрами
Put V to "This project is parameterized"

# 12. Jenkins - Deploy в AWS Elastic Beanstalk - Пример решения задания на интервью для DevOps Engineer



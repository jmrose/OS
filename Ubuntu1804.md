# Nginx install
$ apt-get update   
$ apt-get install nginx    
$ service nginx start  
  
  
### Error
| error |
| ----- |
| dpkg: error processing package nginx |
| # sudo systemctl stop apache2.service & sudo systemctl disable apache2.service |

| error |
| ----- |
| Could not get lock /var/lib/dpkg/lock - open (11: Resource temporarily unavailable) |
| # rm /var/lib/dpkg/lock |

| error |
| ----- |
| Could not get lock /var/lib/apt/lists/lock - open (11: Resource temporarily unavailable) |
| # rm /etc/apt/lists/lock |
  
  
  
# PHP install
### Add the PPA
$ sudo add-apt-repository ppa:ondrej/php  

### Install Required PHP5.6 Modules
$ apt-get install php5.6-fpm  
$ apt-get install php5.6-mbstring php5.6-curl php5.6-xml php5.6-mysqli  
$ apt-get install php5.6-mcrypt  
$ apt-get install php-pear php5.6-dev  
$ service php5.6-fpm start  
  
### Composer Install  
$ composer self-update  
_tokenUrl 확인 : https://github.com/settings/tokens_  
  
### Yii2 Install  
  
### Yii2 버젼업  
$ composer update yiisoft/yii2 yiisoft/yii2-composer bower-asset/inputmask  
  
  
  
# Gearman Install ( php5>=, php<6 에서 사용가능 )
$ sudo apt-get install gearman-job-server libgearman-dev   
$ sudo apt-get upgrade  
$ sudo pecl install gearman  ( pecl : php 확장저장소이며  php-dev 설치해야 실행 됨 )  

__php.ini에 extension="gearman.so" 추가하기__  
  
  
#### Gearman start
$ sudo service gearman-job-server restart  
  
or  

$ gearadmin --shutdown  
$ gearmand -d -l /var/log/gearmand.log  
  
  
# [Supervisor install](http://supervisord.org/installing.html)  ( python 2.4 이상 python 3 이하에서 사용가능 )
  
$ apt-get update  
$ apt-get install python3.6  
$ ln -s /usr/bin/python3.6 /usr/bin/python

$ apt-get install python3-pip  
  
$ ln -s /usr/bin/pip3 /usr/bin/pip  
$ pip install setuptools   
  
$ pip install git+https://github.com/Supervisor/supervisor ( python3에서 실행가능버젼 )
  



## Ubuntu 18.04 주요사항 
* python 3.6 이 기본 설치 됨
* 커널 4.15 탑재 
* Swap  대신 스왑 파일이 생성됨  
* 최소 설치 옵션이 생김
* 설치 이미지 63bit만 지원
  
## Ubuntu 설정 및 명령어  
  
#### 시간설정
$ date  
$ sudo dpkg-reconfigure tzdata  
  Asia/Seoul 선택하기  
  
  
### Swap
  
##### swap 정보 보기  
$ sudo swapon --show  

<pre>
<code>
----- partition 으로 잡혀 있는 경우 -----

~# sudo swapon --show
NAME      TYPE      SIZE USED PRIO
/dev/sda3 partition   4G   0B   -2

~# fdisk -l
Disk /dev/loop0: 86.9 MiB, 91099136 bytes, 177928 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/loop1: 86.6 MiB, 90759168 bytes, 177264 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/sda: 59.6 GiB, 64023257088 bytes, 125045424 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: EF06B257-9E52-4EDB-ACCF-AA837881A283

Device       Start       End   Sectors  Size Type
/dev/sda1     2048      4095      2048    1M BIOS boot
/dev/sda2     4096   1052671   1048576  512M Linux filesystem
/dev/sda3  1052672   9441279   8388608    4G Linux swap
/dev/sda4  9441280 125042687 115601408 55.1G Linux filesystem
</code>
</pre>


##### Creating a Swap File
_Ubuntu 18.04에  swap file이 생김...  swap을 file 로 만들기_
$ sudo fallocate -l 1G /swapfile   
  
$ ls -lh /swapfile  
-rw-r--r-- 1 root root 1.0G Apr 25 11:14 /swapfile  
  
$ sudo chmod 600 /swapfile  
$ sudo mkswap /swapfile  
$ sudo swapon /swapfile  
$ sudo swapon --show  
 
<br/><br/><br/>

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
  
  
  
# Gearman Install
_( php5>=, php<6 에서 사용가능 )_  
  
$ sudo apt-get install gearman-job-server libgearman-dev   
$ sudo apt-get upgrade  
$ sudo pecl install gearman  ( pecl : php 확장저장소이며  php-dev 설치해야 실행 됨 )  

__php.ini에 extension="gearman.so" 추가하기__  
  
  
#### Gearman start
$ sudo service gearman-job-server restart  
  
or  

$ gearadmin --shutdown  
$ gearmand -d -l /var/log/gearmand.log  
  
  
# Supervisor Install
 
$ apt-get update  
$ apt-get install python3.6  
$ ln -s /usr/bin/python3.6 /usr/bin/python  
  
$ apt-get install python3-pip  
  
$ ln -s /usr/bin/pip3 /usr/bin/pip  
$ pip install setuptools   
  
$ pip install git+https://github.com/Supervisor/supervisor ( python3에서 실행가능버젼 )
  
  
<br/><br/>


### 참조
* [Supervisord](http://supervisord.org/installing.html)
* [How To Add Swap Space on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-18-04)

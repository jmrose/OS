## nginx install
<pre>
<code>
# apt-get update  
# apt-get install nginx
</code>
</pre>

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



## php install
<pre>
<code>
# apt-get install php5.6-fpm
# apt-get install php5.6-mstring php5.6-curl php5.6-xml php5.6-mysqli
# apt-get install mcrypt

# composer self-update 
# token
https://github.com/settings/tokens


 yii2 버젼업
# composer update yiisoft/yii2 yiisoft/yii2-composer bower-asset/inputmask

</code>
</pre>



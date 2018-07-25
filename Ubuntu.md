### nginx install
<pre>
<code>
# apt-get update  
# apt-get install nginx
</code>
</pre>

|에러: |
|------|
|메세지|
| dpkg: error processing package nginx |
|해결 |
|# sudo systemctl stop apache2.service & sudo systemctl disable apache2.service |



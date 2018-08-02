
### Linux 명령어

### 환경변수  

> $ export http_proxy=http://xxxxx:3128  
$ env   
$ unset http_proxy  
  
### wget  
> $ wget -P ./ http://www.epost.go.kr/search/areacd/zipcode_DB.zip     

> [Header]  
$ wget -d --header="User-Agent: Mozilla/5.0 (Windows NT 6.0) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.97 Safari/537.11" --header="Referer: http://xmodulo.com/" --header="Accept-Encoding: compress, gzip" http://www.google.com/  

> $ vi ~/.wgetrc   
header = User-Agent: Mozilla/5.0 (Windows NT 6.0) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.97 Safari/537.11  
header = Referer: http://xmodulo.com/  
header = Accept-Encoding: compress, gzip  

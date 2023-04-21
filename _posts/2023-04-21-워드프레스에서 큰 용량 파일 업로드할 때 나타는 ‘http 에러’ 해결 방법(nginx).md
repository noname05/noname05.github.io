**nginx error – 413 Request Entity Too Large**

워드프레스에 동영상 파일을 업록드 하는데 자꾸 http 에러가 난다. PHP에 설정한 용량보다 작은데도 그렇다.
원인은 **nginx 설정**에 있었다. nginx에서도 업로드 용량을 설정해줘야 한다. 기본값은 1MB.

**/etc/nginx/sites-available/default**에 **client_max_body_size 000M;**를 추가해주고, nginx를 재시작 한다.

>server { <br/>
**client_max_body_size 300M;** <br/>
listen 80 default_server; <br/>
listen [::]:80 default_server; <br/>

\# SSL configuration <br/>
\# <br/>
\# listen 443 ssl default_server; <br/>
\# listen [::]:443 ssl default_server; <br/>
\# <br/>
\# Note: You should disable gzip for SSL traffic. <br/>
\# See: https://bugs.debian.org/773332 <br/>
\# <br/>
\# Read up on ssl_ciphers to ensure a secure configuration.
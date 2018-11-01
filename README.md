```php
vagrant 镜像,
1. git clone git@github.com:wxxbard/vagrant_centos7_lnmp.git
2. vagrant up 
包含软件：
centos7
nginx1.14
mysql 5.7
php7.0 +php5.4
git 
composer

mysql username root password root

server {
    listen       80;
    server_name  php7.com;
    root   /data;
    location / {
        index  index.php;
    }
    location ~ \.php(.*)$ {
        fastcgi_pass   127.0.0.1:9000;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        include        fastcgi_params;
    }
}
server {
    listen       80;
    server_name  php5.com;
    root   /data;
    location / {
        index  index.php;
    }
    location ~ \.php(.*)$ {
        fastcgi_pass   127.0.0.1:9001;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        include        fastcgi_params;
    }
}
```
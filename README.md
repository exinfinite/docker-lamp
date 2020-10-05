# docker-lamp

## 建構image
    images/php5.6-apache2/image-build.bat
    images/mysql5.6/image-build.bat

## 設定(資料庫及本機對應資料夾)
    composer/docker-compose.yml
    替換[db user]、[db password]、[exinfinite_projs]

## 執行容器
    composer/lamp-run.bat

## 網址
    web
    http(s)://192.168.99.100

    phpmyadmin
    http://192.168.99.100:8080
# docker-lamp

## 建構image
    PHP：./images/php5.6-apache2/image-build.bat
    MySql：./images/mysql5.6/image-build.bat

## 設定(資料庫及本機對應資料夾)
    檔案：./composer/docker-compose.yml
> 替換[db user]、[db password]、[exinfinite_projs]

## 執行容器
    執行：./composer/lamp-run.bat

## 本機網域(192.168.99.100或docker.local)
    web
    http(s)://本機網域

    phpmyadmin
    http://本機網域:8080

> **使用docker.local須設定host：**
>
> 192.168.99.100　docker.local
>
> **本地端憑證設為有效：**
>
> 將./images/php5.6-apache2/server.crt，匯入到「受信任的根憑證授權單位」
>
> **不使用docker.local，自訂網域名，需重新產生自簽憑證：**
>
>  _<ins>[openssl自簽憑證](https://gist.github.com/exinfinite/484346835b1cc2de6282e58eb6c2dbcc)</ins>_

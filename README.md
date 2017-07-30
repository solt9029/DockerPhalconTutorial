# 手順

dockerphalcontutorial_app_1の中での設定をする

```
cd /project
curl -sS https://getcomposer.org/installer | php
```

上記のコマンドを行うと、curlが通らず以下のようなエラーが出てしまう

```
curl: (6) Could not resolve host
```

そのため、以下のような手順を踏む必要がある

```
apt-get update
apt-get install vim
vi /etc/resolv.conf
```

これで127.0.0.11を8.8.8.8に書き換える

その後以下の処理を行う

```
/etc/init.d/apache2 restart
cd /project
curl -sS https://getcomposer.org/installer | php
```

その後、[https://github.com/phalcon/phalcon-devtools](url)の手順に従ってphalcon-devtoolsをインストールする

```
cd /project/vendor/phalcon/devtools
php phalcon.php
```

これでコマンドを確認することができる
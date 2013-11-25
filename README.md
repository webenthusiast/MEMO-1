# MEMO

## Mac OSX ローカルのDNSキャッシュ削除

    sudo killall -HUP mDNSResponder

====

## Dock

### Dockのアプリ表示側に透明なアイコンを挿入

    defaults write com.apple.dock persistent-apps -array-add '{tile-data={}; tile-type="spacer-tile";}';killall Dock

### ”自動的に隠す機能”を入にしている場合の、Dockの表示速度変更

    defaults write com.apple.dock autohide-delay -float 0;killall Dock
リストア

    defaults delete com.apple.dock autohide-delay

### ”自動的に隠す機能”を入にしている場合の、隠れるアニメーション速度変更

    defaults write com.apple.dock autohide-time-modifier -float 1;killall Dock

### Mission Controlの速度変更

    defaults write com.apple.dock expose-animation-duration -float 0.15; killall Dock

### Spacesの切り替えアニメーションを無効

    defaults write com.apple.dock workspaces-swoosh-animation-off -bool YES && killall Dock

====

## phpMyAdmin インポートタイムアウト

### ログインタイムアウト

/usr/share/phpMyAdmin/libraries/config.inc.php

    $cfg['LoginCookieValidity'] = 86400;

/etc/nginx/nginx.conf

    proxy_connect_timeout 600s;
    proxy_send_timeout 600s;
    proxy_read_timeout 600s;


    fastcgi cache
    fastcgi_cache_path /var/cache/nginx/fastcgi_cache levels=1:2
    # keys_zone=fastcgizone:32m inactive=60m;
    #fastcgi_cache_key "$scheme$request_method$host$request_uri";
    #fastcgi_cache_use_stale error timeout invalid_header http_500;
    fastcgi_send_timeout 600s;
    fastcgi_read_timeout 600s;

====

## MySQL

### ユーザー名指定ログイン

    mysql -u ユーザー名 -p

### ユーザー名追加

    mysql> GRANT ALL ON *.* TO ユーザＩＤ@"localhost"IDENTIFIED BY "パスワード";
    mysql> FLUSH PRIVILEGES;

### ユーザーパスワード変更

    SET PASSWORD FOR 'ユーザ名'@'ホスト名'=password('変更後のパスワード');

### ユーザー削除

    DELETE FROM mysql.user WHERE user='ユーザ名';

### 全ユーザー確認

    select Host, User, Password from mysql.user;

### Anonymous User / Password未設定ユーザー削除

    >use mysql;
    >delete from user where user='';
    >delete from user where password='';
    >flush privileges;

====

## Adobe CreativeCloudバージョンの拡張機能ZXPインストール

[http://www.adobe.com/exchange/em_download/em6_download.html](http://www.adobe.com/exchange/em_download/em6_download.html)


# 網元'Amimoto'のAMIをつかったEC2インスタンス構築の流れ


1. フラットデザインに変わったAmimotoからAMI起動。
2. microインスタンス選択で起動、Elastic IP設定
3. SnapshotでBU
4. yum install mlocateでlocateコマンドインストール
5 .cd /tmp/
6. wget http://downloads.sourceforge.net/project/phpmyadmin/phpMyAdmin/4.1.0-beta1/phpMyAdmin-4.1.0-beta1-all-languages.tar.gz
7. tar xvzf phpMyAdmin-4.1.0-beta1-all-languages.tar.gz
8. mv phpMyAdmin-4.1.0-beta1-all-languages phpMyAdmin
9. mv phpMyAdmin /usr/share/
10. vi /etc/nginx/conf.d/default.confを編集
11. service nginx restart
12. mcryptがないエラー

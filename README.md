# django_deploy
Deploy Django2 on Ubuntu 18.04 using Apache2 and MySQL

* How To Deploy Django on Ubuntu 18.04 using Apache and MySQL

https://www.youtube.com/watch?v=Xjdv31k-Kf4


* Ubuntu 如何用 cp 和 mv 指令複製和搬移整個資料夾（ 包含子資料夾 ） ？

https://www.arthurtoday.com/2010/09/ubuntu-cp-mv.html


1. 建立虛擬環境 & pip

2. 在/var/www/ 建立網站於Apache2的架構

＊ site

>  logs

>  public

＊ django

＊ auth


3. 移植Django網站

4. 設定MySQL資料庫

5. 連結MySQLDB ＆Django

>  sudo apt install python3-dev
>  sudo apt install libmysqlclient-dev

>  pip3 install mysqlclient  (須確認 pip3 freeze 內有mysqlclient)

＊ mysql.cnf 可略過,不用做

---

6. 安裝 Apache2 

>  sudo apt install apache2 libapache2-mod-wsgi-py3

＊ 確認有裝好Apache2：在瀏覽器上輸入ip


7. 更改設定：/etc/apache2/sites-available/000-default.conf （Django網站）

>  sudo nano /etc/apache2/sites-available/000-default.conf

6. 重新啟動Apache2

>  sudo a2enmod wsgi
>  sudo systemctl restart apache2
>  systemctl status apache2.service


7. 設定 STATIC 路徑 

＊ /var/www/tutorial/django/stat_begin/stat01/stat01/settings.py
 
＊ /etc/apache2/sites-available/000-default.conf

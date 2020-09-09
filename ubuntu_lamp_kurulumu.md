# Ubuntu 20.04'e Php Mysql Apache ve PhpmyAdmin Kurulumu

 **Tasksel Kurulumu:**  
```sh 
sudo apt install tasksel
```
**Lamp-Server Kurulumu:**  
```sh 
sudo tasksel install lamp-server
```

**Php Versiyon**  
```sh 
php -v
```

**Mysql Versiyon**  
```sh 
mysql -V
```

**Apache Versiyon**   
```sh 
apachectl -v
```

### Mysql Kullanıcı Ayarları
Mysql'a bağlanırken  **auth_socket** eklentisi ile kimlik doğrulaması yerine biz parola ile kimlik doğrulması yapacağız.
```sh 
sudo mysql
```

```sql
SELECT user, authentication_string, plugin, host FROM mysql.user;
```

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

```sql
SELECT user, authentication_string, plugin, host FROM mysql.user;
```

```sql
exit
```

**Parola ile Mysql'a Giriş:**  
```sh 
mysql -u root -p 
```

### Mysql Loglarını Açmak için:

```sh 
cd /etc/mysql/mysql.conf.d/
```

```sh
sudo nano mysqld.cnf
```

**Başındaki Diyezleri Kaldıralım**   
```
# general_log_file        = /var/log/mysql/query.log
# general_log             = 1

general_log_file        = /var/log/mysql/query.log
general_log             = 1
```

**Mysql Servisini Yeniden Başlatalım**    
```sh
sudo /etc/init.d/mysql restart
```

**Log Kayıtlarını Okuyalım**    
```sh
sudo tail -f /var/log/mysql/query.log
```

### Php Kaynak Dizini Değiştime
Php ile masaüstünde çalışmak istiyorsak, masaüstünde bir dizin oluşturalım ve apache ayarlarını yapalım.

**Masaüstüne Gidelim:**     
```sh
cd ~/Desktop
```
**Bir Dizin Oluşturalım ve Dizin İçine Girelim:**
```sh
mkdir www
```
```sh
cd www
```

**Dizinimizin Gerçek Yolunu Alalım:**    

```sh
pwd
```
> /home/user/Desktop/www

**Apache Ayarlarını Yapalım**
```sh
sudo nano /etc/apache2/apache2.conf
```

```sh
<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>

# Yukarıda bulunan dizin /var/www/ dizin yolunu kendi dizin yolumuzla değiştireceğiz.     
# Önemli nokta bir üst dizinizim adını vereceğiz. O da şu durumda bizim masaüstümüz oluyor.

<Directory /home/user/Desktop/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
```

**Diğer Apache Ayarını Yapalım**    
```sh
sudo nano /etc/apache2/sites-available/000-default.conf
```

```sh
 DocumentRoot /var/www/html
 # Kısmını dizin ismimizle değiştiriyoruz.
DocumentRoot /home/user/Desktop/www
```

**Apache Servisimizi Yeniden Başlatıyoruz**    
sudo /etc/init.d/apache2 restart

### Php Error Gösterme Ayarını Açalım
```sh
cd /etc/php
```

```sh
ls
```
>7.4
```sh
cd 7.4
```

```sh
cd apache2
```

```sh
sudo nano php.ini
```

```sh
display_errors = Off
# Off Kısmını On ile değiştiriyoruz...
display_errors = On
```

**Apache Servisini Yeniden Başlatalım**   
```sh
sudo /etc/init.d/apache2 restart
```
### PhpMyAdmin Kurulumu

**PhpMyadmin Kurulumu:**   
```sh
sudo apt install phpmyadmin
```
**Apache Ayaralarını Açalım:**    
```sh
sudo  nano /etc/apache2/apache2.conf
```
**Apache Ayarlarına PhpMyAdmin Ayarları Dizinin Yolunu Ekleyelim:**    
```sh
Include /etc/phpmyadmin/apache.conf
```

**Apache Servisini Yeniden Başlatalım**
```sh
sudo /etc/init.d/apache2 restart
```

RDS mysql notlari:
************************
My Project repomuza push ettikten sonra localdeki kodu VSC'da actık.
Daha sonra kodumuzun calısması için asagıdaki komutları local pc'mizde çalıştırıp gerekli programları yükledik.
sudo pip3 install flask
sudo pip3 install flask-mysql
sudo pip3 install sqlalchemy
sudo pip3 install Flask-SQLAlchemy
app-with-sql-lite ve app-wıth-mysql.py dosyalarını çalıştırdığımız anda, vscode'da email.db'ın oluştuğunu gormeliyiz, browser'dan localhost:5000'e girerek açtığımız browser sayfamızda da email database'i görebildiysek kod başarıyla çalışmış demektir.
***
MYSQL_RDS DIZAYNI
****
Service'lerden Rds seciliyken gerceklesen adimlar:
create database
engine mysql
version 8.0.27
free-tier
a uniqe database name
credential settings:
	database username: admin
	master password: Clarusway_1
Maximum storage threshold :40
public access: yes
additional configuration
initial database name: clarusway
backup:select window/start time: 01 am
maintenance/select window/start time: 02 am
database olustuktan sonraki adımlar:
------------------------------------------
database seciliyken;
default security group/ edit inbound rules/add rule / seceneklerden mysql/aurora -tcp -3306
ekliyoruz.
mysql.py calistirip
localhost:5000'den email list show diyerek kontrol ediyoruz
-ec2'dan mysql'a baglanma adimlari:
-------------------------------------------
security group'da tcp 80 ve 22 portlari acik olmali.
farkli bir ayarlama yok, normal actigimiz sekilde ec2-instance aciyoruz ve baglaniyoruz.
daha sonra ec2'nun icinde
   sudo yum update -y
   sudo pip3 install flask
   sudo pip3 install flask-mysql
   sudo pip3 install sqlalchemy
   sudo pip3 install flask-SQLAlchemy
   sudo yum install git -y
komutlari ile gereken programlari yukluyoruz.
sudo git clone https://github.com/myusername/my-projects.git> komutuyla
github repomu ec2 instance'a clone'ladim.
cd /myprojects/hands-on/flask-05-Handling-SQL-with-Flask-Web-Application
dosyasina girip;
sudo python3 app-with-sqlite.py calistirdik.
SONUÇ1: ec2'nun public ip'sini herhangi bir browser'da actik.
Ekranda Email Database ve show button'unun altinda kodlarimizdaki email listesini goruyorsak islem basarili.
-ayni islemi mysql.py icinde asagidaki komutla tekrarliyoruz.
         sudo python3 app-with-mysql.py
mysql kodu ile ilgili çok önemli bir puf noktasi:
-----------------------------------------
rds sayfasinda database seciliyken connectivity bolumunden endpoint'i kopyaliyoruz ve
myslq.py'deki kodumuzda
app.config['MYSQL_DATABASE_HOST'] = 'jan77-database-1.cdiyvzxuneay.us-east-1.rds.amazonaws.com'
yukardakine benzer sekilde endpoint'i python kodumuzun ilgili satırına yapistiriyoruz. Bunu yapmasaydık kodumuzdan mysql database'imize bir baglantı kuramazdı. Bu arada mysql dizayn ederken kodumuzla uyumlu şekilde username ve password'lerin aynı olmasına dikkat ettik.
SONUÇ2: sudo python3 app-with-mysql.py calistirdiktan sonra, ec2'nun public dns'ini actigimizda email database'i gorebiliyorsak islem basarili.
Not: ec2'dan baglanirken public dns'te database'i gorebilmemiz icin kodun en altindaki app.run(host='0.0.0.0', port=80) satirini aktiflestirmemiz gerekir.
Localhost'tan baglandigimizda da ayni database'i gorebilmemiz icin app.run(debug=True) satirinin aktive edilmesi gerekir.
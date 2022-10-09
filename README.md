# mysql-selfmanaged

**Cloud Environment**</br>
GCP</br>
**VM Set Up**</br>
Inital set up:</br>
</br>
</br>
</br>
Firewall Configurations (available to everyone; applied to all VMs):</br>
Firewall --> Create Firewall Rule</br>
Direction of Traffic: Ingress</br>
Specified Targets: All instances in the network</br>
Source IPv4 ranges: 0.0.0.0/0</br>
TCP: 3306</br>
</br>
In ssh-browser:</br>
$ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf </br>
change bind-address: 0.0.0.0 </br>
save: ^O</br>
$ sudo /etc/init.d/mysql restart


**Commands to set up OS image**</br>
$ sudo apt-get update</br>
$ sudo apt install mysql-server mysql-client</br>
**Changes to make mysql instance avaiable**</br>
sudo mysql</br>
CREATE USER 'steph'@'%'IDENTIFIED BY'ahi2022';</br>
GRANT ALL PRIVILEGES ON *.* TO 'steph'@'%' WITH GRANT OPTION;</br>
CREATE DATABASE db1</br>
</br>
</br>

SELECT * FROM mysql.user (to check privleges)</br> 
show databases (to double check databases)</br>
select User from mysql.user \G (to check users)</br>
mysql -u steph -p</br>
\q </br> to quit^^^
show grants for steph</br>


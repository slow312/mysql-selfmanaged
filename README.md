# mysql-selfmanaged

### Cloud Environment
GCP
### VM Set Up
Machine Configuration: E2, e2-medium</br>
Boot Disk Type: Ubantu x86/64 </br>
Firewall: Allow HTTP and HTTPs traffic
### Commands to set up OS image
$ sudo apt-get update</br>
$ sudo apt install mysql-server mysql-client</br>
### Making mysql instance available
sudo mysql</br>
CREATE USER 'steph'@'%'IDENTIFIED BY'ahi2022';</br>
GRANT ALL PRIVILEGES ON \*.* TO 'steph'@'%' WITH GRANT OPTION;</br>
CREATE DATABASE db1</br>

**Firewall Configurations**</br>
Firewall --> Create Firewall Rule</br>
Direction of Traffic: Ingress</br>
Specified Targets: All instances in the network</br>
Source IPv4 ranges: 0.0.0.0/0</br>
TCP: 3306 </br>
(available to everyone; applied to all VMs)</br></br>
**In ssh-browser:**</br>
$ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf </br>
change bind-address: 0.0.0.0 </br>
$ sudo /etc/init.d/mysql restart

### Inserting data into mysql database
(In Jupyter Notebook file)</br>
**Variables:**</br>
mysql_Hostname, mysql_User, mysql_Password, mysql_Database</br>
**Create engine:**</br>
db1 = create_engine(connection_string)</br>
**Adding pandas dataframe to mysql database**</br>
dataframe_name.to_sql('name', con=db1, if_exisits='replace')







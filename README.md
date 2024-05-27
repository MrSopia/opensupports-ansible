# opensupports-ansible
ansible playbook to deploy opensupports on rocky9

# temp notes
FRESH INSTALL WITH INTERNET!

sudo service mysqld stop
sudo dnf remove mysql mysql-server -y
sudo dnf remove mysql-client mysql-server -y
sudo rm -r /var/lib/mysql
sudo systemctl stop httpd
sudo systemctl disable httpd
sudo yum remove httpd httpd-tools -y
sudo rm -rf /etc/httpd
sudo rm -rf /var/www/html
sudo firewall-cmd --permanent --remove-service=http
sudo firewall-cmd --permanent --remove-service=https
sudo firewall-cmd --reload
sudo systemctl status httpd
sudo dnf remove -y php php-cli php-fpm php-json php-mysqlnd php-pdo php-xml php-mbstring



mysql -u root -e \"ALTER USER 'root'@'localhost' IDENTIFIED BY 'SuperHardP@ssword123';\"

FLUSH PRIVILEGES;
ALTER USER 'root'@'localhost' IDENTIFIED BY 'SuperHardP@ssword123';

copy ssh 
cat ~/.ssh/id_rsa.pub | ssh root@192.168.127.156 'mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys'

Sources used
database setup: https://stackoverflow.com/questions/41645309/mysql-error-access-denied-for-user-rootlocalhost
opensupports installation: https://docs.opensupports.com/guides/installation/
Chatgpt: help with debugging with some actions not working properly
white page: https://github.com/opensupports/opensupports/issues/1231
php7.4: https://idroot.us/install-php-7-4-centos-stream-9/

Timesheet 26july: 4;24 hours
Timesheet 26july: 5;33 hours
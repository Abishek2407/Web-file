 1 sudo yum update -y
 2 cat /etc/os-release
 **Install Apache**
 3 sudo dnf install -y httpd
 4 sudo systemctl start httpd
 5 sudo systemctl enable httpd
 **Install MariaDB (MySQL)Install MariaDB (MySQL)**
 6 sudo dnf install -y mariadb105-server
 7 sudo systemctl start mariadb
 8 sudo systemctl enable mariadb
 **Secure the DB**
 9 sudo mysql_secure_installation
 **Install PHP + extensions**
 10 sudo dnf install -y php php-mysqlnd php-cli php-common php-fpm php-json php-zip php-gd php-curl php-mbstring php-xml
 **Restart Apache:**
 11 sudo systemctl restart httpd
 **Test PHP**
 12 echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
 **Permissions (if needed)**
 13 sudo chown -R ec2-user:ec2-user /var/www

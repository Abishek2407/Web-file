## Update the System
```
 sudo yum update -y
```
 ## Install Apache
 
 sudo dnf install -y httpd
 sudo systemctl start httpd
 sudo systemctl enable httpd
 
 ## Install MariaDB (MySQL)Install MariaDB (MySQL)
 
 sudo dnf install -y mariadb105-server
 sudo systemctl start mariadb
 sudo systemctl enable mariadb
 
 ## Secure the DB
 
 sudo mysql_secure_installation
 
 ## Install PHP + extensions
 
 sudo dnf install -y php php-mysqlnd php-cli php-common php-fpm php-json php-zip php-gd php-curl php-mbstring php-xml
 
 ## Restart Apache
 
 sudo systemctl restart httpd
 
 ## Test PHP
 
 echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
 
 ## Permissions (if needed)
 
 sudo chown -R ec2-user:ec2-user /var/www

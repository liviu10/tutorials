# Create and configured Ubuntu web server:

## A. <u>Windows and Ubuntu - pre-configurations</u>:

1. Windows:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">       (install bitvise):</span> https://www.bitvise.com/ssh-client-download
    <span style="color:white; font-weight:normal;">(credentials to bitvise):</span> add ubuntu's username, password and IP address to bitvise
    <span style="color:white; font-weight:normal;">(add new virtual server):</span> forwarding > virtual servers > add new
    <span style="color:white; font-weight:normal;">      (add service port):</span> 80
    <span style="color:white; font-weight:normal;">     (add internal port):</span> 80
    <span style="color:white; font-weight:normal;"> (add ubuntu IP address):</span> ifconfig in Ubuntu terminal
    <span style="color:white; font-weight:normal;">          (add protocol):</span> TCP
    <span style="color:white; font-weight:normal;">   (common service port):</span> HTTP</pre>
    </span>

2. Ubuntu:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">       (enable firewall):</span> sudo ufw enable
    <span style="color:white; font-weight:normal;">          (open port 22):</span> sudo ufw allow 22
    <span style="color:white; font-weight:normal;">           (port status):</span> sudo ufw status
    <span style="color:white; font-weight:normal;">           (port status):</span> sudo ufw status
    <span style="color:white; font-weight:normal;">     (install net tools):</span> sudo apt-get install net-tools
    <span style="color:white; font-weight:normal;">   (ubuntu's ip address):</span> ifconfig
    <span style="color:white; font-weight:normal;">(install openssh server):</span> sudo apt install openssh-server
    <span style="color:white; font-weight:normal;"> (install apache server):</span> sudo apt-get install apache2
    <span style="color:white; font-weight:normal;">   (check apache status):</span> sudo /etc/init.d/apache2 status
    <span style="color:white; font-weight:normal;">   (check firewall apps):</span> sudo ufw app list
    <span style="color:white; font-weight:normal;">   (apache port for ssl):</span> sudo ufw allow 'Apache Full' for ssl connection</pre>
    </span>

## B. <u>Ubuntu - configurations</u>:

1. Activate project in '/var/www/html/':
   
    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">    (create new project):</span> sudo mkdir project_name
    <span style="color:white; font-weight:normal;">    (create config file):</span> cd /etc/apache2/site-available & nano project_name.conf
    <span style="color:white; font-weight:normal;">  (activate the project):</span> sudo a2ensite project_name.conf
    <span style="color:white; font-weight:normal;">  (activate config file):</span> sudo systemctl reload apache2</pre>
    </span>

2. Install PHP and MySQL:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">           (install php):</span> sudo apt-get install php php-cgi libapache2-mod-php php-mbstring php-all-dev
    <span style="color:white; font-weight:normal;">  (install MySQL server):</span> sudo apt-get install mysql-server
    <span style="color:white; font-weight:normal;"> (install php for mysql):</span> sudo apt-get install php7.4-mysql
    <span style="color:white; font-weight:normal;">    (install phpmyadmin):</span> sudo apt-get install phpmyadmin (select apache2 and dbconfig-common no)
    <span style="color:white; font-weight:normal;">          (access mysql):</span> sudo mysql (and enter your credentials)
    <span style="color:white; font-weight:normal;">  (root access to mysql):</span> SELECT user, authentication_string, host FROM mysql.user;
    <span style="color:white; font-weight:normal;">   (auth_string to root):</span> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password_here';
    <span style="color:white; font-weight:normal;">      (flush privileges):</span> FLUSH PRIVILEGES;
    <span style="color:white; font-weight:normal;">        (create db user):</span> CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
    <span style="color:white; font-weight:normal;">  (grant access to user):</span> GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;
    <span style="color:white; font-weight:normal;">    (enable apache mods):</span> sudo a2enmod php7.4
    <span style="color:white; font-weight:normal;">    (link to phpmyadmin):</span> sudo ln -s /etc/phpmyadmin/</pre>
    </span>

3. Install composer and laravel:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">      (install composer):</span> sudo apt install composer
    <span style="color:white; font-weight:normal;">       (install laravel):</span> composer install
    <span style="color:white; font-weight:normal;">        (install nodejs):</span> sudo apt install nodejs
    <span style="color:white; font-weight:normal;">(update and upgrade apt):</span> sudo apt update sudo apt upgrade
    <span style="color:white; font-weight:normal;">          (install curl):</span> sudo apt install -y curl
    <span style="color:white; font-weight:normal;">(download latest nodejs):</span> curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
    <span style="color:white; font-weight:normal;"> (install latest nodejs):</span> sudo apt install -y nodejs
    <span style="color:white; font-weight:normal;">           (install npm):</span> npm install
    <span style="color:white; font-weight:normal;">   (add .env to project):</span> set credentials to connect to the database
    <span style="color:white; font-weight:normal;">     (migrate & seed db):</span> php artisan migrate & php artisan db:seed</pre>
    </span>

4. User group and permissions:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">      (create new group):</span> sudo addgroup groupname
    <span style="color:white; font-weight:normal;">     (add user to group):</span> sudo adduser username groupname
    <span style="color:white; font-weight:normal;">   (add 664 permissions):</span> sudo find /var/www/html/ -type f -exec chmod 664 {} \;
    <span style="color:white; font-weight:normal;">   (add 775 permissions):</span> sudo find /var/www/html/ -type f -exec chmod 775 {} \; (BAD PRACTICE: sudo chmod 777 /var/www/html -R)
    <span style="color:white; font-weight:normal;">(set group id up & SGIG):</span> sudo find /var/www/html/ -type f -exec chmod g+s {} \;
    <span style="color:white; font-weight:normal;">      (set folder owner):</span> sudo chown -R username:groupname /var/www/html/
    <span style="color:white; font-weight:normal;">(set owner node_modules):</span> sudo chmod -R u+x node_modules/
    <span style="color:white; font-weight:normal;">     (set owner storage):</span> sudo chmod -R ugo+rw storage/
    <span style="color:white; font-weight:normal;">     ( set owner public):</span> sudo chmod -R ugo+rw public/
    <span style="color:white; font-weight:normal;"> (restart apache server):</span> sudo systemctl restart apache2</pre>
    </span>

5. Generate SSH key for github:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">  (verify if ssh exists):</span> sudo ls -l ~/.ssh/id_*.pub
    <span style="color:white; font-weight:normal;">      (generate ssh key):</span> sudo ssh-keygen -t rsa -b 4096 -C "your_email@domain.com"
    <span style="color:white; font-weight:normal;">    (verify ssh pairing):</span> sudo ls ~/.ssh/id_*
    <span style="color:white; font-weight:normal;">          (copy ssh key):</span> sudo cat ~/.ssh/id_rsa.pub</pre>
    </span>

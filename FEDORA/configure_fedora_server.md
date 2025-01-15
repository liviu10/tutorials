# Create and configured Fedora web server:

## A. <u>Windows and Fedora - pre-configurations</u>:

1. Windows:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">       (install bitvise):</span> https://www.bitvise.com/ssh-client-download
    <span style="color:white; font-weight:normal;">(credentials to bitvise):</span> add fedora's username, password and IP address to bitvise
    <span style="color:white; font-weight:normal;">(add new virtual server):</span> forwarding > virtual servers > add new
    <span style="color:white; font-weight:normal;">      (add service port):</span> 80
    <span style="color:white; font-weight:normal;">     (add internal port):</span> 80
    <span style="color:white; font-weight:normal;"> (add fedora IP address):</span> ip addr show in Fedora terminal
    <span style="color:white; font-weight:normal;">          (add protocol):</span> TCP
    <span style="color:white; font-weight:normal;">   (common service port):</span> HTTP</pre>
</span>

2. Fedora:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">       (enable firewall):</span> sudo firewall-cmd --permanent --add-service=ssh
    <span style="color:white; font-weight:normal;">          (open port 22):</span> sudo firewall-cmd --permanent --add-port=22/tcp
    <span style="color:white; font-weight:normal;">           (port status):</span> sudo firewall-cmd --list-all
    <span style="color:white; font-weight:normal;">     (install net tools):</span> sudo dnf install net-tools
    <span style="color:white; font-weight:normal;">   (Fedora's ip address):</span> ip addr show
    <span style="color:white; font-weight:normal;">(install openssh server):</span> sudo dnf install openssh-server
    <span style="color:white; font-weight:normal;"> (install apache server):</span> sudo dnf install httpd
    <span style="color:white; font-weight:normal;">   (check apache status):</span> sudo systemctl status httpd
    <span style="color:white; font-weight:normal;">   (apache port for ssl):</span> sudo firewall-cmd --permanent --add-service=https</pre>
</span>

## B. <u>Fedora - configurations</u>:

1. Activate project in '/var/www/html/':
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">    (create new project):</span> sudo mkdir /var/www/html/project_name
    <span style="color:white; font-weight:normal;">    (create config file):</span> cd /etc/httpd/conf.d/ & sudo nano project_name.conf
    <span style="color:white; font-weight:normal;">  (activate the project):</span> sudo systemctl reload httpd</pre>
</span>

2. Install PHP and MySQL:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">           (install php):</span> sudo dnf install php php-cli php-fpm php-mysqlnd php-xml php-mbstring php-json php-zip php-gd php-curl
    <span style="color:white; font-weight:normal;">  (install MySQL server):</span> sudo dnf install mysql-server
    <span style="color:white; font-weight:normal;">    (install phpmyadmin):</span> sudo dnf install phpmyadmin (select apache2 and dbconfig-common no)
    <span style="color:white; font-weight:normal;">          (mysql status):</span> sudo systemctl status mysqld
    <span style="color:white; font-weight:normal;">           (mysql start):</span> sudo systemctl start mysqld
    <span style="color:white; font-weight:normal;">  (mysql enable on boot):</span> sudo systemctl enable mysqld
    <span style="color:white; font-weight:normal;">          (access mysql):</span> sudo mysql (and enter your credentials)
    <span style="color:white; font-weight:normal;">  (root access to mysql):</span> SELECT user, authentication_string, host FROM mysql.user;
    <span style="color:white; font-weight:normal;">   (auth_string to root):</span> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password_here';
    <span style="color:white; font-weight:normal;">      (flush privileges):</span> FLUSH PRIVILEGES;
    <span style="color:white; font-weight:normal;">        (create db user):</span> CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
    <span style="color:white; font-weight:normal;">  (grant access to user):</span> GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;
    <span style="color:white; font-weight:normal;">    (link to phpmyadmin):</span> sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin</pre>
</span>

3. Install composer and laravel:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">      (install composer):</span> sudo dnf install composer
    <span style="color:white; font-weight:normal;">       (install laravel):</span> composer create-project --prefer-dist laravel/laravel project_name
    <span style="color:white; font-weight:normal;">        (install nodejs):</span> sudo dnf install nodejs
    <span style="color:white; font-weight:normal;">   (add .env to project):</span> set credentials to connect to the database
    <span style="color:white; font-weight:normal;">     (migrate & seed db):</span> php artisan migrate && php artisan db:seed
    <span style="color:white; font-weight:normal;">     (microsoft gpg key):</span> sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    <span style="color:white; font-weight:normal;"> (add vscode repository):</span> sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1" > /etc/yum.repos.d/vscode.repo'
    <span style="color:white; font-weight:normal;">        (install vscode):</span> sudo dnf install code</pre>
</span>

4. User group and permissions:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">      (create new group):</span> sudo groupadd groupname
    <span style="color:white; font-weight:normal;">     (add user to group):</span> sudo usermod -aG groupname username
    <span style="color:white; font-weight:normal;">   (add 664 permissions):</span> sudo find /var/www/html/ -type f -exec chmod 664 {} \;
    <span style="color:white; font-weight:normal;">   (add 775 permissions):</span> sudo find /var/www/html/ -type d -exec chmod 775 {} \; (BAD PRACTICE: sudo chmod 777 /var/www/html -R)
    <span style="color:white; font-weight:normal;">(set group id up & SGIG):</span> sudo find /var/www/html/ -type d -exec chmod g+s {} \;
    <span style="color:white; font-weight:normal;">      (set folder owner):</span> sudo chown -R username:groupname /var/www/html/
    <span style="color:white; font-weight:normal;"> (restart apache server):</span> sudo systemctl restart httpd</pre>
</span>

5. Generate SSH key for github:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">  (verify if ssh exists):</span> ls -l ~/.ssh/id_*.pub
    <span style="color:white; font-weight:normal;">      (generate ssh key):</span> ssh-keygen -t rsa -b 4096 -C "your_email@domain.com"
    <span style="color:white; font-weight:normal;">    (verify ssh pairing):</span> ls ~/.ssh/id_*
    <span style="color:white; font-weight:normal;">          (copy ssh key):</span> cat ~/.ssh/id_rsa.pub</pre>
</span>

6. Mount share folders in fedora:
<span style="color:red; font-weight:bold;">
    <pre>
    <span style="color:white; font-weight:normal;">(check if vboxsf is loaded):</span> lsmod | grep vboxsf
    <span style="color:white; font-weight:normal;">     (manually load vboxsf):</span> sudo modprobe vboxsf
    <span style="color:white; font-weight:normal;">       (mount share folder):</span> sudo mount -t vboxsf [directory_name] /media/[shared_folder_name]</pre>
</span>
# CasaDaMah

# Wordpress
Configurar no Ubuntu: (TODO)

# Configurar Wordpress no Virtual Server Amazon EC2:
* Lançar uma Instância Amazon Linux AMI 2015.03 (HVM), SSD Volume Type
Seguir os passos de criação...
Não perder o par de chaves (key pair, arquivo com extensão .pem)

* Acessar via SSH:
Open an SSH client.
Locate your private key file (glandre-new-key.pem).
The wizard automatically detects the key you used to launch the instance.
Your key must not be publicly viewable for SSH to work.

Use this command if needed:
chmod 400 glandre-new-key.pem

Example:
ssh -i glandre-new-key.pem ec2-user@ip-address

* Instalar Wordpress:

(root)# yum update
(root)# yum install httpd php php-mysql mysql-server
(root)# service mysqld start
(root)# mysqladmin -uroot create casadamah
(root)# cd /var/www/html/
(root)# wget http://wordpress.org/latest.tar.gz
(root)# tar -xzvf latest.tar.gz 
(root)# mysql_secure_installation
(root)# mv wordpress casadamah
(root)# rm -f latest.tar.gz 
(root)# cd casadamah/
(root)# mv wp-config-sample.php wp-config.php
(root)# vi wp-config.php 

# Vagrant:
Box utilizada: hashicorp/precise64 (padrÃ£o do https://atlas.hashicorp.com)

# Backup automÃ¡tico do Banco de dados
Vagrantfile adaptado para fazer backup do banco de dados a cada "vagrant up"
 - utilizando script da pasta db/backup-developer-db.sh
Para restaurar o banco anterior, basta executar (logado na vm):
$ sh /vagrant/db/restore-developer-db.s

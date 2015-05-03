# CasaDaMah

# Wordpress
Configurar no Ubuntu: (TODO)

# Vagrant:
Box utilizada: hashicorp/precise64 (padrão do https://atlas.hashicorp.com)

# Backup automático do Banco de dados
Vagrantfile adaptado para fazer backup do banco de dados a cada "vagrant up"
 - utilizando script da pasta db/backup-developer-db.sh
Para restaurar o banco anterior, basta executar (logado na vm):
$ sh /vagrant/db/restore-developer-db.s

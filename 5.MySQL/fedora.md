MySQL
---

Faça o download:       
[http://dev.mysql.com/downloads/mysql/](http://dev.mysql.com/downloads/mysql/)

O pacote de download é __Linux - Generic (glibc 2.5) (x86, 64-bit), Compressed TAR Archive__,
no qual o nome do arquivo é mysql-5.6.17-linux-glibc2.5-x86_64.tar.gz.

Tome cuidado ao fazer o download, existem diversos pacotes disponíveis, mudando somente
o nome do arquivo no site.

### Execute

    # groupadd mysql
    # useradd -g mysql mysql
    # cd /usr/local
    # tar zxvf caminho/do/arquivo/mysql-<versão>-<so>.tar.gz
    # ln -s /mysql-<versão>-<so> mysql
    # cd mysql
    # chown -R mysql .
    # chgrp -R mysql .
    # scripts/mysql_install_db --user=mysql
    # chown -R root .
    # chown -R mysql data


_Iniciar o MySQL_

    # bin/mysqld_safe --user=mysql &

_Finalizar o MySQL_

    # bin/mysqladmin -u root -p shutdown

_Alterar senha_

    # ./mysqladmin -u root password nova_senha


Para incluir os executáveis no PATH, acrescente no arquivo `/etc/profile` a seguinte linha:

    export PATH=$PATH:/usr/local/mysql/bin


Correção do erro: 'Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)'
Check that mysqld is running and that the socket: '/tmp/mysql.sock' exists!

Entre no arquivo `/etc/my.cnf` e adicione as linhas:

    [mysqladmin]
    socket=/var/lib/mysql/mysql.sock

# ObligatorioJulio2024
Trabajo obligatorio correspondiente al Taller de Linux Julio 2024

- Para este trabajo se utilizan 1 centos strems 9 GUID (controller), 1 centos server y 1 ubuntu server.

- Se deben instalar los paquetes y librerias necesarias para utilizar GIT y Ansible. Se debe crear una clave SSH en el server centos GUID y copiar a los demas servidores. 

$ sudo dnf install git

$ sudo ssh-keygen

$ sudo ssh-copy-id ip-server-centos
$ sudo ssh-copy-id ip-server-ubuntu

- Copiar la clave ssh generada a su repositorio GitHub

- Clonar repositorio con la clave creada.

$ sudo dnf install pip
$ pip install pipx
$ pipx ensurepath
$ pipx install ansible-core

$ pipx inject ansible-core argcomplete
$ pipx inject ansible-core ansible-lint
$ activate-global-python-argcomplete –user

$ source /home/sysadmin/.bash_completion

- Se deben instalar en el server controller los requerimientos para el correcto funcionamiento de los playbook

$ ansible-galaxy collection install -r collections/requirements.yml

- Ejecutar playbook para configurar firewall en el servidor ubuntu

$ ansible-playbook playbooks/ubuntu_firewall_ufw.yml --ask-become-pass

- En el server centos instalar Java

$ ansible-playbook playbooks/install_Java.yml --ask-become-pass

- En el server centos instalar Tomcat

$ ansible-playbook playbooks/install_tomcat.yml --ask-become-pass
$ ansible-playbook playbooks/open_port_tomcat.yml --ask-become-pass

- Instalar mariadb en el servidor ubuntu

- En el servidor centos instalamos los requerimientos:

$ sudo dnf install mysql -y
$ pipx inject ansible-core pymysql

- En el servidor ubuntu instalamos los requerimientos:

$ ansible-playbook playbook/install_module_sql.yml --ask-become-pass

- Ejecutamos el playbook para instalar mariadb en el server ubuntu

$ ansible-playbook playbooks/install_database.yml --ask-become-pass

$ ansible-playbook playbooks/ubuntu_firewall_ufw.yml --ask-become-pass

- Playbook para instalar el Web Server

- Ejecutamos el playbook

$ ansible-playbook playbooks/install_webserver.yml --ask-become-pass






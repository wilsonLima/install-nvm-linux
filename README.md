install-nvm-linux
=========

Role do Ansible com os passos para a instalação do NVM em distribuições Linux.

Distribuições Suportadas pela Role
------------

- Fedora 37 ou superior
- Linux Mint 21 ou superior
- openSUSE Leap 15.4 ou superior
- openSUSE Tumbleweed
- Ubuntu 22.10 ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
  
- deps: Instala os pacotes de dependências.
- nvm: Instala o Docker.


Variáveis da Role 
--------------

- nvm_version: versão do NVM, valor padrão: "v0.39.5" .


Dependências da Role 
--------------

Linux Mint e Ubuntu:

- openssh-server. Ex.: sudo apt install openssh-server


Exemplo de Inventario
----------------

Exemplo de arquivo de hosts: pasta_invetario/hosts

    [NOME]
    IP ansible_connection=ssh ansible_ssh_user=USUARIO ansible_ssh_pass=SENHA_URUARIO ansible_become_pass=SENHA_ROOT


Especificar interpretador python 3: pasta_invetario/group_vars/all

    ansible_python_interpreter: "/usr/bin/python3"


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - install-nvm-linux

Exemplo de uso da Role com variáveis:

    - hosts: desktop
      roles:
         - { role: install-nvm-linux, nvm_version: "v0.39.5" }


Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "nvm" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, nvm"


License
-------

MIT
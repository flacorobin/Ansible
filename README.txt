Ansible exmaple playbook that runs 3 roles:
 -basic-build
  Installs basic tools on all servers
  
 -reverse-proxy
  Installs Apache, copies the configuration to work as a reverse proxy, starts and enables Apache

 -website
  Installs Apache, copies a small site to /var/www/html folder, starts and enables Apache


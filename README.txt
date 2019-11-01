Ansible example playbook that runs 3 roles:
 -basic-build
  Installs basic tools on all servers

 -reverse-proxy
  Installs Apache, copies the configuration to work as a reverse proxy, starts and enables Apache

 -website
  Installs Apache, copies a small site to /var/www/html folder, starts and enables Apache

This ansible playbook expects the following:
-Webserver and AppServer are recheable, resolvable via DNS or hosts.
-Ansible computer can access both servers type via ssh passwordless
-User on servers us able to elevate via sudo. If not run ansible-playbook -K playbook.yml (then input root password)

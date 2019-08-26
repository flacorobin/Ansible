Changes to do for reverse proxy:
Install httpd both web and app server

On app server host a test page:
/var/www/html/index.html
<html>
<head><title>Test page for Backend server</title></head>
<body>This is a simple test page hosted on backend server.</body>
</html>

On Web server:
	- Add modules to the configuration on /etc/httpd/conf/httpd.conf
	  LoadModule proxy_module modules/mod_proxy.so
          LoadModule proxy_http_module modules/mod_proxy_http.so
	
	- Add reverse proxy configuration on /etc/httpd/conf/httpd.conf

#<VirtualHost *:80>

#ProxyPreserveHost On
ProxyPass / http://172.31.83.45/
ProxyPassReverse / http://172.31.83.45/

#</VirtualHost>


By default, SELinux prevents Apache from initiating outbound connections, so it is unable to proxy requests to Bitbucket Server.
Run this to allow

/usr/sbin/setsebool -P httpd_can_network_connect 1




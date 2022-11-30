# nginx_start
erste Schritte mit nginx auf einem Ubuntu Server
**KISS-Prinzip (englisch Keep it simple and stupid)**
>ein Grundsatz, den ich verfolge: eine einzige Anwendung auf einem Server in einer VM (virtuellen Maschine)
## Grundsätzliches
### nginx Dateien und Verzeichnisse
- /etc/nginx
- /etc/nginx/nginx.conf
- /etc/nginx/conf.d/
- /var/log/nginx
### nginx Kommandos
- nginx -h
- nginx -v
- nginx -V
- nginx -t
- nginx -T
- nginx -s signal (stop, quit, reload, reopen)
## Installations- und Konfigurationsbeispiel mit rtmp-Modul und PHP
```
sudo apt install nginx
sudo apt install libnginx-mod-rtmp
sudo apt install php-fpm
```

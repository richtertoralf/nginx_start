# nginx_start
erste Schritte mit nginx auf einem Ubuntu Server
>KISS-Prinzip (englisch: Keep it simple and stupid)  
>Grundsatz: nur eine einzige Webanwendung auf einem Server in einer VM (virtuellen Maschine)
## Grundsätzliches
### nginx Dateien und Verzeichnisse
- /etc/nginx  
  Standardkonfigurationsverzeichnis für den NGINX-Server
- /etc/nginx/nginx.conf  
  Die Datei /etc/nginx/nginx.conf ist der Standardkonfigurationseinstiegspunkt, der von der NGINX-Dienst verwendet wird. Diese Konfigurationsdatei legt globale Einstellungen und Verweise auf andere NGINX-Konfigurationsdateien fest.
- /etc/nginx/conf.d/  
Das Verzeichnis /etc/nginx/conf.d/ enthält die Standardkonfigurationsdatei des HTTP-Servers. Dateien in diesem Verzeichnis, die auf .conf enden, werden in den Top-Level http-Block innerhalb der Datei /etc/nginx/nginx.conf aufgenommen. In einigen Anleitungen wird für weitere Konfigurationsdateien der Ordner sites-enabled verwendet und die Konfigurationsdateien werden von dem Ordner site-available verlinkt; diese Konvention gilt als veraltet.
- /var/log/nginx  
  Das Verzeichnis /var/log/nginx/ ist der Standardspeicherort für Logdateien. In diesem Verzeichnis gibt es eine access.log-Datei und eine error.log-Datei. Das Zugriffsprotokoll enthält einen Eintrag für jede Anfrage, die NGINX bedient. Die Fehlerprotokolldatei enthält Fehlerereignisse und Debug-Informationen, wenn das Debug-Modul aktiviert ist.
### nginx Kommandos
- nginx -h -> zeigt Hilfen an
- nginx -v -> zeigt die NGINX Version
- nginx -V -> zeigt die NGINX-Version, Build-Informationen und Konfigurationsargumente an
- nginx -t -> testet die NGINX Konfiguration und zeigt eventuelle Fehler an
- nginx -T -> testet die NGINX Konfiguration und zeigt die überprüfte Konfiguration an
- nginx -s signal (stop, quit, reload, reopen)  
  Das stop-Signal beendet den NGINX-Prozess sofort. Das quit-Signal stoppt den NGINX-Prozess, nachdem er die Verarbeitung laufender Anfragen beendet hat. Das reload-Signal lädt die Konfiguration neu. Das reopen-Signal weist NGINX an, die Logdateien erneut zu öffnen.  
## Installations- und Konfigurationsbeispiel mit rtmp-Modul und PHP
```
# NGINX:
sudo apt install nginx
# Das RTMP-Modul wird für den Einsatz als Streaming-Server benötigt:
sudo apt install libnginx-mod-rtmp
# PHP wird für dynamische Webseiteninhalte benötigt:
sudo apt install php-fpm
```
Ohne an der Konfiguration etwas verändern zu müssen, funktioniert jetzt bereits der Webserver. Die statischen Inhalte befinden sich im Verzeichnis `/var/www/html`.

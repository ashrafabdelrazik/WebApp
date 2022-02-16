# WebApp
This repository contains the scripts and the configuration files for my very first web app.

# OverView
Mikkawy.tk is just a WordPress site built on four Linux servers

- Nginx Load balancer (Ubuntu 20):
Nginx Load Balancer distributes the incoming traffic across a group of backend servers, in my case, it's going to distribute the traffic across App Server 1 & App Server 2. The Load Balancing method used is ip_hash to guarantee that requests from the same address get to the same server unless it's not available.
- App Server 1 (Debian 10) & App Server 2 (Debian 10):
the servers that host the WordPress application files via Nginx and it's configured to accept http/s requests only from the Load Balancer Server, These servers backup their data daily using crontab and the backup script located at '/usr/local/scripts/backup' and it synchronizes the upload directories (/var/www/html/wp-content/uploads/) on both servers using rsync.
- MySQL Server (Ubuntu 20): The fourth server and it's hosting the database, it's configured to accept requests on port 3306 only from AppServer1 & AppServer 2 and it backup its data daily at 00:00 using crontab and the backup script located at 'usr/local/scripts/backup'

# Demo:
https://www.mikkawy.tk/

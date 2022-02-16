# Additional Details

- Rsync: the rsync process is happening between app server one and app server two every one minute using crontab, and the user responsible for the rsync process is `www-data`, the command used is `rsync -pogtrv --append -e 'ssh -p 8022' www-data@<app_server_1_ip>:/var/www/html/wp-content/uploads/* /var/www/html/wp-content/uploads/`

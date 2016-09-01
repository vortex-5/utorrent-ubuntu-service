# Utorrent Systemd Script #

### Customize utorrent-service ###
1. Copy script/utorrent-service to a directory you want the script to live in your system.
2. Open utorrent-service and edit UTORRENT_PATH= to point to where your utorrent utserver file is.
3. Optionally customize utorrent.log location this must be writable by the user you wish utorrent to run as.

### Customize utorrent.service ###
1. Open lib/systemd/system/utorrent.service.
2. Select the user account that you will be running the utorrent service as by editing User=MyUser.
3. Change ExectStart= to point to the location of utorrent-service above.
4. Ensure utorrent-service is executable by the user you have selected.
4. copy lib/systemd/system/utorrent.service to /lib/systemd/system/utorrent.service

### Enable the service ###
1. execute `sudo systemctl daemon-reload` which will cause the new service to be detected.
2. execute `sudo systemctl enable utorrent.service` this will install the service and cause it to auto start on system startup. If you do not wish to start utorrent on system startup you can change the `enable` to `disable`.

If you want to start the service without rebooting the system you can use `sudo systemctl start utorrent.service`. You can also stop the service at any time by using `sudo systemctl stop utorrent.service`.

Please post in the issue track if you encouter issues.
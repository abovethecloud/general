# Tips and tricks to remember

##### rsync [options] ...:
A better way to transfer files even remotely, due to the ability to restart after a lost connection. Better than scp and with more options.
Example:

    $ rsync -a --ignore-existing --progress claudio@192.168.7.69:"'/Volumes/My Book 3/qBittorrent downloads/Black.Panther.2018.1080p.BluRay.x264-SPARKS'" /Volumes/Compatible/Movies

Note that there are double quotes around the remote path. This is necessary since the string has to be parsed twice: locally and remotely.



##### nmap -sn ...:
Command to scan the network and list all connected devices. Useful to list also the devices connected via OpenVPN (if the respective network are scanned, such as 10.8.0.0/24 or 10.8.1.0/24).
Note that given the reduced amount of addresses per OpenVPN instance, a mask of 29 should be sufficient.
Example:

    $ nmap -sn 192.168.7.0/24 10.8.0.0/29 10.8.1.0/29

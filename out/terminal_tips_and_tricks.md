# Terminal commands to remember

##### rsync [options] ...:
A better way to transfer files even remotely, due to the ability to restart after a lost connection. Better than scp and with more options.
Example:

    $ rsync -vazhP claudio@192.168.7.69:"'/Volumes/My Book 3/qBittorrent downloads/FILE_OR_DIRECTORY'" /Volumes/Compatible/DESTINATION

Note that there are double quotes around the remote path. This is necessary since the string has to be parsed twice: locally and remotely. To transfer a directory, do not append a "/" at the end of the path. Doing so would result in transferring only the contents of such directory.
Also, the options are:

    [-n : DRY RUN. See what would happen]
    -v : Verbose
    -a : archive mode; same as -rlptgoD (recursive, etc..)
    -z : compress (useful with a slow connection)
    -h : human-readable output
    -P : shows progress and preserves partial transfers
    (-u : skip files that are newer on the destination)
    (--ignore-existing: skips the update of files that already exist on the destination)


##### nmap -sn ...:
Command to scan the network and list all connected devices. Useful to list also the devices connected via OpenVPN (if the respective network are scanned, such as 10.8.0.0/24 or 10.8.1.0/24).
Note that given the reduced amount of addresses per OpenVPN instance, a mask of 29 should be sufficient.
Example:

    $ nmap -sn 192.168.7.0/24 10.8.0.0/29 10.8.1.0/29

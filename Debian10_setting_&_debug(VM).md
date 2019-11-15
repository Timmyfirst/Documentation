# DEBIAN 10 setting and debug for VM

## ** WARNING: It's necessary to attribute +10Go to VM disk space **

## -- SETTING --

### Add user to sudoers
With root
> nano /etc/group
at sudo line add user 

### Edit sources
> sudo nano /etc/apt/sources.list

(Help link)
https://wiki.debian.org/SourcesList?action=show&redirect=sources.list

### Install curl
> sudo apt-get install curl

### To permit sshfs (ssh too)
- VM: 
    * > sudo apt-get install openssh-server
    * configuration de la VM: permettre la promiscuité

- Hôte: 
    * > sudo apt-get install sshfs
    * > sudo sshfs -o allow_other $USER@XXX.XXX.XXX.XXX:/ $MOUNT_POINT

### Check open ports
- TCP:
> sudo nmap -sT -O localhost

- UDP:
> sudo nmap -sU -O localhost

### Open port
Install ufw:
> sudo apt-get install ufw

 


### Install Nodejs
https://github.com/nodesource/distributions

### Install Mongo
https://docs.mongodb.com/manual/tutorial/install-mongodb-on-debian/

Enable mongo boot service
> sudo systemctl enable mongod

### Install VUE CLI
> sudo npm install -g @vue/cli

## -- DEBUG -- 

### Logs access
> nano /var/log/

### Change owner of file/directory
> chown $USER $FILE_OR_DIRECTORY

### Change rights on file
> chmod NNN $FILE_OR_DIRECTORY 

### Partition management
- Prérequis: ajouter /sbin dans le $PATH (soit dans ~.profile, soit ~/.bash_profile etc.)

fdisk | df

### List groups (that's funny)
> groups

### Autoremove useless packages
> sudo apt autoremove

### Remove packages and dependencies
> sudo apt remove --purge $PAQUET

### List all process
> ps -aux



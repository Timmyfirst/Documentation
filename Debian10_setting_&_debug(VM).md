# DEBIAN 10 setting and debug for VM

## ** WARNING: It's necessary to attribute +10Go to VM disk space **

## -- SETTING --

### Edit sources
nano /etc/apt/sources.list

(Help link)
https://wiki.debian.org/SourcesList?action=show&redirect=sources.list

### To permit sshfs (ssh too)
- VM: 
    * > sudo apt-get install openssh-server
    * configuration de la VM: permettre la promiscuité

- Hôte: 
    * sudo apt-get install sshfs
    * sudo sshfs -o allow_other $USER@XXX.XXX.XXX.XXX:/ $MOUNT_POINT

### Install Nodejs

### Install Mongo

## -- DEBUG -- 

### Logs access
nano /var/log/

### Change owner of file/directory
chown $USER $FILE_OR_DIRECTORY

### Change rights on file
chmod NNN $FILE_OR_DIRECTORY 

### Partition management
- Prérequis: ajouter /sbin dans le $PATH (soit dans ~.profile, soit ~/.bash_profile etc.)

fdisk | df

### List groups (that's funny)
groups

### Autoremove useless packages
sudo apt autoremove

### Remove packages and dependencies
sudo apt remove --purge $PAQUET

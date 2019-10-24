# DEBIAN 10 setting and debug for VM

## -- SETTINGS --

### Editer les sources
nano /etc/apt/sources.list

(en s'aidant du lien)
https://wiki.debian.org/SourcesList?action=show&redirect=sources.list

### Permettre la synchronisation sshfs
- VM: 
    * sudo apt-get install openssh-server

- Hôte: 
    * sudo apt-get install sshfs
    * sudo sshfs -o allow_other user@192.168.43.9:/ /mnt/application-test

## -- DEBUG -- 

### Accéder aux logs
nano /var/log/

### Changer le propriétaire d'un fichier/dossier
chown $USER $FILE_OR_DIRECTORY

### Changer les droits sur un fichier
chmod NNN $FILE_OR_DIRECTORY 

### Gérer les partitions
- Prérequis: ajouter /sbin dans le $PATH (soit dans ~.profile, soit ~/.bash_profile etc.)

fdisk | df

### Lister les groupes
groups

### Supprimer les paquets inutiles automatiquement
sudo apt autoremove

### Supprimer les paquets et leurs dépendances
sudo apt remove --purge $PAQUET

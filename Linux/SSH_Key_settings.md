# SSH Key settings



## SSH Key between machinas - Generation

### *** Then you be able to connect on remote server without password

### Create directory for ssh keys if it doesn't exist
> mkdir ~/.ssh

### Generate rsa keys
> ssh-keygen -t rsa -C "mail@mail.com"

### Check generated keys
> cd ~/.ssh
ls -la

You should find "id_rsa" (private key) and "id_rsa.pub" (public key)

## SSH Key between machinas - Copy

### Copy the local public key on remote server
> scp ~/id_rsa.pub user@192.168.0.1:/home/user/.ssh/authorized_key

### Set permission on remote ssh directory and key
> ssh user@192.168.0.1 "chmod 700 .ssh; chmod 640 .ssh/authorized_key"

Now you can connect without password

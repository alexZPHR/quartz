Create_Date : 30/11/2022
MOC :  [[RHCSA]]
Tags : #Linux #RHCSA #SSH

----------------------------------

##### Création de la paire de clé

La commande ssh-keygen permet de générer une paire de clé RSA

```console
[user@host ~]$ ssh-keygen 
Generating public/private rsa key pair. 
Enter file in which to save the key (/home/user/.ssh/id_rsa): Enter 
Created directory '/home/user/.ssh'. Enter passphrase (empty for no passphrase): Enter Enter same passphrase again: Enter 
Your identification has been saved in /home/user/.ssh/id_rsa. 
Your public key has been saved in /home/user/.ssh/id_rsa.pub. 
The key fingerprint is: 
SHA256:vxutUNPio3QDCyvkYm1 user@host.lab.example.com 
The key's randomart image is: 
+---[RSA 2048]----+ 
|                 |
|    .      .     |
|   o o      o    |
| . = o  o   .    |
| o + = S  E .    |
| ..O o + *  +    |
|.+% O .  + B .   |
|=*oO  .  . + *   |
|++.   .    +.    |
+----[SHA256]-----+
```

###### <span style="color:#858585;font-weight: bold;">Les options disponibles:</span>
	-t : Type de clé (rsa, dsa, ecdsa...)
	-b : Taille de la clé
	-f : Fichier de sortie



##### Copie de la clé public sur le serveur distant

Une fois la paire de clé créée, il faut copier la clé public sur le serveur. Pour cela, on utilise la commande ssh-copy-id

```console
[user@host ~]$ ssh-copy-id -i .ssh/key-with-pass.pub user@remotehost
user@remotehost's password:  
Number of key(s) added: 1
```



##### Connexion sur le serveur avec la clé SSH

Pour se connecter, il suffit de rajouter l'option -i vers la clé privée

```console
[user@host ~]$ ssh -i .ssh/key-with-pass user@remotehost 
Enter passphrase for key '.ssh/key-with-pass': 
...output omitted... 
[user@remotehost ~]$
```


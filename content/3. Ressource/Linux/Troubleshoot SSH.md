Create_Date : 30/11/2022
MOC : [[RHCSA]]
Tags : #Linux #RHCSA #SSH #Troubleshoot

----------------------------------

## Identifier les informations à la connexion

Dans un premier temps, tenter une connexion ssh avec l'option -v pour afficher chaque étape de la connexion.

```console
[user@host ~]$ ssh -v user@remotehost 
OpenSSH_8.7p1, OpenSSL 3.0.1 14 Dec 2021    (1)
debug1: Reading configuration data /etc/ssh/ssh_config    (2)
debug1: Reading configuration data /etc/ssh/ssh_config.d/01-training.conf 
debug1: /etc/ssh/ssh_config.d/01-training.conf line 1: Applying options for * 
debug1: Reading configuration data /etc/ssh/ssh_config.d/50-redhat.conf 
...output omitted... 
debug1: Connecting to remotehost [192.168.1.10] port 22.    (3)
debug1: Connection established. ...output omitted... 
debug1: Authenticating to remotehost:22 as 'user'    (4)
...output omitted...
debug1: Authentications that can continue: publickey,gssapi-keyex,gssapi-withmic,password    (5)
...output omitted...
debug1: Next authentication method: publickey    (6)
debug1: Offering public key: /home/user/.ssh/id_rsa RSA
 SHA256:hDVJjD7xrUjXGZVRJQixxFV6NF/ssMjS6AuQ1+VqUc4    (7)
debug1: Server accepts key: /home/user/.ssh/id_rsa RSA
 SHA256:hDVJjD7xrUjXGZVRJQixxFV6NF/ssMjS6AuQ1+VqUc4    (8)
Authenticated to remotehost ([192.168.1.10]:22) using "publickey".
...output omitted...
```

- (1): OpenSSH and OpenSSL versions
- (2): Fichier de configuration OpenSSH
- (3): Connexion sur l'host distant
- (4): Authentification sur l'host distant
- (5): Tentative d'authentification
- (6): Tentative d'authentification avec la clé privée
- (7): Utilisation de la clé privée
- (8): L'host distant accepte la clé privée


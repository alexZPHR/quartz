Create_Date : 30/11/2022
MOC : [[RHCSA]]
Tags : #Linux #RHCSA #SSH 

----------------------------------

Un fichier ~/.ssh/config peut être créé pour charger des profils de connexion SSH

**Exemple de fichier:**
```console
[user@host ~]$ cat ~/.ssh/config 
host servera 
	HostName servera.example.com 
	User usera 
	IdentityFile ~/.ssh/id_rsa_servera 

host serverb 
	HostName serverb.example.com 
	User userb 
	Port 2222
```

###### <span style="color:#858585;font-weight: bold;">Les options communes disponibles:</span>
	Hostname : Host cible
	User : Utilisateur à utiliser
	IdentityFile : Clé privée à utiliser
	Port : Port spécifique à utiliser
	ProxyHost : Utilisation d'un proxy




[Doc détaillé](https://man.openbsd.org/OpenBSD-current/man5/ssh_config.5)



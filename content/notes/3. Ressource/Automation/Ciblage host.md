Create_Date : 29/11/2022
MOC : [[Automation]]
Tags : #Salt #SaltStack #CheatSheet #target #automation #automatisation 

----------------------------------

Note concernant le ciblage d'un host ou d'un groupe d'host lors de l'appel de la commande salt



### Sélection à partir d'une IP ou d'une plage IP

###### Pour une IP
```console
salt -S 192.168.0.42 test.ping
```
###### Pour une plage IP
```console
salt -S 192.168.0.0/24 test.ping
```
<br>

### Sélection d'une liste définie d'host

```console
salt -L host1,host2,host3 test.ping
```
<br>

### Sélection avec une regex

```console
salt -E '^[m|M]in.[e|o|u]n$' test.ping
```
<br>

### Sélection à partir d'une information définie

```console
salt -G 'os:Ubuntu' test.ping
```
```console
salt -G 'ip_interfaces:eth0:192.168.11.38'
```
<br>

### Sélection complexe à partir d'une information définie

```console
salt --grain-pcre 'os:red(hat|flag)' test.ping
```
<br>

### Sélection à partir d'un pillar

```console
salt -I 'my_var:my_val' test.ping
```

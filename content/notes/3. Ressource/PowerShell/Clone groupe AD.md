Create_Date : 29/11/2022
MOC : [[PowerShell]]
Tags : #PowerShell #AD #ActiveDirectory

----------------------------------

Récupération des utilisateurs d'un groupe AD pour l'ajouter dans un nouveau groupe

```Powershell
Get-ADGroupMember "GROUPE SOURCE" | Foreach-Object {
    $User = Get-ADUser -Identity $_
    $Group = Get-ADGroup -Identity "GROUPE DESTINATION"
    Add-ADGroupMember -Identity $Group -Members $User
}
```
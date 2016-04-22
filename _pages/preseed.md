---
title: Preseed
categories: [Divers]
---


# Identifier les items preseed associés aux questions du debian installer

Le fichier /var/log/installer/cdebconf/templates.dat contient toutes les questions dans toutes les langues posées par le debian-installer, avec le nom utilisable dans preseed et le type.

Par exemple si on cherche à répondre automatiquement à la question "Continue installation without /boot partition?" il suffit de la chercher dans le fichier :

```
fgrep -B2 "Continue installation without /boot partition?" /var/log/installer/cdebconf/templates.dat
```

```
Name: partman-auto-lvm/no_boot
Type: boolean
Description: Continue installation without /boot partition?
```

Il faut donc ajouter au fichier preseed : 

```
d-i partman-auto-lvm/no_boot boolean true
```


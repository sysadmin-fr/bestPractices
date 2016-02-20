---
categories: [obfusquer]
title: Obfusquer  les services
--- 

# Obfusquer les services

## Base de données

### Mysql

On ne peut camoufler des informations sur Mysql. Le client a besoin de connaître la verion serveur afin de communiquer avec lui.
Sources :

- http://lists.mysql.com/mysql/226578
- http://bugs.mysql.com/bug.php?id=58152

## Serveurs web

### Apache 

> ServerSignature Off
> ServerTokens Prod


## Serveurs d'application

### PHP

> expose_php = Off


## SSH

### OpenSSH

http://www.openssh.com/faq.html#2.14
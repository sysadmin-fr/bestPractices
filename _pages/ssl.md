---
categories: [SSL]
title: Configuration de SSL
---

# Généralités

## Configuration des ciphers

  * Voir https://wiki.mozilla.org/Security/Server_Side_TLS#Recommended_configurations

## OSCP Stapling

L'OSCP est un protocole en ligne permettant de vérifier le statut de révocation d'un certificat. Il est normalement effectué par le client (celui qui veut vérifier le certificat sur lequel il va), sur toute la chaîne de certification (hors certificat racine).

Le concept de l'OSCP stapling est d'incorporer la réponse OSCP lors de la négociation TLS entre le client et le serveur HTTP. Pour plus d'information, consulté [la page Wikipedia](https://fr.wikipedia.org/wiki/Agrafage_OCSP).

# Serveurs Web

## HAProxy

```
global 
   ssl-default-bind-ciphers ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256
   ssl-default-bind-options no-sslv3
```

## Apache

# Serveurs mails

# Postfix

# Création d'un service automatisé sous Unix

## Création du service

Dans le fichier `/etc/systemd/system/myservice.service`, implémenter ceci:

```bash
[Unit]
Description=<Description>
After=network.target
StartLimitIntervalSec=0

[Service]
Type=simple
ExecStart=<command>
User=<user>
[Install]
WantedBy=multi-user.target
```

## État d'un service

`systemctl status myservice.service` permet de connaitre l'état du service.

## Execution d'un service en *one-shoot*

`systemctl start myservice.service` permet de lancer un service.

`systemctl stop myservice.service` permet de stopper un service.

## Éxecution d'un service au démarrage

`systemctl enable myservice.service` permet d'ajouter le service à la liste des services s'executant au démarrage.

`systemctl disable myservice.service` permet de faire l'opération inverse.

## Reload le gestionnaire de services

`systemctl daemon-reload` permet de redémarrer le gestionnaire.

## Lister les services

`systemctl` permet de lister les services et affiche leur état.
# Exercice 1 : Gestion du stockage

## 1.1 Préparation du disque

Il m'as était demandé de créer 2 partitions : 1 de 6Go nomme "DATA" et une autre de 4Go nommée "SWAP"

Le premier imprime écran montre la création des partitions, ainsi que l'espace disque alloué à ses partitions.

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture0.PNG)

Commande utilisée `cfdisk` 


Le deuxième imprime écran montre le systeme de fichier alloué aux partitions et l'activation de la partition "SWAP" crée précedanment

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture1.PNG)

Commandes utilisées `mkfs` ; `swapon` et `swapoff`

`mkfs.ext4 -L "DATA" /dev/sdb1`

`mksawp -L "SWAP" /dev/sdb2`

`swapon /dev/sdb2`

`swapoff /dev/sda5`

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture3.PNG)

## 1.2 Montage

Nous allons maintenant activer le montage automatique en allant modifier le fichier `/etc/fstab` en l'ouvrant avec Nano.

En tapant la ligne suivnate : `UUID=ef60467b-99a4-4ce3-bedc-66cc0a306da7 /mnt  ext4 defaults 0 2`

Commande utilisé `nano /etc/fstab`

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture4.PNG)

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture5.PNG)

# Exercice 1 : Gestion du stockage

## 1.1 Préparation du disque

Il m'as était demander de crée 2 partitions : 1 de 6Go nomme "DATA" et une autre de 4Go nommée "SWAP"

Le premier imprime écran montre la création des partitions, ainsi que l'espace disque alloué à ses partitions.

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture0.PNG)

Commande utilisé `cfdisk` 


Le deuxième imprime écran montre le systeme de fichier alloué aux partitions et l'activation de la partition "SWAP" crée précedanment

![img](https://github.com/michaelc31/Checkpoint1/blob/main/Capture1.PNG)

Commande utilisé `mkfs` ; `swapon` et `swapoff`

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



# Exercices 2 : Script de création d'utilisateurs en bash

vous trouverai le script [script](https://github.com/michaelc31/Checkpoint1/blob/main/adduser.sh)

	#! /bin/bash



	utilisateur1=$1 

	utilsateur2=$2

	utilisateur3=$3



	if [ -z $1 ]

	then 

		echo "Il manque les noms d'utilisateurs en argument - Fin du script"

		exit 1	

	else

		if [ cat /etc/passwd | grep "$1" ]

		then

			echo "utilisateur $utilisateur1 existe deja"

			exit 1

		else

			adduser $1

			echo "L'utilisateur $utlisateur1 a été crée"

		fi

	fi

	if [ -z $2 ]

	then 

		echo "Il manque les noms d'utilisateurs en argument - Fin du script"

		exit 1

	else

		if [ cat /etc/passwd | grep "$2" ]

		then

			echo "utilisateur $utilisateur2 existe deja"

			exit 1

		else

			adduser $2

			echo "L'utilisateur $utlisateur2 a été crée"	

		fi

	fi

	if [ -z $3 ]

	then 

		echo "Il manque les noms d'utilisateurs en argument - Fin du script"

		exit 1

	else

		if [ cat /etc/passwd | grep "$3" ]

		then

			echo "utilisateur $utilisateur3 existe deja"

			exit 1

		else

			adduser $3

			echo "L'utilisateur $utlisateur3 a été crée"	

		fi

	fi

	exit 0


## Exercice 3 : Quiz

| Question | Réponse |
| :-------: | :------- | 
| 1  |  la commande permettant d'afficher les utilisateur est : `cat /etc/passwd`  |
| 2  |  la commande pour changer les droit d'acces au fichier est `chmod`  |
| 3  | pour ne pas envoyer les fichier PDF d'un depot local gît il suffit de ne pas faire de `git add` et `git comit` sur les fichier .pdf ccomme ca tout les fichier qui auront eu un `git commit` pourrons etre envoyé |
| 4  |  la gommande Gît est `git merge main test_valide`  |
| 5  | Pour afficher le message j'utilise la commande : `echo -e "Malgré le prix élevé de 100$, il a dit \" Bonjour ! \" au vendeur :"\\n- \"Bonjour est-ce que ce clavier fonctionne bien ?\"\\n\"Evidemment \! On peut tout écrire avec, que ce soit des pipe \|\ ou bien des backslash \\\\\\ \!\"\\n - \"Même des tildes \~\ ?\"\\n -\"Evidemment \!\"` |
| 6  | Pour afficher le processus en premier la commande sera `ps -C gedit`   |
| 7  |  les couches de modeles OSI au niveau 2 et 3 sont les couches Réesaux et Liaisons du coup on travaillera sur le l'adressage IP et MAC du coup on trouvera comme materiel réseaux des carte Reseau, des routeurs, les commutateur, switch. exemple (PC client, box ADSL,)   |
| 8  |  les commande powershell pour les commande bash sont : `cd =  Set-Location` ; `cp = Copy-Item` ; `mkdir = New-Item` ; `ls = Get-ChildItem`  |
| 9  |  le Payload est la charge utile dans une trame ethernet elle va varier selon le type d'adressage IP (ipv4 ipv6) , le protocole utiliser (tcp , udp) et les données. |
| 10 |  Les Classes IP ont été remplacer par le CIDR car les calsses IP comprennait trop de contrainte (nb d'adresse IP pas assez importante ou Trop importante selon la classe ex: classe C : 2^8-2 = 254 adresses classe B : 2^16-2 =65534 adresses) et le CIDR permet de mieux decouper votre reseaux en adaptant au mieux le masque de sous reseau |

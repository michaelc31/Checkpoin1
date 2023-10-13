# Exercices 2 : Script de création d'utilisateurs en bash

vous trouverai le script [adduser.sh](https://github.com/michaelc31/Checkpoint1/blob/main/adduser.sh)

	#! /bin/bash


#---------- VARIABLE ---------------------

	utilisateur1=$1 

	utilsateur2=$2

	utilisateur3=$3

#------------ MAIN ---------------------

	if [ -z $1 ]

	then 

		echo "Il manque les noms d'utilisateurs en argument - Fin du script"

		exit 1	

	else

		if [ cat /etc/passwd | grep "$1" ]

		then

			echo "utilisateur $utilisateur1 existe deja"


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


		else

			adduser $3

			echo "L'utilisateur $utlisateur3 a été crée"	

		fi

	fi

	exit 0

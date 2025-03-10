Le service rendu : 

Le service est une application web qui génère une page HTML en fonction d'un nom fourni en paramètre de requête. Il associe ce nom à un identifiant de Pokémon en utilisant un algorithme de hachage, puis récupère le nom du Pokémon correspondant via une API externe (PokeAPI). La page affiche ensuite le nom du Pokémon et d'autres informations.

Comment lancer le service sur son poste

Pour lancer le service sur votre poste, suivez ces étapes :

Assurez-vous d'avoir Go installé sur votre machine.
Clonez le dépôt contenant le code source ou placez le fichier Go dans un répertoire de votre choix.
Ouvrez un terminal et naviguez jusqu'au répertoire contenant le fichier Go.
Exécutez la commande go run main.go pour démarrer le serveur.
Par défaut, le serveur écoutera sur http://0.0.0.0:8080. Vous pouvez accéder à l'application en ouvrant un navigateur web et en allant à http://localhost:8080.
Le fonctionnement global
L'application fonctionne comme suit :

Démarrage : Le serveur démarre et écoute les requêtes HTTP sur l'adresse et le port spécifiés.
Requête : Lorsqu'une requête GET est reçue à la racine (/), le serveur extrait le paramètre name de l'URL.
Calcul de l'ID Pokémon : Le nom est haché en utilisant SHA-1, et le résultat est utilisé pour calculer un identifiant de Pokémon (modulo 151).
Récupération du nom du Pokémon : L'application envoie une requête à l'API PokeAPI pour obtenir le nom du Pokémon correspondant à l'ID calculé.
Génération de la page : Un modèle HTML est rempli avec les informations récupérées et rendu dans la réponse HTTP.
Logging : Le temps de génération de la page et les informations associées sont enregistrés dans les logs.


# Projet  8 : Déployer un modèle dans le cloud


### Contexte
Une très jeune start-up de l'AgriTech, nommée  "Fruits!", cherche à proposer des solutions innovantes pour la récolte des fruits.

La volonté de l’entreprise est de préserver la biodiversité des fruits en permettant des traitements spécifiques pour chaque espèce de fruits en développant des robots cueilleurs intelligents.

La mise en place d'une application permettant d'afficher les informations d'un fruit à partir d'une photo permettrait de sensibiliser le grand public à la biodiversité des fruits et de mettre en place une première version du moteur de classification des images de fruits.

### Mission
Vous êtes donc chargé de développer dans un environnement Big Data une première chaîne de traitement des données qui comprendra le preprocessing et une étape de réduction de dimension.

### Jeu de données
131 dossiers, chacun représentant une variété de fruit. Pour chaque fruit il y a plus ou moins 400 photos prise sous 360°. Soit au total plus de 64.000 photos


### Le projet

Pour la preuve de concept j'ai choisi selement 4 variétés de fruits, pour chacune d'elle j'ai pris 4 photos sous différents angles 

#### Localement
Dans un premier temps, pour réduire les frais et exclure les erreurs de liées à la connection entre les différents services du cloud, j'ai développé le projet en local.
Il a fallu pour cela télécharger les données, Spark et Java. 
Ensuite il a fallu configurer les varables d'environnement. Ayant un système d'exploitation Windows il a fallu également télécharger le fichier executable WinUtils.exe et hadoop.dll

#### Sur le cloud
Créer une AMI avec ses clés d'accès et un bucket S3 sur lequel j'ai chargé mes 16 photos. 
Lancer une instance EC2 t2.large Ubuntu dans laquelle il faut refaire la même chose qu'en local mais via SSH. Une fois les packages installés et l'environement prêt on importe le script. Le lancement du script va charger les photos depuis le bucket S3, faire les traitement et la réduction de dimension et enfin enregistrer la sortie dans le même bucket sous format csv
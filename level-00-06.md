# Niveaux 0 à 6

> Aucun mot de passe n'est publié ici, conformément aux règles d'OverTheWire. Ce document liste les commandes et concepts pratiqués pour progresser dans ces niveaux.

## Connexion SSH

```
ssh UTILISATEUR@bandit.labs.overthewire.org -p 2220
```

Connexion au serveur Bandit avec le port dédié 2220.

## Navigation et exploration

```
ls          # lister les fichiers visibles
ls -a       # inclure les fichiers cachés
ls -la      # détails + fichiers cachés (permissions, propriétaire, taille...)
cd DOSSIER  # entrer dans un répertoire
cd ..       # revenir au répertoire parent
cat FICHIER # afficher le contenu d'un fichier
```

## Cas particuliers de noms de fichiers

```
cat ./-file07                      # fichier commençant par un tiret
cat "./--spaces in this filename--" # fichier avec espaces
```

`./` permet de forcer l'interprétation du nom comme chemin plutôt que comme option de commande.

## Permissions Unix

Format `-rw-r-----` : type de fichier, puis droits du propriétaire / groupe / autres (lecture, écriture, exécution).

## Identification de fichiers

```
file NOM_DU_FICHIER   # déterminer le type réel du contenu
file ./*               # analyser tous les fichiers du répertoire actuel
```

## Recherche avancée avec find

```
find . -type f                              # tous les fichiers ordinaires
find . -type d                              # tous les répertoires
find . -type f -size 1033c ! -executable    # taille exacte, non exécutable
find . -type f -size 1033c -executable      # taille exacte, exécutable
```

## Conversion bits / bytes

1 byte = 1 octet = 8 bits. Utile quand une consigne donne une taille en bits et que `find -size` attend des octets (`c`).

## Méthode de progression

1. Lire la consigne du niveau.
2. Identifier la ou les commandes pertinentes.
3. Exécuter et localiser l'information demandée.
4. Se connecter au niveau suivant via SSH.

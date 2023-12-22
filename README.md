# Introduction au cours : Création d'un Projet PHP avec Devilbox

Bonjour et bienvenue dans ce tutoriel pas à pas sur la mise en place d’un projet PHP en utilisant Devilbox, un environnement de développement PHP moderne et flexible qui s'appuie sur Docker. Aujourd’hui, tu vas apprendre à démarrer un projet PHP from scratch en utilisant cet outil incroyable qui va simplifier la gestion de ton environnement de développement.

## Étape 1 : Installer Docker

Avant tout, assure-toi que Docker est installé sur ton système. Docker nous permettra de gérer des conteneurs pour nos services web tels que Apache, Nginx, MySQL et d’autres.
```bash
# Installation sur les systèmes basés sur Debian/Ubuntu
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```


## Étape 2 : Cloner et Configurer Devilbox

Maintenant, clone le dépôt Git de Devilbox pour récupérer les fichiers nécessaires.
```bash
git clone https://github.com/cytopia/devilbox
cd devilbox
```
Une fois dans le dossier Devilbox, copie le fichier d'environnement exemple pour le personnaliser :
```bash
cp env-example .env
```

Ouvre le fichier .env et ajuste les configurations selon tes besoins, telles que les versions de PHP, le serveur web, etc.



### Étape 3 : Lancer Devilbox

Avec Docker installé et Devilbox configuré, il est temps de démarrer les conteneurs.

```bash
docker-compose up -d httpd php mysql
```

## Étape 4 : Créer ton Projet PHP
Place-toi dans le dossier de données :
```
cd data/www
```
Crée un nouveau dossier pour ton projet :

```bash
mkdir -p monprojet/htdocs
cd monprojet/htdocs
```
Maintenant que tu es dans le dossier de données, crée un nouveau dossier pour ton projet dans le sous-dossier *htdocs* :

Dans le dossier *htdocs* de ton projet, tu pourras placer tes fichiers PHP. C'est l'équivalent du *DocumentRoot* d'un serveur classique.


## Étape 5 : Configurer `/etc/hosts` pour ton Projet
Pour que ton projet soit accessible via un nom de domaine local, tu dois modifier le fichier /etc/hosts sur ton système hôte :
```bash
echo "127.0.0.1 monprojet.loc" | sudo tee -a /etc/hosts
```

Ainsi, tu pourras accéder à ton projet en allant sur ```http://monprojet.loc``` dans ton navigateur.

## Étape 6 : Accéder à ton Projet via Navigateur
Après avoir ajouté l'entrée dans ```/etc/hosts```, ton projet est normalement accessible via ```http://monprojet.loc```. 
N'oublie pas également que le tableau de bord de Devilbox est toujours accessible à ```http://localhost:8080``` pour gérer tes projets facilement.

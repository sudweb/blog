# Le blog de Sud Web

[![Build Status](https://travis-ci.org/sudweb/2018.svg?branch=master)](https://travis-ci.org/sudweb/2018)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/sud-web/sud-web)

Site internet du cycle de conférences annuel Sud Web, dont la 7e édition aura lieu à Anduze les 25 et 26 mai 2018.

[https://sudweb.fr/](https://sudweb.fr/)

## Pré-requis

Le site est généré à l'aide de [Jekyll](http://jekyllrb.com/) et nécessite Ruby 2.4.0 (voir `.ruby-version`)

Nous vous recommandons de gérer l'installation de Ruby via [rbenv](http://rbenv.org/).

Sous Mac OS X, vous pouvez utiliser [Homebrew](http://brew.sh/) pour cela
```bash
$ brew install rbenv ruby-build
```

Sous GNU/Linux, certaines librairies sont nécessaires (à adapter à votre gestionnaire de paquets) :
```bash
sudo apt-get install -y libreadline-dev build-essential
```
Puis pour rbenv et ruby-build, préférer une installation par git :
```bash
$ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
$ cd ~/.rbenv && src/configure && make -C src
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
$ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

## Installation

Si vous n'avez pas déjà cloné le dépot :
```bash
$ git clone https://github.com/sudweb/2018.git && cd 2018
```
Si bundler n'est pas installé
```bash
$ gem install bundler
```
Pour installer toutes les dépendances du projet :
```bash
$ bundle install;
$ bundle exec rake prebuild:install;
```
Pour installer la bonne version de Ruby avec rbenv :
```bash
$ rbenv install
```

## Travailler en local

Pour travailler sur le site et surveiller les modifications :

```bash
$ bundle exec rake build:serve
```

Pour builder pour le Dév

```bash
$ bundle exec rake build:dev
```

Pour builder pour la Production

```bash
$ bundle exec rake build:prod
```

Si vous modifiez le fichier `_config.yml`, il faut couper et relancer.

Le site est maintenant accessible en local à l'adresse http://127.0.0.1:4000/ (dev).

Pour plus d'information sur l'utilisation de Jekyll, reportez-vous à la [documentation officielle](http://jekyllrb.com/docs/home/).

## Production

Le blog est déployé sur un serveur [AlwaysData](https://www.alwaysdata.com/) par le biais de GitHub Actions.

Le script de déploiement se trouve dans le fichier [`.github/workflows/deploy.yml`](/.github/workflows/deploy.yml). Pour fonctionner, il a besoin d’une clé <abbr>SSH</abbr> privée valide.

Pour générer et autoriser une nouvelle clé <abbr>SSH</abbr>, **à exécuter sur votre machine locale** :

```console
$ # Génère la clé SSH elle-même (lorsqu’il vous sera demandé, ne précisez pas de mot de passe)
$ ssh-keygen -o -a 100 -t ed25519 -f ./deploykey -C "github-actions@sudweb.fr"
$
$ # Autorise la clé à être utilisée pour se connecter au serveur (il vous sera demandé le mot de passe de l’utilisateur sudweb_blog)
$ ssh-copy-id -i deploykey.pub sudweb_blog@ssh-sudweb.alwaysdata.net
$
$ # Copie la clé privée dans votre presse-papier
$ cat deploykey | xsel --clipboard
```

Il ne reste plus qu’à coller la valeur copiée en valeur de la variable d’environnement `SSH_PRIVATE_KEY` pour [l’environnement `production-alwaysdata`](https://github.com/sudweb/blog/settings/environments).

Le script a également besoin d’une variable d’environnement `SSH_KNOWN_HOSTS` dont vous pouvez générer la valeur avec la commande suivante :

```console
$ ssh-keyscan ssh-sudweb.alwaysdata.net
```

## Contribution

Pour toute demande, merci de [créer une issue](https://github.com/sudweb/2018/issues/new) sur GitHub.

Si vous souhaitez nous aider, vous pouvez [copier](https://help.github.com/articles/fork-a-repo/) le dépôt, faire vos modifications dans une nouvelle branche et [faire une demande de fusion](https://github.com/sudweb/2018/pulls).

Toute modification doit faire l'objet d'une [pull request](https://github.com/sudweb/2018/pulls) et doit passer les tests avant de pouvoir être fusionnée.

## Tests

Avant de soumettre votre pull-request, vérifiez que les tests passent :

```bash
$ bundle exec rake postbuild:test:kiss
```

## Licence

Ce code est publié sous licence MIT.

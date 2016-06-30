# sudweb.fr/blog [![Build Status](https://travis-ci.org/sudweb/blog.svg)](https://travis-ci.org/sudweb/blog)

Les actualités de Sud Web… et toutes les contributions que vous auriez envie
de mettre à la vue de toutes et tous !

## Installer

Vous devez avoir Ruby sur votre machine — idéalement [rbenv](http://rbenv.org/)

```bash
git clone https://github.com/sudweb/blog.git sudweb-blog
cd sudweb-blog

# installe la version Ruby adéquate
rbenv install

# installe les dépendances du projet
rbenv exec bundle install
```

## Développer localement

Lancez Jekyll en local :

```bash
rbenv exec foreman start
```

Vous pouvez maintenant prévisualiser le site à l'adresse  [localhost:4000/blog](http://localhost:4000/blog/).

## Publier des modifications

Créer une branche de travail, enregistrez vos modifications et [ouvrez une pull request](https://github.com/sudweb/blog/pulls)

## Rédiger un billet

Créer un nouveau fichier markdown dans un dossier du type `/2016/_posts/`
en respectant la nomenclature suivante : `YYYY-MM-DD-titre-fr-mon-billet.md`

Si vous le souhaitez, vous pouvez renseigner les entêtes YAML suivantes :

```yaml
---
title: Titre du billet
description: Description en moins de 150 caractères du contenu du billet.
author: Prénom Nom
categories:
# Affecter le billet à la catégorie correspondante à l'année de l'édition
- 'YYYY'
# Image pour les partages sur les réseaux sociaux
image: /assets/images/image-opengraph-billet.jpg
---
```

Par défaut les commentaires Disqus sont ouverts, mais peuvent-être désactivés
 en ajoutant une entête YAML `comments: false`.

Vous pouvez ensuite rédiger votre billet dans votre éditeur Markdown favori.
Si vous n'êtes pas encore familarisé avec cette syntaxe, [reportez vous à la documentation](https://guides.github.com/features/mastering-markdown/).

Pour ajouter une image dans un billet, déposez votre image dans le
répertoire `/assets/images/` et faites appel à l'include `figure.html`
dans le fichier Markdown :

```liquid
{% include figure.html name="sudweb-2012-bruce-lawson.jpg"
caption="Bruce Lawson à Toulouse" %}
```

## Lancer les tests

Des tests basiques sont là pour vous aider à vérifier que les fichiers
respectent bien les [régles](https://github.com/mivok/markdownlint/blob/master/docs/RULES.md)
définies dans le fichier de configuration du linter et qu'il n'y a aucun lien mort.

Pour lancer les tests il suffit de lancer la commande suivante :

```bash
script/cibuild
```

Quand les tests sont OK, vous pouvez ouvrir une PR, c'est à dire demander
à fusionner votre brancge sur la branche `gh-pages`. Vous pouvez ainsi demander
 à un autre membre de l'équipe de relire vos modifications avant de les fusionner.

## Déploiement

Le site est hébergé par Github Pages, et sera donc mis à jour automatiquement
à chaque PR fusionnée sur la branche `gh-pages`.

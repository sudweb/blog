# sudweb.fr/blog [![Build Status](https://travis-ci.org/sudweb/blog.svg)](https://travis-ci.org/sudweb/blog)

> Les actualités de Sud Web … et toutes les contributions que vous auriez envie de mettre à la vue de toutes et tous !

# Installer

Vous devez avoir Ruby sur votre machine — idéalement, [rbenv](http://rbenv.org/).

```bash
git clone https://github.com/sudweb/blog.git sudweb-blog
cd sudweb-blog

# installe la version Ruby adéquate
rbenv install

# installe les dépendances du projet
rbenv exec bundle install
```
# Développer localement

```bash
rbenv exec foreman start
```
Le blog sera accessible via [localhost:4000/blog](http://localhost:4000/blog/).

# Publier des modifications

Créer une branche de travail, puis enregistrez vos modifications.

Si vous modifiez des fichiers au format Markdown, vérifiez qu'ils respectent les régles définies dans le fichier de configuration avant de faire une demande de fusion :

```bash
rbenv exec mdl --config .mdlrc **/*.md
```
Le site sera mis à jour automatiquement à chaque commit fusionné sur la branche `gh-pages`.

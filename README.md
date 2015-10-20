# sudweb.fr/blog [![Build Status](https://travis-ci.org/sudweb/blog.svg?branch=feature-ci)](https://travis-ci.org/sudweb/blog)

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

# Publier

Le site sera mis à jour automatiquement à chaque commit poussé sur la branche `gh-pages`.

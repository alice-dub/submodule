# submodule

Conclusions sur l'utilisation des commandes submodules.
Fortement inspiré du tutoriel : https://delicious-insights.com/fr/articles/git-submodules/#envie-d-en-savoir-plus-

Initialiser le repo du submodule:
<code>
git init
</code>

Ajouter les submodules (suivi sur la branche master) au repo :
<code>
git submodule add -b master Url_distant_repo Lien_local_submodule
</code>

Rendre le git status plus verbeux : 
<code>
git config --global status.submoduleSummary true
</code>

## Premier cas : un des repos enfants a des updates par ailleurs que l'on souhaite récupérer dans le dossier parent 

A la racine du dossier parent :

<code>
  git submodule update --remote nom_module
</code>

- Faire un commit classique 

- Le pusher sur la version remote du dossier 

Attention : si aucun nom de module n'est spécifié, tout est mis à jour

## Deuxième cas : Des modifications sont directements faites dans le dossier parent et doivent remontes dans le repo enfant

Dans le repo enfant contenu dans le dossier parent (aucune branche n'est par défaut précisée d'où la commande un peu plus longue) : 

- Faire un commit classique dans le dossier enfant

- Le pusher sur le repo enfant branche master : 
<code>
   git push origin HEAD:master
</code>

- Retourner dans le dossier parent 

- Faire le commit dans le dossier parent

- Le pusher



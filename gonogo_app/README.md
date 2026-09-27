# Tâche Go / No-Go

Application web statique conçue pour GitHub Pages. Ouvrez la page `task/go_no_go_task.html` sur le site pour accéder à la tâche.

Lorsque le signal est vert (Go), appuyez sur la barre d’espace ou touchez l’image. Lorsque le signal est rouge (No-Go), ne répondez pas.

## Organisation des fichiers

```text
gonogo_app/
├── task/
│   └── go_no_go_task.html
├── go/
│   ├── manifest.json
│   └── go01_...jpg ... go08_...jpg
├── nogo/
│   ├── manifest.json
│   └── nogo01_...jpg ... nogo08_...jpg
```

La page charge d’abord les images par défaut à partir des chemins relatifs `../go/...` et `../nogo/...`. Si une image locale ne peut pas être chargée, elle tente de récupérer l’image correspondante sur Wikimedia Commons. Ce recours nécessite une connexion Internet et dépend de la disponibilité du service.

## Choix des images

Les catégories Go et No-Go se configurent indépendamment. Vous pouvez utiliser :

- les images par défaut pour les deux catégories, sans sélectionner de dossier ;
- un dossier Go personnel et les images No-Go par défaut ;
- un dossier No-Go personnel et les images Go par défaut ;
- un dossier personnel pour chaque catégorie.

Par exemple, cliquez uniquement sur **Choisir un dossier No-Go** pour utiliser vos propres images No-Go tout en conservant les images Go par défaut. Chaque catégorie possède un bouton permettant de revenir à ses images par défaut.

Chaque dossier personnel doit contenir au moins **6 images directement dans le dossier** : les sous-dossiers ne sont pas parcourus. La sélection utilise le sélecteur de fichiers du navigateur avec prise en charge des dossiers (`webkitdirectory`), compatible avec les versions récentes de Brave, Chrome, Edge, Firefox et Safari sur Mac. Si le navigateur ne prend pas en charge la sélection de dossiers, sélectionnez plusieurs fichiers image.

## Paramètres du protocole

- **Session courte** : 96 essais répartis en 3 blocs de 32 essais.
- **Session standard** : 192 essais répartis en 6 blocs de 32 essais.
- Chaque bloc comprend 16 essais Go et 16 essais No-Go.
- Chaque image reste associée à la même catégorie pendant toute la session : Go ou No-Go.
- Chaque image sélectionnée est présentée au moins 6 fois.
- La session utilise au maximum 8 images par catégorie en mode court et 16 en mode standard. Si le dossier en contient davantage, les images utilisées sont sélectionnées aléatoirement.
- Le signal apparaît 100 ms après l’apparition de l’image ; la durée de présentation du stimulus est de 1 500 ms et l’intervalle entre les stimuli est de 500 ms.

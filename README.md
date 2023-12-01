# Bravo ! 
Voici votre nouvelle appli, connectée au réseau de données distribuées Constellation.

*Note: ce dépôt est conçu pour être utilisé comme gabarit par la fonctionnalité autogénération d'applis de l'interface Constellation. [Nous vous recommendons d'utiliser cette fonctionnalité](https://docu.réseau-constellation.ca/exemples/scienceCitoyenne.html#collecte-de-donnees) plutôt que de cloner ce projet directement.*

Ce projet est configuré pour générer automatiquement, à base du même code, **un site web** (installable sur les téléphones avec PWA) de même qu'une **application installable** sur Windows, MacOS et Linux, toutes compatibles entre elles et prêtes à partager vos données. Chouette, non ? De rien ! :)

**Note : le but de ce gabarit est de rendre l'adoption de Constellation facil et amusant. Si vous êtes confus ou ne vous amusez pas, n'hésitez pas à nous contacter pour qu'on puisse vous aider !** Vous pouvez nous contacter sur le forum publique sur [GitHub](https://github.com/reseau-constellation/gabarits) ou bien par [courriel](julien.malard@mail.mcgill.ca).

## Démarrer
Pour finaliser votre appli, suivez les étapes suivantes :

1. Sortez ce dossier de votre dossier de téléchargements et copiez-le quelque part sur votre ordinateur où vous allez le retrouver.
2. Ouvrez le code dans votre éditeur favoris. Nous on utise [VSCodium](https://vscodium.com/), mais c'est une question de goût !
3. Installez [Node.js](https://nodejs.org/en) et [pnpm](https://pnpm.io/fr/installation) sur votre ordinateur, si ce n'est pas déjà fait.
4. Sur la ligne de commande, allez au dossier du projet (`cd mon/projet/est/ici/gabarits`) et exécutez la commande `pnpm install`.
5. **Changez votre logo !** Le projet vient avec le logo de Constellation par défaut...il est très jolie mais n'est peut-être pas celui que vous voulez pour votre appli. Vous pouvez changer les icônes à `buildResources/icon.icns` et `buildResources/icon.png` (ce sont les icônes qui apparaîteront sur l'appli installable), `packages/renderer/public/logo.svg` (l'icône d'onglet pour le site web) et `packages/renderer/assets/logo.svg` (le logo qui apparâit sur la page principale).  Vous pouvez changer les images à l'icône de vos rêves, mais soyez sûrs de garder les mêmes noms pour les fichiers.
6. **Vérifiez que tout est beau.** Dans le terminal, taper `pnpm watch:web` pour prévisualiser l'appli Internet ou bien simplement `pnpm watch` pour prévisualiser l'appli installable.

## Publier votre appli
Tout est beau ? On y va ! 

### Publication sur GitHub (tout gratuit)
Vous avez plusieurs options pour publier votre appli. La plus facile est d'utiliser GitHub.

1. [Créez un nouveau dépôt](https://docs.github.com/fr/repositories/creating-and-managing-repositories/creating-a-new-repository) vide sur GitHub et téléversez ce code sur le nouveau dépôt en suivant les instructions sur le site GitHub. **Assurez-vous de bien choisir l'option « projet publique » et non privé.** Vous aurez aussi besoin de [git](https://git-scm.com/downloads) sur votre ordinateur, s'il n'y est pas déjà.
2. Allez au fichier `packages/renderer/consts.ts` et changer la valeur de la variable `DÉPÔT_GITHUB` au nom du dépôt que vous venez de créer.
3. Activez [GitHub Pages](https://docs.github.com/fr/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) sur votre dépôt et sélectionnez la branche `gh-pages` en tant que source.
4. Votre appli est maintenant disponible sur l'Internet ! Pour les pros : si vous voulez achetter votre propre nom de domaine (par exemple, `www.ma-super-appli.ca`), vous pouvez le faire maintenant et l'ajouter à la configuration de GitHub Pages (instructions un peu confuses [ici](https://docs.github.com/fr/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)).
5. Si vous vouliez uniquement une appli Internet, c'est fini ! Tout est beau et le site web se mettre automatiquement à jour chaque fois que vous modifierez votre code.
6. Si vous voulez que votre projet soit disponible en tant qu'application installable sur ordinateur, il vous reste une dernière étape - ajouter une étiquette de version, ce qui indiquera à GitHub que votre appli est prête à compiler et à publier. Exécutez `git tag v1.0 && git push --tags` chaque fois que vous voulez publier une nouvelle version de l'appli (changer le numéro de version à chaque fois). L'appli installable sur Linux, Windows et MacOS apparaîtera sur la page `releases` de votre dépôt GitHub.
7. Si vous avez de l'argent en trop, vous pouvez payer Microsoft ou Apple pour le privilège de publier votre appli sur leurs magasins d'applis en ligne ([instructions ici](https://github.com/samuelmeuli/action-electron-builder#code-signing)). Sans ça, vos utilisateurs recevront, au moment de l'installer, des messages comme quoi la sécurité de votre appli n'a pas été vérifiée.

## Mises à jour
Lorsque vous vivez sur la fine pointe de la technologie, les choses bougent vite. Vous pouvez activer [Mend Rennovate](https://github.com/marketplace/renovate) gratuitement sur votre projet GitHub. Ce robot se chargera de garder le projet à jour tout en vérifiant que tous les tests de contrôle de qualité et de fonctionnalité fonctionnent toujours.

Note : au fur et à mesure que la technologie évolue, nous mettre le gabarit original à jour (https://github.com/reseau-constellation/gabarits), et les nouvelles applis que vous générez à travers l'interface de Constellation utiliseront toujours la nouvelle version.

## Licence et conditions
Ces gabarits sont distribués sous la licence source ouverte AGPL-3.0. Cette licence stipule que vous devez distribuer tout dérivé de ce code sous la même licence. 

La structure du projet est basé sur [Vite Electron Builder Boilerplate](https://github.com/cawa-93/vite-electron-builder) de [Олександр Козак](https://kozack.me/) sous [licence MIT](https://choosealicense.com/licenses/mit/).

Les images et l'art dans l'interface proviennent de [unDraw](https://undraw.co/) et de [வள்ளுவர் வள்ளலார் வட்டம்](https://commons.wikimedia.org/wiki/User:Valluvar_Vallalar_Vattam?uselang=ta), de la catégorie [iconographie](https://commons.wikimedia.org/wiki/Category:Tamil_Iconography?uselang=ta). Ces derniers sont disponibles selon la licence [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.fr).

# Add-ons Firefox OS
## Firefox OS France User Group<br>Meetup Octobre 2015

---

[@g_marty](https://twitter.com/g_marty) - Guillaume Marty

Je suis <img src="img/French.svg" style="height: .8em; vertical-align: middle;" alt="Francais" title="Francais"> et j'habite en <img src="img/UK.svg" style="height: .8em; vertical-align: middle;" alt="Angleterre" title="Angleterre">

Je travaille sur <img src="img/Firefox-OS.svg" style="height: 1.7em; vertical-align: middle; margin-bottom: 21px;" alt="Firefox OS" title="Firefox OS">

---

## C'est quoi ?

Note:
On pouvait deja editer le code auparavant: demo.
Les add-ons permettent de persister ces changements.
Exclusivite, unique dans le monde du mobile.

---

## WebExtensions

Note:
Projet touchant a terme toutes les version de Firefox.
Nouveau modele d'extensions base sur les extensions supportees par Chrome et Opera.
Mozilla croit au principe d'interroperabilite.

---

## Anatomie d'une extension

![WebExtension](img/webextension.svg)

---

## manifest.json

```json
{
  "manifest_version": 1,
  "name": "Add-on Sample",
  "description": "Firefox OS add-on example",
  "version": "1.0",
  "author": "Guillaume Marty",
  "content_scripts": [
    {
      "matches": ["app://system.gaiamobile.org/index.html"],
      "css": ["css/style.css"],
      "js": ["js/index.js"]
    }
  ],
  "icons": { "128": "/icons/128.png" }
}
```

---

## update.webapp

```json
{
  "name": "Add-on Sample",
  "description": "Firefox OS add-on example",
  "developer": {
   "name": "Guillaume Marty"
  },
  "package_path": "extension.zip",
  "icons": { "128": "/icons/128.png" }
}
```

Note:
icons de update.webapp peut changer.

---

## Cycle de vie d'un add-on

1. Développement
2. [Mise en ligne]
3. Installation
4. Activation / Désactivation

Note:
Active par defaut si installe depuis le Marketplace.
A activer dans settings si installe depuis le WebIDE.

---

## Spécificités

* `window` est proxié
* Le DOM peut être chargé ou pas
* Éviter les injections multiples
* Évènement `onenabledstatechange`

Note:
On peut lire les prop de window mais les prop creees par l'add-on ne sont visibles
par l'app.
Verifier le cas ou le DOM a deja ete charge pour executer l'add-on.
onenabledstatechange pour initialiser ou nettoyer une extension. Dispo dans certaines
conditions uniquement.

---

## Documentation

---

[developer.mozilla.org/en-US/Firefox_OS/Add-ons](https://developer.mozilla.org/en-US/Firefox_OS/Add-ons)

![MDN](img/mdn.png)

---

[developer.chrome.com/extensions](https://developer.chrome.com/extensions)

![Google Chrome Developers](img/google-chrome.png)

---

## Attention

|Produit|Version|Date|
|---------------|---|----------------------|
|Firefox OS     |2.5|2015/08/27 ou + récent|
|Firefox Desktop|44 |2015/09/30 ou + récent|

Note:
Techno experimentale.
Totalement instable.
Ca peut et ca va casser dans les prochains jours/semaines/mois.

---

## Attention

* Incompatible avec simulators du WebIDE
* Utiliser le mulet

---

## A quoi ça sert?

Note:
Micro fonctionnalite.
Pas de limite a la customisation de mon telephone.

---

## Le futur

* Bientôt disponibles dans le Marketplace
* Plus de fonctionnalités, moins de bugs
* Support d'APIs des WebExtensions de Chrome

Note:
Compatbilite avec les versions de Firefox.

---

## Merci

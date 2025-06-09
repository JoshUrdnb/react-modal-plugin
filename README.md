# react-modal-plugin-oc

[![NPM Version](https://img.shields.io/npm/v/react-modal-plugin-oc.svg)](https://www.npmjs.com/package/react-modal-plugin-oc)
[![License](https://img.shields.io/npm/l/react-modal-plugin-oc.svg)](https://github.com/JoshUrdnb/react-modal-plugin/blob/main/LICENSE)

Un plugin de fenêtre modale simple et personnalisable pour React. Il permet d'afficher du contenu dans une superposition qui apparaît au-dessus du reste de la page.


## Installation

Pour installer le plugin, utilisez `npm` ou `yarn` :

```npm install react-modal-plugin-oc```

ou

```yarn add react-modal-plugin-oc```

**Remarque :** N'oubliez pas d'importer le fichier CSS pour un rendu visuel correct de la modale.

```import 'react-modal-plugin-oc/modalPlugin.css';```


## Utilisation

Voici un exemple de base pour utiliser le composant `ModalPlugin`. Le composant est contrôlé, ce qui signifie que vous devez gérer son état d'ouverture (ouvert/fermé) dans le composant parent à l'aide d'un état, comme `useState`.

```
import React, { useState } from 'react';
import ModalPlugin from 'react-modal-plugin-oc';
import 'react-modal-plugin-oc/modalPlugin.css';

function MonApplication() {
  const [modalEstOuverte, setModalEstOuverte] = useState(false);

  const ouvrirModal = () => {
    setModalEstOuverte(true);
  };

  const fermerModal = () => {
    setModalEstOuverte(false);
  };

  return (
    <div>
      <h1>Mon Application</h1>
      <button onClick={ouvrirModal}>Ouvrir la modale</button>
      <ModalPlugin 
        isOpen={modalEstOuverte} 
        onClose={fermerModal}
      >
        <h2>Contenu de la modale</h2>
        <p>Ceci est un exemple de contenu. Vous pouvez y insérer n'importe quel élément React.</p>
        <button onClick={fermerModal}>Fermer</button>
      </ModalPlugin>
    </div>
  );
}

export default MonApplication;
```


## Props

Le composant `ModalPlugin` accepte les props suivantes pour sa configuration :

| Prop       | Type              | Requis | Description                                                                                                        |
| :--------- | :---------------- | :----- | :----------------------------------------------------------------------------------------------------------------- |
| `isOpen`   | `Boolean`         | Oui    | Contrôle la visibilité de la modale. Passez `true` pour l'afficher et `false` pour la masquer.                    |
| `onClose`  | `Function`        | Oui    | Fonction de rappel (callback) exécutée lorsque l'utilisateur demande la fermeture de la modale.                    |
| `children` | `React.ReactNode` | Non    | Le contenu à afficher à l'intérieur de la modale. Optionnel. |

### Callbacks

#### `onClose()`

La fonction passée à la prop `onClose` est appelée dans deux situations :

1.  Lors d'un clic sur le **bouton de fermeture** (⊗).
2.  Lors d'un clic sur l'**arrière-plan** de la modale (l'overlay gris).

## License

MIT © [Joshua Urdanabia](https://github.com/JoshUrdnb)
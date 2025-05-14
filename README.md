# Memo-One-liners-&-Useful-Functions-JS
Compilation en français des meilleurs one-liners de JS ES6 et des fonctions les plus utiles pour le développement web. Revenez voir de temps à autres puis que j'essaierai de ne pas oubleir de mettre à jour avec mes découvertes.

---

## One-liners

---

**Manipulation de Tableaux (Arrays)**

1.  **Cloner un tableau :**
    ```javascript
    const nouveauTableau = [...ancienTableau];
    ```
    *   **Fonctionnement :** L'opérateur de décomposition (spread operator `...`) décompose les éléments de `ancienTableau` et les insère dans un nouveau tableau littéral.
    *   **Usage :** Créer une copie superficielle d'un tableau sans modifier l'original.

2.  **Fusionner des tableaux :**
    ```javascript
    const tableauFusionne = [...tableau1, ...tableau2, ...autresElements];
    ```
    *   **Fonctionnement :** Le spread operator décompose les éléments de chaque tableau et les combine dans un nouveau tableau.
    *   **Usage :** Combiner plusieurs tableaux en un seul.

3.  **Créer un tableau avec des valeurs uniques (supprimer les doublons) :**
    ```javascript
    const uniques = [...new Set(tableauAvecDoublons)];
    ```
    *   **Fonctionnement :** `Set` est une collection d'éléments uniques. En convertissant le tableau en `Set`, les doublons sont éliminés. Le spread operator reconvertit le `Set` en tableau.
    *   **Usage :** Obtenir une version d'un tableau sans doublons.

4.  **Vérifier si tous les éléments d'un tableau satisfont une condition :**
    ```javascript
    const tousPositifs = nombres.every(n => n > 0);
    ```
    *   **Fonctionnement :** La méthode `every()` teste si tous les éléments du tableau passent le test implémenté par la fonction fournie. Elle retourne `true` ou bien `false`.
    *   **Usage :** Validation, vérification de conditions sur des collections.

5.  **Vérifier si au moins un élément d'un tableau satisfait une condition :**
    ```javascript
    const auMoinsUnPositif = nombres.some(n => n > 0);
    ```
    *   **Fonctionnement :** La méthode `some()` teste si au moins un élément du tableau passe le test. Elle retourne `true` ou `false`.
    *   **Usage :** Recherche rapide, vérification de présence.

6.  **Filtrer un tableau :**
    ```javascript
    const pairs = nombres.filter(n => n % 2 === 0);
    ```
    *   **Fonctionnement :** La méthode `filter()` crée un nouveau tableau avec tous les éléments qui passent le test implémenté par la fonction fournie.
    *   **Usage :** Extraire des sous-ensembles de données basés sur des critères. Dernière partie (le test) à remplacer bien sûr.

7.  **Mapper un tableau vers un nouveau tableau (transformer chaque élément) :**
    ```javascript
    const carres = nombres.map(n => n * n);
    ```
    *   **Fonctionnement :** La méthode `map()` crée un nouveau tableau avec les résultats de l'appel d'une fonction fournie sur chaque élément du tableau appelant.
    *   **Usage :** Transformer des données, extraire des propriétés d'objets dans un tableau.

8.  **Réduire un tableau à une seule valeur (ex: somme, produit) :**
    ```javascript
    const somme = nombres.reduce((accumulateur, valeurCourante) => accumulateur + valeurCourante, 0);
    ```
    *   **Fonctionnement :** La méthode `reduce()` applique une fonction qui est un "accumulateur" et qui traite chaque valeur d'un tableau (de gauche à droite) afin de la réduire à une seule valeur. Le `0` est la valeur initiale de l'accumulateur.
    *   **Usage :** Calculs agrégés, regroupements, transformations complexes.

9.  **Trouver le premier élément qui satisfait une condition :**
    ```javascript
    const premierPair = nombres.find(n => n % 2 === 0);
    ```
    *   **Fonctionnement :** La méthode `find()` retourne la valeur du premier élément trouvé dans le tableau qui respecte la condition donnée par la fonction de test. Sinon, la valeur `undefined` est renvoyée.
    *   **Usage :** Rechercher un élément spécifique.

10. **Trouver l'index du premier élément qui satisfait une condition :**
    ```javascript
    const indexPremierPair = nombres.findIndex(n => n % 2 === 0);
    ```
    *   **Fonctionnement :** La méthode `findIndex()` renvoie l'index du premier élément du tableau qui satisfait une condition donnée par une fonction de test. Sinon, elle renvoie -1.
    *   **Usage :** Localiser un élément spécifique.

11. **Créer un tableau rempli d'une valeur :**
    ```javascript
    const tableauDeZeros = Array(5).fill(0); // [0, 0, 0, 0, 0]
    ```
    *   **Fonctionnement :** `Array(5)` crée un tableau vide avec 5 emplacements. `fill(0)` remplit tous ces emplacements avec la valeur 0.
    *   **Usage :** Initialiser des tableaux avec des valeurs par défaut.

12. **Aplatir un tableau d'un niveau :**
    ```javascript
    const tableauAplatir = [1, [2, 3], [4, [5]]].flat(); // [1, 2, 3, 4, [5]]
    ```
    *   **Fonctionnement :** La méthode `flat()` crée un nouveau tableau contenant tous les éléments des sous-tableaux concaténés récursivement jusqu'à une profondeur spécifiée (par défaut 1).
    *   **Usage :** Simplifier des tableaux imbriqués.

13. **Aplatir un tableau complètement :**
    ```javascript
    const tableauTotalementAplatir = [1, [2, 3], [4, [5]]].flat(Infinity); // [1, 2, 3, 4, 5]
    ```
    *   **Fonctionnement :** En passant `Infinity` comme argument à `flat()`, tous les niveaux d'imbrication sont aplatis.
    *   **Usage :** Obtenir une liste simple à partir d'une structure profondément imbriquée.

**Manipulation d'Objets (Objects)**

14. **Cloner un objet (superficiellement) :**
    ```javascript
    const nouvelObjet = { ...ancienObjet };
    ```
    *   **Fonctionnement :** L'opérateur de décomposition (spread operator) copie les propriétés énumérables de `ancienObjet` dans un nouvel objet littéral.
    *   **Usage :** Créer une copie superficielle d'un objet.

15. **Fusionner des objets :**
    ```javascript
    const objetFusionne = { ...objet1, ...objet2, nouvelleProp: 'valeur' };
    ```
    *   **Fonctionnement :** Le spread operator combine les propriétés des objets. Les propriétés des objets plus à droite écrasent celles des objets plus à gauche en cas de conflit de clés.
    *   **Usage :** Combiner des objets, ajouter/mettre à jour des propriétés.

16. **Obtenir les clés d'un objet sous forme de tableau :**
    ```javascript
    const cles = Object.keys(monObjet);
    ```
    *   **Fonctionnement :** `Object.keys()` retourne un tableau contenant les noms des propres propriétés énumérables d'un objet donné.
    *   **Usage :** Itérer sur les clés d'un objet, vérifier la présence de clés.

17. **Obtenir les valeurs d'un objet sous forme de tableau :**
    ```javascript
    const valeurs = Object.values(monObjet);
    ```
    *   **Fonctionnement :** `Object.values()` retourne un tableau des propres valeurs énumérables d'un objet donné.
    *   **Usage :** Itérer sur les valeurs, effectuer des opérations sur les valeurs.

18. **Obtenir les paires [clé, valeur] d'un objet sous forme de tableau :**
    ```javascript
    const entrees = Object.entries(monObjet); // [['cle1', valeur1], ['cle2', valeur2]]
    ```
    *   **Fonctionnement :** `Object.entries()` retourne un tableau des propres paires [clé, valeur] énumérables d'un objet donné.
    *   **Usage :** Itérer facilement sur les clés et les valeurs, convertir un objet en `Map`.

19. **Déstructuration d'objet pour accéder aux propriétés :**
    ```javascript
    const { nom, age } = personne; // si personne = { nom: 'Alice', age: 30 }
    ```
    *   **Fonctionnement :** La syntaxe de déstructuration assigne les valeurs des propriétés de l'objet `personne` à des variables du même nom.
    *   **Usage :** Accéder de manière concise aux propriétés d'un objet.

20. **Déstructuration d'objet avec renommage de variables :**
    ```javascript
    const { nom: nomUtilisateur, age: ageUtilisateur } = personne;
    ```
    *   **Fonctionnement :** Permet d'assigner la valeur d'une propriété à une variable avec un nom différent.
    *   **Usage :** Éviter les conflits de noms, rendre le code plus descriptif.

21. **Déstructuration d'objet avec valeurs par défaut :**
    ```javascript
    const { nom, age, ville = 'Inconnue' } = personne;
    ```
    *   **Fonctionnement :** Si la propriété `ville` n'existe pas dans `personne` (ou est `undefined`), la variable `ville` prendra la valeur par défaut 'Inconnue'.
    *   **Usage :** Gérer les propriétés optionnelles.

22. **Propriétés d'objet dynamiques (Computed Property Names) :**
    ```javascript
    const nomProp = 'couleur'; const monObjet = { [nomProp]: 'bleu' }; // { couleur: 'bleu' }
    ```
    *   **Fonctionnement :** Permet d'utiliser une expression (ici, la variable `nomProp`) comme nom de clé lors de la création d'un objet.
    *   **Usage :** Créer des objets avec des clés déterminées à l'exécution.

**Chaînes de Caractères (Strings)**

23. **Vérifier si une chaîne commence par un certain préfixe :**
    ```javascript
    const commenceParHttp = url.startsWith('http://');
    ```
    *   **Fonctionnement :** La méthode `startsWith()` détermine si une chaîne de caractères commence par les caractères d'une chaîne de caractères spécifiée.
    *   **Usage :** Validation de format, routage simple.

24. **Vérifier si une chaîne se termine par un certain suffixe :**
    ```javascript
    const finitParPng = fichier.endsWith('.png');
    ```
    *   **Fonctionnement :** La méthode `endsWith()` détermine si une chaîne de caractères se termine par les caractères d'une chaîne de caractères spécifiée.
    *   **Usage :** Vérification de type de fichier, validation.

25. **Vérifier si une chaîne inclut une autre chaîne :**
    ```javascript
    const contientMot = phrase.includes('JavaScript');
    ```
    *   **Fonctionnement :** La méthode `includes()` détermine si une chaîne de caractères est contenue dans une autre chaîne de caractères. Sensible à la casse.
    *   **Usage :** Recherche de sous-chaînes.

26. **Répéter une chaîne plusieurs fois :**
    ```javascript
    const etoiles = '*'.repeat(5); // "*****"
    ```
    *   **Fonctionnement :** La méthode `repeat()` construit et retourne une nouvelle chaîne qui contient le nombre de copies spécifié de la chaîne sur laquelle elle a été appelée, concaténées.
    *   **Usage :** Mise en forme, génération de motifs.

27. **Template Literals (Gabarits Chaînes) pour l'interpolation :**
    ```javascript
    const message = `Bonjour, ${nomUtilisateur} ! Vous avez ${ageUtilisateur} ans.`;
    ```
    *   **Fonctionnement :** Les gabarits chaînes (entourés de backticks `` ` ``) permettent d'insérer des expressions (variables, appels de fonctions) directement dans une chaîne en utilisant la syntaxe `${expression}`.
    *   **Usage :** Construction de chaînes dynamiques de manière lisible.

**Fonctions et Logique**

28. **Fonctions Fléchées (Arrow Functions) concises :**
    ```javascript
    const addition = (a, b) => a + b;
    ```
    *   **Fonctionnement :** Syntaxe plus courte pour définir des fonctions. Si le corps de la fonction est une seule expression, le `return` est implicite.
    *   **Usage :** Callbacks, fonctions simples. (Attention au `this` qui est lexicalement lié).

29. **Valeurs par défaut pour les paramètres de fonction :**
    ```javascript
    const saluer = (nom = 'Visiteur') => `Bonjour, ${nom} !`;
    ```
    *   **Fonctionnement :** Si un argument n'est pas fourni pour `nom` (ou si `undefined` est passé), `nom` prendra la valeur par défaut 'Visiteur'.
    *   **Usage :** Rendre les fonctions plus robustes en gérant les arguments manquants.

30. **Opérateur Ternaire pour des conditions simples :**
    ```javascript
    const statut = age >= 18 ? 'Majeur' : 'Mineur';
    ```
    *   **Fonctionnement :** Une alternative concise à `if/else` pour des assignations conditionnelles simples. `condition ? valeurSiVrai : valeurSiFaux`.
    *   **Usage :** Assignations conditionnelles rapides, expressions courtes.

31. **Opérateur de Coalescence des Nuls (Nullish Coalescing Operator `??`) :**
    ```javascript
    const valeur = entreeUtilisateur ?? 'Valeur par défaut';
    ```
    *   **Fonctionnement :** Retourne l'opérande de droite si celui de gauche est `null` ou `undefined`. Sinon, retourne l'opérande de gauche. Différent de `||` qui considère aussi `0`, `''`, `false` comme "falsy".
    *   **Usage :** Fournir des valeurs par défaut lorsque `null` ou `undefined` sont des états valides mais nécessitent un fallback.

32. **Opérateur de Chaînage Optionnel (Optional Chaining `?.`) :**
    ```javascript
    const nomRue = utilisateur?.adresse?.rue; // undefined si utilisateur ou adresse est null/undefined
    ```
    *   **Fonctionnement :** Permet de lire la valeur d'une propriété située profondément dans une chaîne d'objets connectés sans avoir à valider explicitement que chaque référence dans la chaîne est valide. Si une référence est `null` ou `undefined`, l'expression s'arrête et retourne `undefined`.
    *   **Usage :** Accéder de manière sûre à des propriétés imbriquées.

33. **Assignation par Décomposition (Tableaux) :**
    ```javascript
    const [premier, second] = monTableau;
    ```
    *   **Fonctionnement :** Assigne les éléments d'un tableau à des variables individuelles.
    *   **Usage :** Extraire facilement des éléments d'un tableau.

34. **Échanger deux variables sans variable temporaire (avec décomposition) :**
    ```javascript
    [a, b] = [b, a];
    ```
    *   **Fonctionnement :** Crée un tableau temporaire `[b, a]` puis déstructure ses valeurs dans `a` et `b`.
    *   **Usage :** Un moyen élégant d'échanger des valeurs.

**Asynchrone (Promises)**

35. **Consommer une Promise avec `async/await` :**
    ```javascript
    async function fetchData() { try { const data = await maPromise(); console.log(data); } catch (e) { console.error(e); } }
    ```
    *   **Fonctionnement :** `async` déclare une fonction asynchrone. `await` met en pause l'exécution de la fonction `async` jusqu'à ce que `maPromise` soit résolue ou rejetée. `try/catch` gère les erreurs.
    *   **Usage :** Écrire du code asynchrone qui ressemble à du code synchrone, de manière plus lisible.

36. **Retourner implicitement une Promise résolue depuis une fonction `async` :**
    ```javascript
    const obtenirDonnees = async () => 'Données récupérées'; // Retourne une Promise résolue avec 'Données récupérées'
    ```
    *   **Fonctionnement :** Une fonction `async` retourne toujours une Promise. Si vous retournez une valeur, la Promise est résolue avec cette valeur.
    *   **Usage :** Simplifier la création de fonctions qui retournent des Promises.

**Autres**

37. **Obtenir l'horodatage actuel (timestamp) :**
    ```javascript
    const timestamp = Date.now(); // ou +new Date()
    ```
    *   **Fonctionnement :** `Date.now()` retourne le nombre de millisecondes écoulées depuis le 1er janvier 1970 00:00:00 UTC.
    *   **Usage :** Mesurer des durées, générer des identifiants uniques (basiques).

38. **Arrondir un nombre à N décimales :**
    ```javascript
    const arrondi = parseFloat(nombre.toFixed(2)); // Arrondit à 2 décimales et reconvertit en nombre
    ```
    *   **Fonctionnement :** `toFixed(2)` formate un nombre en chaîne avec 2 décimales. `parseFloat()` reconvertit en nombre.
    *   **Usage :** Affichage de prix, mesures.

39. **Générer un nombre aléatoire dans une plage :**
    ```javascript
    const aleatoireEntre = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min;
    ```
    *   **Fonctionnement :** `Math.random()` donne un nombre entre 0 (inclus) et 1 (exclu). On ajuste l'échelle et on translate pour obtenir la plage souhaitée. `Math.floor()` pour obtenir un entier.
    *   **Usage :** Jeux, simulations, tests.

40. **Vérifier si une variable est un tableau :**
    ```javascript
    const estTableau = Array.isArray(maVariable);
    ```
    *   **Fonctionnement :** `Array.isArray()` est la méthode la plus fiable pour déterminer si une valeur est un tableau.
    *   **Usage :** Validation de type avant d'utiliser des méthodes de tableau.

---

## Fonctions

---

1.  **`Array.prototype.map()`**
    ```javascript
    const idsProduits = produits.map(produit => produit.id);
    const elementsLi = donnees.map(item => `<li>${item.nom}</li>`);
    ```
    *   **Fonctionnement :** Crée un **nouveau tableau** avec les résultats de l'appel d'une fonction fournie sur chaque élément du tableau d'origine. Elle ne modifie pas le tableau original.
    *   **Tâches Concrètes (Développement Web) :**
        *   Transformer des données reçues d'une API pour les adapter à l'affichage (ex: extraire uniquement les noms d'une liste d'objets utilisateurs).
        *   Générer des listes d'éléments JSX/HTML à partir d'un tableau de données (très courant en React, Vue, Angular).
        *   Créer des tableaux de valeurs calculées (ex: une liste de prix TTC à partir de prix HT).

2.  **`Array.prototype.filter()`**
    ```javascript
    const produitsEnStock = produits.filter(produit => produit.stock > 0);
    const commentairesActifs = commentaires.filter(commentaire => commentaire.estApprouve);
    ```
    *   **Fonctionnement :** Crée un **nouveau tableau** contenant uniquement les éléments du tableau d'origine qui passent un test (la fonction de rappel retourne `true`).
    *   **Tâches Concrètes (Développement Web) :**
        *   Filtrer des listes de données basées sur des critères de recherche ou des états (ex: afficher uniquement les tâches complétées, les produits d'une certaine catégorie).
        *   Retirer les éléments invalides ou non désirés d'un tableau avant traitement ou affichage.
        *   Implémenter des fonctionnalités de filtrage dans une interface utilisateur.

3.  **`Array.prototype.find()`**
    ```javascript
    const utilisateurCourant = utilisateurs.find(user => user.id === idUtilisateurConnecte);
    const articleSelectionne = articles.find(article => article.slug === 'mon-super-article');
    ```
    *   **Fonctionnement :** Retourne la **valeur du premier élément** du tableau qui satisfait la condition fournie par la fonction de test. Si aucun élément ne correspond, retourne `undefined`.
    *   **Tâches Concrètes (Développement Web) :**
        *   Récupérer un objet spécifique d'une liste en fonction d'un identifiant unique.
        *   Vérifier si un élément avec certaines caractéristiques existe dans une collection.
        *   Trouver l'objet de configuration correspondant à une route active.

4.  **`Array.prototype.reduce()`**
    ```javascript
    const totalPanier = itemsPanier.reduce((total, item) => total + (item.prix * item.quantite), 0);
    const categoriesComptees = produits.reduce((acc, produit) => {
      acc[produit.categorie] = (acc[produit.categorie] || 0) + 1;
      return acc;
    }, {}); // Résultat: { electronique: 5, livres: 3 }
    ```
    *   **Fonctionnement :** Applique une fonction "réducteur" à chaque élément du tableau (de gauche à droite) pour le réduire à une **valeur unique** (l'accumulateur). Le deuxième argument de `reduce` est la valeur initiale de l'accumulateur.
    *   **Tâches Concrètes (Développement Web) :**
        *   Calculer des sommes, des moyennes, ou d'autres agrégats à partir de listes (ex: total d'un panier d'achat).
        *   Regrouper des données ou les transformer en une structure différente (ex: compter le nombre d'éléments par catégorie, créer un objet "lookup" comme vu précédemment).
        *   Aplatir des tableaux (bien que `flat()` soit souvent plus simple pour cela).

5.  **Fonctions Fléchées `=>`**
    ```javascript
    elements.forEach(element => element.classList.add('active'));
    fetch('/api/data').then(response => response.json()).then(data => console.log(data));
    ```
    *   **Fonctionnement :** Fournissent une syntaxe plus concise pour écrire des fonctions. Crucialement, elles n'ont pas leur propre `this` ; elles héritent le `this` du contexte lexical environnant.
    *   **Tâches Concrètes (Développement Web) :**
        *   Callbacks pour les méthodes de tableau (`map`, `filter`, `forEach`, etc.).
        *   Gestionnaires d'événements simples.
        *   Callbacks pour les Promises (`.then()`, `.catch()`).
        *   Rend le code plus court et souvent plus lisible pour les petites fonctions.

6.  **Déstructuration d'Objets et de Tableaux**
    ```javascript
    // Objet
    const { id, titre, contenu } = articleAPI;
    function MonComposant({ utilisateur, options }) { /* ... */ }

    // Tableau
    const [premierElement, secondElement] = monTableau;
    const [latitude, longitude] = await obtenirCoordonnees();
    ```
    *   **Fonctionnement :** Permet d'extraire des valeurs d'objets ou de tableaux et de les assigner à des variables distinctes de manière concise.
    *   **Tâches Concrètes (Développement Web) :**
        *   Extraire des propriétés spécifiques de réponses d'API ou d'objets d'état.
        *   Passer des "props" à des composants React/Vue de manière plus propre.
        *   Travailler avec les valeurs retournées par des Hooks React (ex: `const [etat, setEtat] = useState()`).
        *   Récupérer des éléments spécifiques de tableaux (ex: coordonnées, résultats multiples d'une fonction).

7.  **Template Literals (Gabarits Chaînes) `` `...${}...` ``**
    ```javascript
    const urlApi = `https://api.example.com/users/${userId}?apiKey=${API_KEY}`;
    const messageBienvenue = `<h1>Bonjour, ${utilisateur.prenom} !</h1>`;
    ```
    *   **Fonctionnement :** Permettent d'intégrer des expressions JavaScript (variables, appels de fonctions) directement dans des chaînes de caractères en utilisant la syntaxe `${expression}`. Elles supportent aussi les chaînes multi-lignes.
    *   **Tâches Concrètes (Développement Web) :**
        *   Construire des URLs dynamiques pour les appels API.
        *   Générer des chaînes HTML ou des messages dynamiques pour l'interface utilisateur.
        *   Rendre la concaténation de chaînes beaucoup plus lisible.

8.  **Opérateur de Décomposition (Spread Operator) `...`**
    ```javascript
    const nouveauxParametres = { ...anciensParametres, theme: 'sombre' }; // Fusion/Mise à jour d'objet
    const listeComplete = [...listeA, ...listeB]; // Fusion de tableaux
    maFonction(...argsTableau); // Passer les éléments d'un tableau comme arguments distincts
    ```
    *   **Fonctionnement :** "Décompose" un itérable (comme un tableau ou une chaîne) en éléments individuels, ou "étale" les propriétés d'un objet dans un autre objet.
    *   **Tâches Concrètes (Développement Web) :**
        *   Cloner des tableaux et des objets (superficiellement).
        *   Fusionner des tableaux ou des objets.
        *   Passer des props à des composants React de manière concise (ex: `<MonComposant {...propsObjet} />`).
        *   Créer de nouveaux tableaux/objets en ajoutant/modifiant des éléments/propriétés sans muter les originaux (important pour l'immutabilité).

9.  **Modules ES6 (`import` / `export`)**
    ```javascript
    // fichier utils.js
    export const calculerTotal = (a, b) => a + b;
    export default function afficherMessage(msg) { console.log(msg); }

    // fichier app.js
    import afficherMessageParDefaut, { calculerTotal } from './utils.js';
    ```
    *   **Fonctionnement :** Un système standardisé pour organiser le code en modules réutilisables. `export` rend des fonctions, objets ou primitives disponibles, et `import` les charge dans d'autres modules.
    *   **Tâches Concrètes (Développement Web) :**
        *   Structurer l'ensemble de votre application front-end et/ou back-end (Node.js).
        *   Partager des fonctions utilitaires, des composants, des services entre différentes parties de votre code.
        *   Permettre aux outils de build (Webpack, Rollup, Parcel) de faire du "tree-shaking" (éliminer le code non utilisé).

10. **Promises et `async/await`**
    ```javascript
    async function recupererDonneesUtilisateur(userId) {
      try {
        const reponse = await fetch(`/api/users/${userId}`);
        if (!reponse.ok) throw new Error(`Erreur HTTP: ${reponse.status}`);
        const donnees = await reponse.json();
        return donnees;
      } catch (erreur) {
        console.error("Impossible de récupérer l'utilisateur:", erreur);
        // Gérer l'erreur, peut-être retourner une valeur par défaut ou relancer
      }
    }
    ```
    *   **Fonctionnement :**
        *   **Promises :** Représentent l'achèvement (ou l'échec) éventuel d'une opération asynchrone.
        *   **`async` :** Déclare une fonction qui retourne implicitement une Promise.
        *   **`await` :** Utilisé à l'intérieur d'une fonction `async`, met en pause l'exécution de la fonction jusqu'à ce que la Promise à sa droite soit résolue ou rejetée. Si résolue, retourne la valeur de résolution. Si rejetée, lève l'erreur.
    *   **Tâches Concrètes (Développement Web) :**
        *   Effectuer des appels API (`fetch`).
        *   Interagir avec des bases de données côté serveur (Node.js).
        *   Gérer toute opération qui prend du temps et qui ne doit pas bloquer le thread principal (ex: lecture de fichier, timers complexes).
        *   Rendre le code asynchrone beaucoup plus lisible et semblable à du code synchrone.

11. **`fetch()` API**
    ```javascript
    fetch('https://api.example.com/data')
      .then(response => {
        if (!response.ok) throw new Error('Réponse réseau non OK');
        return response.json(); // Parse la réponse JSON en objet JS
      })
      .then(data => console.log('Données reçues:', data))
      .catch(error => console.error('Erreur de fetch:', error));
    ```
    *   **Fonctionnement :** Une interface JavaScript moderne pour effectuer des requêtes HTTP (remplace `XMLHttpRequest`). Elle est basée sur les Promises.
    *   **Tâches Concrètes (Développement Web) :**
        *   Récupérer des données depuis des APIs RESTful.
        *   Envoyer des données à un serveur (avec les méthodes `POST`, `PUT`, etc., en configurant l'objet `options` de `fetch`).
        *   Interagir avec des services tiers.

12. **Paramètres de Fonction par Défaut**
    ```javascript
    function creerElement(tag = 'div', contenu = '', classes = []) {
      const element = document.createElement(tag);
      element.textContent = contenu;
      element.classList.add(...classes);
      return element;
    }
    ```
    *   **Fonctionnement :** Permet d'assigner des valeurs par défaut aux paramètres d'une fonction si aucun argument n'est fourni pour eux, ou si `undefined` est passé.
    *   **Tâches Concrètes (Développement Web) :**
        *   Rendre les fonctions plus flexibles et moins sujettes aux erreurs si certains arguments sont optionnels.
        *   Définir des configurations par défaut pour des fonctions utilitaires ou des constructeurs de composants.

13. **Paramètres Rest `...`**
    ```javascript
    function sommerTous(...nombres) { // nombres devient un tableau [1, 2, 3, 4]
      return nombres.reduce((sum, num) => sum + num, 0);
    }
    sommerTous(1, 2, 3, 4); // Retourne 10
    ```
    *   **Fonctionnement :** Permet à une fonction de recevoir un nombre indéfini d'arguments sous forme d'un tableau. Doit être le dernier paramètre de la fonction.
    *   **Tâches Concrètes (Développement Web) :**
        *   Créer des fonctions qui acceptent un nombre variable d'arguments (ex: une fonction de logging, une fonction qui combine plusieurs objets de configuration).
        *   Transférer des arguments d'une fonction à une autre.

14. **Optional Chaining `?.`** (Déjà vu, mais son utilité en dev web est immense)
    ```javascript
    const nomAuteur = article?.auteur?.nom ?? 'Anonyme';
    const onClickHandler = props.callbacks?.onClick; // si onClick est optionnel
    if (onClickHandler) onClickHandler();
    ```
    *   **Fonctionnement :** Permet d'accéder à des propriétés ou d'appeler des méthodes sur des objets potentiellement `null` ou `undefined` sans causer d'erreur. Si une partie de la chaîne est `null` ou `undefined`, l'expression entière court-circuite et retourne `undefined`.
    *   **Tâches Concrètes (Développement Web) :**
        *   Accéder en toute sécurité à des données imbriquées provenant d'API ou d'états complexes (très fréquent dans les applications React/Vue/Angular).
        *   Appeler des fonctions de rappel optionnelles passées en props.
        *   Réduire la verbosité des vérifications `if (obj && obj.prop && obj.prop.subProp)`.

15. **`Object.entries()`, `Object.keys()`, `Object.values()`**
    ```javascript
    const config = { theme: 'dark', fontSize: 16, showTooltips: true };
    Object.keys(config).forEach(key => console.log(key)); // 'theme', 'fontSize', 'showTooltips'
    Object.values(config).forEach(value => console.log(value)); // 'dark', 16, true
    for (const [key, value] of Object.entries(config)) {
      console.log(`${key}: ${value}`);
    }
    ```
    *   **Fonctionnement :**
        *   `Object.keys(obj)` : Retourne un tableau des propres clés énumérables de `obj`.
        *   `Object.values(obj)` : Retourne un tableau des propres valeurs énumérables de `obj`.
        *   `Object.entries(obj)` : Retourne un tableau de paires `[clé, valeur]` des propres propriétés énumérables de `obj`.
    *   **Tâches Concrètes (Développement Web) :**
        *   Itérer sur les propriétés d'un objet de configuration pour les afficher ou les traiter.
        *   Vérifier si un objet contient certaines clés ou valeurs.
        *   Transformer des objets (ex: convertir un objet en `Map`, ou filtrer un objet pour ne garder que certaines paires clé/valeur).
        *   Afficher dynamiquement les données d'un objet dans une interface utilisateur.

---


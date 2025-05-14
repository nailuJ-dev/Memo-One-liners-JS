# Memo-One-liners-JS
Try to compile the most useful JS one-liners

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



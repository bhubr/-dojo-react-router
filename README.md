# Dojo React Router

:point_right: **Commencez par cloner ce repo** et vous y placer, puis installez les dépendances :

- soit via `npm install` ou `npm i`,
- soit en installant `pnpm`, alternative à NPM plus rapide : `npm i -g pnpm`, **puis** `pnpm install`

Objectif :

- Savoir installer et mettre en place React Router
- Associer un composant à un "path" (chemin relatif)
- Gérer les paramètres d'URL

## "Scope"

Vous allez devoir créer un mini-blog contenant 3 routes :

- une page d'accueil qui va afficher une liste d'articles (données fournies, voir plus loin).

  - chemin : `/`
  - nom du composant : `HomePage`

- une page "à propos"

  - chemin : `/about`
  - nom du composant : `About`

- une page "contact"

  - chemin : `/contact`
  - nom du composant : `Contact`

- une page affichant les détails d'un article (à faire en dernier)

  - chemin : `/post/:id`
  - nom du composant : `PostDetails`

## Ordre

En cas de coup dur, "RTFM" (ça veut lire "lisez la doc").

![RTFM](https://binuxlubuntu.files.wordpress.com/2009/10/mao_rtfm_vectorize_by_cmenghi.png)

1. Commencez par installer React Router dans le projet. Attention, comme mentionné dans la [section Quick Start de la doc](https://reactrouter.com/web/guides/quick-start), c'est le module `react-router-dom` qu'il faut installer. :warning: Vous n'avez pas besoin d'utiliser `create-react-app`, c'est déjà fait !
2. Vous pouvez :

- soit suivre la doc et importer `BrowserRouter` depuis `App.jsx` (renommé dans l'exemple en `Router` lors de l'import)
- soit l'importer depuis `index.jsx`, et alors entourer `<App />` avec les balises `<Router>` ... `</Router>` (ou `<BrowserRouter>` ... `</BrowserRouter>`)

3. Ecrivez les 4 composants, sous forme de **fonctions**, qui peuvent ne renvoyer qu'un contenu minimal pour l'instant (une "div" vide).
4. Mettez en place la structure avec le `Switch` et à l'intérieur, les `Route`, pour associer les composants aux chemins.
5. Testez en changeant l'URL dans la barre d'adresse
6. Créez un composant `Navbar` que vous appellerez depuis `App`, mais en le plaçant en-dehors (au-dessus) du `Switch`. Vous utiliserez 3 `Link` pour mener à la homepage, à la page "à propos", à la page contact.
7. Dans le composant `HomePage`, importez les articles depuis le fichier `src/data/posts.json`, puis faites un `map` pour afficher autant de `div` que d'articles. Pour chaque article, affichez son `title` dans un `h3`, et son `body` dans un `p`.
8. Dans le composant `Post`, cherchez à afficher le paramètre d'URL `id`. Pour tester, comme on n'a pas mis de lien vers cette page dans la navbar, essayez de mettre le chemin `/posts/1` dans la barre d'adresse (après l'URL http://localhost:3000). Indice : examinez les props de `Post` dans les React Dev Tools. On y trouve `params`, un objet qui contient un autre objet `match`, contenant les paramètres d'URL.
9. Comme dans HomePage, importez le fichier d'articles. Essayez de n'afficher que l'article correspondant au paramètre `id` passé via l'URL. Vous pouvez utiliser `filter` ou une variante ne renvoyant qu'un seul élément, [find](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array/find). Attention, vous aurez besoin de convertir le paramètre d'URL `id` en nombre pour pouvoir utiliser filter ou find correctement.

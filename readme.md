# Documentation

## Convention BEM

B -> Block
E -> Element
M -> Modifier

```html
<!-- mainList = Block -->

<ul class="mainList mainList--xmas">
  <!-- _item = Element -->
   <li class="mainList_item">
     <a href="/home" class="mainList_itemLink--isActive">Home</a>
   </li>
   <li class="mainList_item">
     <a href="/about" class="mainList_itemLink">About</a>
   </li>
   <li class="mainList_item">
     <a href="/works" class="mainList_itemLink">Works</a>
   </li>
</ul>
```

```css
.mainList {
  display: flex;
  justify-content: space-between;
  &--xmas {
    background: green;
  }
  &__item {
    list-style: none;
  }
  &__itemLink {
    color: red;
    &--isActive {
      color: white;
    }
  }
}
```

Exemple en CSS du rendu :

```css
.mainList {
}
.mainList--xmas {
}
.mainList_item {
}
.mainList_itemLink {
}
.mainList_itemLink--isActive {
}
```

## Pseudo attributs

Les pseudo attributs 'before' et 'after' permmettent de créer des noeuds HTML en CSS. Ils sont essentiellement utilisés pour ajouter des ornements, des decorations... On peut bien entendu faire des animations avec, les positionner par rappaort à leur parent (relative / absolute). **Ils doivent obligatoirement avoir un 'content:'** afin de s'afficher

```html
 <section class="cover">
    <h1 class='cover_mainTitle'>Presentation des Pseudo-attributs</h1>
 </section>
```

```CSS
.cover{
  background: #FDFDFD;
  padding: 20px;
  &-mainTitle{
    text-align: center;
    font-size: 24px;
    color: green;
    &::before,
    &::after{
      content: '';
      display: block;
      width: 30px;
      height: 30px;
      background: green;
      top: 0;
    }
    &::before{
      left: 0;
    }
    &::after{
      right: 0;
    }
  }
}
```

## REM, EM, %, VW Sizing

## %

## EM

```css
.cover {
  font-size: 16px;
  @_maintitle {
    /* 1em === 16px  */
    font-size: 0.8em;
  }
}
```

## REM

- Le REM est basé sur la taille de la racine (suit la balise <html>)qui, par défaut a une valeur de 16px. Afin d'eviter tout calcul, il est necessaire de l'ecraser en donnant une base de 18px soit 62.58.
- Le REM est intéressant a utiliser si les media-queries employées sont en rem egalement. Cela vous permettra de garder les proportions égales lorsqu'on va redimensionner la page
- Ses proportions seront également gardées quand l'utilisateur zoomera dans votre pageAccueil

```css
html {
  font-size: 62.5%;
}
.mainTitle {
  font-size: 3.6em;
  width: 30rem;
}
```

## VW() / VH()

- Unités relatives à la taille de votre ecran (peu importe le device)
- Attention au VH et a son contenu. 100vh ==100
- VH : très utiles pour les interfaces fluides

## Utiliser Parcel Starter pack via terminal

- Rentrer dans le dossier correspondant et faire npm init (cela va creer un package.json). Il va demander plusieurs informations mais on va uniquement remplir le package name qui va etre le nom du dossier , la version 1.0.0

- On rentre dans le dossier avec un editeur (atom .) et dans package.json on rajoute les scripts et les dependencies :

```
"main": "index.js",
"scripts":{
  "start": "parcel index.html",
  "build": "parcel index.js"
},
"author": "",
"license": "ISC",
"dependencies": {
  "parcel-bundler": "^1.6.2",
  "node-sass": "^4.7.2"
}
```

- Ensuite pour on va mettre parcel-bundler dans le fichier en question avec npm install .

- Pour lancer le fichier on va ecrire dans le terminal npm start ou (npm run start) , ensuite on va dans un navigateur puis on marque localhost:1234;

- Tout ce qui est en dehors du dossier "src" normalement on ne doit plus les toucher

- Les fichiers .postcssrc et babelrc permet de de changer le code directement selon le navigateur

* Pour utiliser les FLEXBOX : npm install flexboxgrid dans le terminal , dans le fichier ecrire import 'flexboxgrid'

## Flexbox Grid

- Systeme de Grid basé sur flexbox. Install via terminal npm ou download le fichier et le linker avec son fichier html

- Permet de placer ces elements selon une grille de 12 colonnes , simplifie egalement le responsive avec des media queries deja defini (notamment pour le layout) avec des tailles differentes.

- Pour commencer il faut placer une classe 'row' , tout les elements placer a l'interieur de la classe se mettront en display flex.

```html
 <div class='row'>

 </div>
```

- Ensuite pour placer mes elements on va placer les classes 'col-xs-12' où le 'xs' correspond au device et '12' le nombre de grille que mon element va prendre. Il y a quatre format de devices ==> col-xs col-sm col-md col-lg.

```html
 <div class='row'>
    <div class='col-xs-12'>
      <p>Hello</p>
    </div>
 </div>
```

- On a egalement la possibilité de placer les elements en offset et d'utiliser des proprietes flex plus facilement en rajoutant des classes au row . Possibilité d'imbriquer mes classes.

```html
 <div class='row center-xs top-xs'>
    <div class='col-xs-12 col-md-offset-4'>

      <p>Hello</p>

      <div class='row start-xs between-xs'>

          <div class='col-xs-offset-1 col-lg-12'>

                <p>Yo</p>

                <p>Oy</p>

          </div>
      </div>

    </div>
 </div>
```

## Bulma

- CSS Framework basé sur flexbox . Install via terminal npm ou download fichier et le linker

- Contient des variables de depart pour les couleurs , font-size etc mais on peut declarer des variables par nous mêmes

```html
 <p class="has-text-success is-size-4"> Bulma </p>
```

- On va utiliser les classes 'columns' et 'column' pour placer ces elements en flex , tout les elements dans columns vont se placer en display flex et les column auront tous des width similaires peu importe le nombre de column

```html


<div class="columns">
     <div class="column"></div>

      <div class="column"></div>

     <div class="column"></div>

</div>
```

- https://bulma.io/ ==> voir la doc 

## Liens utiles:

https://caniuse.com/ --> savoir sur quelle navigateur le CSS marche

https://github.com/awesome-css-group/awesome-css --> awesome CSS

https://github.com/diegocard/awesome-html5 --> awesome HTML

https://github.com/sorrycc/awesome-javascript --> awesome JS

# my-form

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

********************************************************************************************

0/Pré-requis nodeJS d'installé:
npm install -g @vue/cli | vue create <name-project> | cd <name-project> | npm run serve

npm run serve:

1/Formulaire de base avc les inputs : lié nos données à ds input, on utilise 'v-model'
*Pas d'action en attribut dans la balise <form> car on ne fait que la partie "front"...
*class form group (form-control dans les inputs egalement) pr styliser le tout via bootstrap
*Il faut lié nos data() à nos input via v-model !
*Interpolation , composant moustache sous les Résultats

2/Astuce formulaire :
* Mettre toutes ls données relative à un formulaire via formData: {}
*Dans le <textarea>, "white-space: pre" : pr passer à la ligne en appuyant sur entrée

3/ Gérer les checkbox :
Très important de renseigner "value", puis de faire v-model et le lier à un [] dans le <form> et l'afficher avc une boucle for pour l'afficher en dehors du <form>
v-bind:key="index" pour fruit | index unique à chaque éléménet de liste que l'on va créer

4/Gerer les select Box : pas besoin d'ID , Vue ns propose qqch, on fait juste une balise <option>
et on complete le formdData (via select:'' et listePays: ['xxx','xxx'...]) de data()
v-model="formData.select" pour le <select>, le lié à nos data()!


5/Envoyer les données (submit): comment envoyer les données en local.
On a pas de backend, mais par exemple avec firebase
un formulaire ça marche soit avec un "input" type submit ou un <button>...
* v-if="infoSubmit" : div que l'on affiche seulement apres avoir valider les données
* v-on:click.prevent="envoiForm" et on crée la fct 'envoiForm' dans methods, le prevent pour maintenir le result et donc l'affichage apres avoir submit le result
* v-on: input (un évènement)







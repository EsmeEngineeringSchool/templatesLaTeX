## `td` :

Placer `td.sty` en local ou dans votre installation TEXMFHOME

### Utilisation

Pour chaque document de TD l'utilisateur doit configurer quelques variables 
dans le fichier `.tex` :

```
\promo{\texttt{PROMO}}     % ex. IngéSUP, IngéSPE, Ingé1
\module{\texttt{MODULE}}   % ex. Systèmes Techniques, Mathématiques Fondamentales
\tdno{1}                   % ex. 1 pour que TD 1
\titre{\texttt{DATE}}      % ex. Cinématique des solides indéformables 
\esme{true}                % examen ESME true or false
\reponse{true}             % document réponse true or false
```

1. `promo` : Nom de la promo (ex. IngéSUP, IngéSPE, Ingé1)
2. `module` : Nom du module (ex. Systèmes Techniques, Mathématiques Fondamentales )
3. `tdno` : Numéro du TD dans la progression
4. `titre` : Titre du TD
5. `esme` : TD au logo de l'esme
6. `reponse` : variable spécifiant si le document est un document réponse (ex. `\reponse{true}` ou `\reponse{false}` 

Si `\reponse{true}` vous pouvez utiliser la commande `\feuilleDR{10cm}`
qui insère une grille réponse de 10cm de hauteur.

### Sujet en français et en anglais.

Vous pouvez utiliser la commande `\fr{<texte en français>}{<texte en anglais>}` 
pour permettre d'interpréter à la fois le texte en français et en anglais selon 
la langue utilisée en option du paquet `babel`.

Note : Vous pouvez utiliser la commande `\fr{}{}` à l'intérieur d'autres commandes. Cela peut être utile 
pour la définition des variables précédentes ou les commandes `\exercice` et `\question`. 
```
\module{\fr{Mathématiques}{Mathematics}}

\exercice{\fr{Le pendule simple}{Pendulum}}
```

### Aperçu

#### Page de titre
![Page de titre](../img/exemple_td.png)
#### Exemple avec grilles
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/exemple_sujet_reponses-1.png?raw=true)



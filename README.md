# esme

Templates LaTeX de l'ESME. 

## beamer :

Il existe deux thèmes : `esmeDL`(nouveau) et `esme` (ancien). 
Ces deux thèmes nécessitent l'option `aspectratio=169` de la classe beamer :

```
\documentclass[aspectratio=169,11pt]{beamer}
```

Deux possibilités :
1. copier les fichiers `*.sty` et le dossier `img/` 
   en local avec votre fichier `.tex`

ou 

2. copier le dossier `beamer` dans votre TEXMFHOME (ex.  ~/texmf/tex/latex/ )
   ou le dossier `esme` dans `beamer/themes` si ces derniers existent déjà  
### Aperçu (thème esmeDL)

#### Page de titre
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/esmeDL-example-0.png?raw=true)
#### Frame title 
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/esmeDL-example-1.png?raw=true)
#### Section page 
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/esmeDL-example-4.png?raw=true)

### Aperçu (thème esme)

#### Page de titre
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/esme-example-0.png?raw=true)
#### Frame title 
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/esme-example-1.png?raw=true)
#### Section page 
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/esme-example-4.png?raw=true)

## examen :

Placer `examen.sty` en local ou dans votre installation TEXMFHOME

### Utilisation

Pour chaque examen l'utilisateur doit configurer quelques variables 
dans le fichier `.tex` :

```
\newcommand\promo{\texttt{<PROMO>}}                     
\newcommand\module{\texttt{<MODULE>}}                  
\newcommand\annee{\texttt{2022-2023}}                  
\newcommand\epreuve{\texttt{<EPREUVE>}}                
\newcommand\titreEval{\texttt{<TITRE DE L'EVALUATION>}}
\newcommand\dureeEval{\texttt{<X>}}                   
\usepackage{examen}
\reponse{false}
```

1. `promo` : Nom de la promo (ex. IngéSUP, IngéSPE, Ingé1)
2. `module` : Nom du module (ex. Systèmes Techniques, Mathématiques Fondamentales )
3. `annee` : Année scolaire (ex. 2022-2023)
4. `epreuve` : Nom de l'épreuve (ex. Midterm, Final Exam)
5. `titreEval` : Nom de l'évaluation (ex. Dynamique et Déformation, Série Entière)
6. `dureeEval` : Nombre d'heures de l'évaluation (ex. 2)
7. `reponse` : variable spécifiant si le document est un document réponse (ex. `\reponse{true}` ou `\reponse{false}` 


Si `\reponse{true}` vous pouvez utiliser la commande `\feuilleDR{10cm}`
qui insère une grille réponse de 10cm de hauteur.

### Exemples :
 Le dépôt propose des exemples :
1. Examen classes anglophones :
 `example_test.tex`  `example_test_responses.tex`
2. Examen classes francophones :
`exemple_sujet.tex`  `exemple_sujet_reponses.tex`

avec ou sans grille réponses.

### Aperçu

#### Page de titre
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/exemple_sujet_reponses-0.png?raw=true)
#### Exemple de grille de réponse 
![Page de titre](https://github.com/FilipeVasconcelos/esme/blob/main/img/exemple_sujet_reponses-1.png?raw=true)

### Sujet en français et en anglais.

Vous pouvez utiliser la commande `\fr{<texte en français>}{<texte en anglais>}` 
pour permettre d'interpréter à la fois le texte en français et en anglais selon 
la langue utilisée en option du paquet `babel`.

Note : Vous pouvez utiliser la commande \fr{}{} à l'intérieur d'autres commandes. Cela peut être utile 
pour la définition des variables précédentes ou les commandes exercice et question. 
```
\module{\fr{Mathématique}{Mathematics}}

\exercice{\fr{Le pendule simple}{Pendulum}}
```

# Template `examen`

## Utilisation

Placer `examen.sty` en local ou dans votre installation TEXMFHOME

Pour chaque examen l'utilisateur doit configurer quelques variables 
dans le fichier `.tex` :

```latex
\promo{\texttt{PROMO}}     % ex. IngéSUP, IngéSPE, Ingé1
\module{\texttt{MODULE}}   % ex. Systèmes Techniques, Mathématiques Fondamentales
\annee{\texttt{DATE}}      % ex. 2022-2023
\epreuve{\texttt{EPREUVE}} % ex. MidTerm, FinalExam, Rattrapage
\titreEval{\texttt{TITRE}} % ex. Dynamique et Déformation
\dureeEval{\texttt{2}}     % ex. 2 (en nombre d'heures)
\esme{true}                % examen ESME true or false
\grille{true}              % document grille réponse true or false
\documentautorise{false}   % documents autorisés
\moyencalcul{false}        % moyen de calcul autorisés
\dispositions{false}       % dispositions en cas d'erreur rencontrée
\corrige{false}            % produire le corrigé
```

1. `promo` : Nom de la promo (ex. IngéSUP, IngéSPE, Ingé1)
2. `module` : Nom du module (ex. Systèmes Techniques, Mathématiques Fondamentales )
3. `annee` : Année scolaire (ex. 2022-2023)
4. `epreuve` : Nom de l'épreuve (ex. Midterm, Final Exam)
5. `titreEval` : Nom de l'évaluation (ex. Dynamique et Déformation, Série Entière)
6. `dureeEval` : Nombre d'heures de l'évaluation (ex. 2)
7. `esme` : Examen au logo de l'esme
8. `grille` : variable spécifiant si le document est un document réponse  
9. `documentautorise` : Les documents sont-ils autorisés ?
10. `moyendecalcul` : Les moyens de calcul sont-ils autorisés ?
11. `dispositions` : Afficher une phrase concernant la rencontre d'une erreur d'énoncé
12. `corrige` : Produire le document corrigé en utilisant les macros `\reponse{}`

Si `\corrige{true}` vous pouvez utiliser la commande `\grillereponse[10cm]{Le texte de la réponse}`
qui insère une grille réponse de 10cm de hauteur et permet de définir le texte de la réponse.

### Sujet en français et en anglais.

Vous pouvez utiliser la commande `\fr{<texte en français>}{<texte en anglais>}` 
pour permettre d'interpréter à la fois le texte en français et en anglais selon 
la langue utilisée en option du paquet `babel`.

Note : Vous pouvez utiliser la commande `\fr{}{}` à l'intérieur d'autres commandes. Cela peut être utile 
pour la définition des variables précédentes ou les commandes `\exercice{}`, `\question{}` ou `\grillereponse{}`. 
```latex
\module{\fr{Mathématiques}{Mathematics}}

\exercice{\fr{Le pendule simple}{Pendulum}}

\question{\fr{Quelle est la valeur de $\pi$ ?}{What is the value of $\pi$?}}

\grillereponse[6cm]{\fr{La réponse est $\sqrt{2}$}{The answer is $\sqrt{2}$}}
```

### Exemples :
   Plusieurs exemples sont présentés dans le repertoire `exemples`.

### Astuces

#### Variables utiles
Il n'est pas nécessaire d'utiliser grillereponse pour obtenir un corrigé.
Il est également possible d'utiliser `\ifeditiongrillereponse` si l'on souhaite
que certaines parties ne soient affichées que dans le cas de l'édition corrigé du document.
ou encore avec la construction plus globale :
```latex
\ifeditiongrillereponse
    Ce qui sera affiché au corrigé
\else
    Ce qui ne sera pas affiché dans le corrigé
\fi
```

#### Pour la compilation 

Il est tout à fait possible de n'avoir qu'un seul et unique fichier `.tex` et
de compiler les différentes versions à l'aide d'un script qui filtre les valeurs
de la langue, des paramètres de grille réponse ou de corrigé.

On pourra par exemple utiliser les instructions dans le fichier source:
```latex
\usepackage[__LANG__]{babel}
\corrige{__CORRIGE__}
\grille{__GRILLE__} 
```
et appliquer un filtre avant la compilation 
```bash
cat ${texin} | sed s/__LANG__/${lang}/g |
               sed s/__CORRIGE__/${corrige}/g |
                sed s/__GRILLE__/${grille}/g > ${texout}.tex
```
en bouclant sur toutes les valeurs souhaitées.

#### Page de titre
<img src="../img/exemple_sujet_grille-0.png" width="800" class="center">

#### Exemple de grille de réponse 
<img src="../img/exemple_sujet_grille-1.png" width="800" class="center">



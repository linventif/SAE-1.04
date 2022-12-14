## Traces d'exécution textuelle

Au lance du jeu, une menu principale souvre et celui ci permet de:

- Lancer une partie

- Tableau des Scores

- Paramètres

- Quitter

### Lancer une partie

Au lancement d'une partie, le joueur a un résumé bref de sa mission lui expliquant le context et ce qu'il doit faire.

```text
Bonjour Désamorceur, vous avez été choisi pour désamorcer une bombe.
Voici votre manuel d'utilisation de la bombe, il vous expliquera comment la désamorcer.
Cependant la bombe est instable, si vous faite 3 erreurs, la bombe explosera.
Bon courage.
```

Pour que l'expliquation se ferme et que la partie commence le joueur doit appuyer sur entrée.

Après cela le joueur peut voir la bombe, et le manuel.

L'écran du joueur est divisé en 3 parties:

```text
|                 |                 |
|      Bombe      |      Manuel     |
| _ _ _ _ _ _ _ _ | _ _ _ _ _ _ _ _ |
|        Liste des Commandes        |
```

### Bombe

La bombe et ces module sont représenté par des caractères ASCII.

Les intéractiosn avec la bombe et le manuel se font par des commandes.

#### Commandes

- tourner [direction]: tourne la bombe dans la direction [direction] (haut, bas, gauche, droite)

- module [id]: affiche le module [id] et les commandes associées

### Manuel

Le manuel est réparti en plusieurs pages, chaque page contient des informations sur un module de la bombe.

#### Commandes

- page suivante: affiche la page suivante du manuel

- page précédente: affiche la page précédente du manuel

- page [id]: ouvre la page [id] du manuel

### Tableau des Scores

Le tableau des scores est un tableau qui affiche les meilleurs scores.

Le tableau des scores est composé de 3 colonnes de 10 lignes:

- Nom

- Score

- Date

#### Calcul du score

Le score est calculé en fonction du nombre d'erreur commise, de la difficulter et du temps mis pour résoudre la bombe.

Equation: `((Nombre de Module Fait * 1000) * difficulté) / (1 + (temps / 60))`

### Paramètres

Le menu des paramètres permet de:

- Changer la difficulté

#### Difficulté

- Facile: Valeur 1 - Modules 3

- Moyen: Valeur 2 - Modules 6

- Difficile: Valeur 1 - Modules 9

Plus la difficulté est élevé, plus la bombe est complexe et le score est élevé.

## Informations Techniques

### Mocule: Coupe Fils

##### Description et Objectif

L'objectif de ce module est de coupé le bon fils parmis 5 fils, pour ce faire le joueur devera s'aider du manuel et de la théorie des ensemble.

##### Page du Manuel

```txt
a = fil vertical, b = fil en diagonal (haut gauche) - c = fil en diagonal (haut droite)
si un fil b est tout a gauche et qu'un fil a est tout a droite alors coupé le fil 4
si un fil a est tout a gauche et qu'un fil b est tout a droite alors coupé le fil 5
si tout les fils sont a alors coupé le fil 3
si la suite abaca est vrais alors coupé le fil 1
si cbacb est vrai alor coupé le fil 5
```

##### Commandes

- couper fil [id]: coupe le fil n°[id]

### Module: Terminal

##### Description et Objectif

L'objectif de ce module est d'utuliser des commande bash simple affain de supprimé un fichier ou de récupérer un code qui se trouve dans un fichier.

##### Page du Manuel

```txt
cd: permet de ...
rm: permet de ...
pwd: permet de ...
cat: permet de ...
```

##### Commandes

- [commands]: effectue une action selon [commands]

### Module: Cryptographie

##### Description et Objectif

L'objectif de ce module est d'utuliser de traduite un code secret crypter en binaire, morce, hexadecimal ou juste décaler.

##### Page du Manuel

```txt
traduction du morce
binaire
```

##### Commandes

- [commands]: effectue une action selon [commands]

### Types

#### Manuel

- Page du manuel: `Page`

#### Bombe

- Bombe: `Bombe`

- Face: `Face`

- Module: `Module`

#### Autre

- Score: `Score`


## Exemple

### Module: Coupé le bon Fil

### Module: Terminal (supprimer fichier)
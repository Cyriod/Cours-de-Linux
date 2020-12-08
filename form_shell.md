# Formation du Shell

#### Le shell ressemble à un langage de programmation. C'est-à-dire qu'il se forme de la même manière avec l'utilisation de variables, de boucles, de conditions etc...

#### Il est préférable d'avoir vu avant le [premier script](./premier_script.md) qui permet de poser les bases sur l'exécution et l'écriture d'un script.
------

## Les variables

### Déclaration et utilisation d'une variable

Pour **déclarer** une variable, il faut faire :

```bash
nomdelavar=lavaleur
```

Mais pour utiliser la **valeur** d'une variable, on écrit:

```bash
$nomdelavar
```

En bash, une variable **n'est pas typée**. Donc on peut avoir beaucoup de variables différentes :

```bash
caractere=a
mot=texte
message="texte avec espace"
messagedeux='texte avec espace 2'
nombre=2108
```
Nous verrons un peu plus tard quelle est la différence entre les **simple quotes ' '** et les **double quotes " "**.

**Exemple**

On écrit un script qui va print ``Hello World!`` mais cette fois-ci en utilisant les variables.

```bash
#!/bin/bash

var="Hello World!"

echo $var
```
(voir [ici](./new_command.md#la-commande-echo) pour l'explication du fonctionnement de echo)

Une fois le script exécuté, voici le résultat :

```bash
$ ./hello_world.sh
Hello World!
$
```
### La différence entre les ***"quotes"***

#### Single quotes (apostrophes ' ')

Dans le script 
```bash
#!/bin/bash

var="Hello World!"

echo 'la variable est : $var'
```
En sortie :

```html
$ ./hello_world.sh
la variable est : $var
$
```

En effet, ici cela écrit littéralement ce qu'il y a entre les apostrophes. (il n'y a pas d'analyse)

#### Double quotes (guillemets " ")

Dans le script 
```bash
#!/bin/bash

var="Hello World!"

echo "la variable est : $var"
```
En sortie :

```html
$ ./hello_world.sh
la variable est : Hello World!
$
```
En effet, ici cela écrit ce qu'il y a entre les apostrophes en prenant en compte les symboles spéciaux. (il y a une analyse)

#### Back quotes (les accents graves \` `)

Dans le script 
```bash
#!/bin/bash

var=`pwd`

echo "la variable est : $var"
```
En sortie :

```html
$ ./hello_world.sh
la variable est : username/Documents
$
```
Les accents graves permettent de mettre une commande dans une variable (et par conséquent de l'exécuter avec ``echo``).

### Demande de saisie

On peut utiliser la commande `read` (explication de la commande [ici](./new_command.md#la-commande-read)) afin d'assigner une valeur par la demande de saisie.

Grâce à `read` on peut faire des programmes avec des demandes de saisie du type :

Dans le script:

```bash
echo "Combien avez vous d'argent ?"

read monnaie

echo "Vous avez $monnaie€ d'argent !"
```
En sortie :

```html
$ ./monnaie.sh
Combien avez vous d'argent ?
50
Vous avez 50€ d'argent !
```
Cet exemple montre l'utilisation de `read` pour lire l'information que le script avait besoin, et retourne avec `echo` la variable.

Vous pouvez retrouver les options de la commande `read` [ici](./new_command.md#la-commande-read).

## Les variables d'environnement





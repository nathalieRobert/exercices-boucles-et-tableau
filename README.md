# exercices-boucle-et-tableau

Objectifs à atteindre samedi 27 octobre :

Etre capable de "déclarer" et d'"initialiser" un "tableau" de n'importe quel "type" et 
d'"itirer" dessus à l'aide d'une "boucle" "for" pour afficher son contenu dans la console sans avoir 
à se référer à des cours ou tout autre ressource (Internet, code des cours...)

Objectif bonus : être capable de manipuler une "chaîne de caractères" ("java.lang.String") 
de la même manière qu'un tableau de "char"

Entre guillemets : mots clés.

Étapes :

#################################################################################################

Étape A - Les fondamentaux, le vocabulaire, les raccourcis Eclipse (CTRL+SPACE notamment)

1. Créer une nouvelle classe nommée Application dans le package com.socgen.mentoring
2. Déclarer une méthode main dans cette même classe (penser au raccourci Eclipse main CTRL+SPACE)
3. Déclarer une variable de type char[] nommée firstnameArray et lui affecter un tableau de la longueur
   du prénom Nathalie. La longueur indique le nombre maximum d'éléments (ici des caractères) que peut contenir le
   tableau, cette longueur peut se spécifier à la construction entre les crochets (par exemple new char[3];)
4. Remplir le tableau caractère par caractère de N à e grâce aux index du tableau (par exemple firstnameArray[2] = 't';)
5. Déclarer une boucle for pour itérer sur le tableau firstnameArray (penser au raccourci Eclipse for CTRL+SPACE)
6. Afficher dans la console chacun des caractères du tableau grâce à l'index déclaré dans la boucle (généralement 
   nommé i et initialisé à 0)
7. Résultat attendu dans la console :

N

a

t

h

a

l

i

e

#################################################################################################

Étape B - Organiser le code pour plus de lisibilité, vocabulaire, appeler une méthode depuis une autre méthode, obtenir le même résultat 
   qu'à l'étape A mais avec une chaîne de caractère

1. Dans la classe Application, écrire une nouvelle méthode private static void printFirstnameArray() et couper-coller
   le code actuel de la méthode main dans le corps de cette nouvelle méthode (le corps de la méthode est ce qui
   se trouve entre les accolades de la méthode)
2. Appeler la méthode printFirstnameArray() depuis la méthode main, exécuter le programme, le résultat dans la console 
   doit être le même que précédamment
3. Dans la méthode printFirstnameArray() ajouter une instruction avant la boucle pour afficher dans la console la chaîne de caractères 
   "From an array of chars:"
4. Résultat attendu dans la console (test intermédiaire pour vérifier que ça fonctionne pareil après modifications du code (refactoring) :

From an array of chars:

N

a

t

h

a

l

i

e

5. Écrire une nouvelle méthode avec les mêmes modificateurs (private static) et le même type de retour (void) que printFirstnameArray() mais 
   nommée printFirstnameString()
6. Dans cette nouvelle méthode, déclarer une variable nommée firstname de type String et l'initialiser avec la valeur "Nathalie"
7. Déclarer un tableau de type char nommé firstnameArray et lui assigner le tableau de char retourné par la méthode toCharArray(). C'est une méthode 
   de la classe String, qui peut donc être appelé sur toute chaîne de caractères (variables de type String). Exemple firstname.toCharArray();. Elle 
   retourne une copie du tableau de char que représente la chaîne de caractères
8. Ajouter un "sysout" pour afficher dans la console "From a String object:" (rappel objet et instance sont des synonymes)
9. Itérer sur le tableau de caractères de la même manière que dans l'étape A en imprimant chacun des éléments du tableau dans la console
10. Appeler la nouvelle méthode depuis la méthode main (sans enlever l'appel à l'autre méthode pour comparer)
10. Résultat attendu :

From an array of chars:

N

a

t

h

a

l

i

e

From a String object:

N

a

t

h

a

l

i

e

#################################################################################################

Étape C - Longueur (taille) d'un tableau ou d'une chaîne (String)

1. Pour y voir plus clair dans la console, on peut commenter les 2 appels à printFirstnameArray() et printFirstnameString() dans la méthode main
2. Ecrire une nouvelle méthode privée et statique qui ne retourne rien (void), sans paramètre du nom de printArrayAndStringLength
3. Déclarer une variable de type String initialisée avec "Nathalie"
4. Déclarer une variable de type tableau de char et l'initialiser directement avec les caractères qui composent la chaîne Nathalie 
   (new char[] { 'N', 'a', 't', 'h', 'a', 'l', 'i', 'e' };) Avec ce mode d'initialisation (inline initialization) il n'est pas nécessaire de préciser 
   la longueur car Java peut la déduire des différents caractères qu'on spécifie à l'initialisation et même ça n'est pas permis car cela pourrait 
   être contradictoire en précisant une longueur différentes (par exemple new char[10] {'F','r','a','n','k'}).
   C'est pourquoi on peut également initialiser un tableau directement sans le mot clé new (exemple char[] frank = {'F','r','a','n','k'})
5. La classe String expose (fourni) une méthode length() pour retourner la longueur de la chaîne alors que les tableaux exposent un champs length 
   et non une méthode. Par exemples : str.length() vs arr.length où str et arr sont des variables String vs tableau
6. Terminer d'implémenter cette méthode puis l'appeler depuis le main pour obtenir le résultat suivant dans la console :

- firstname length: 8
- firstnameArray length: 8

#################################################################################################

Étape D - Parcourir un tableau pour trouver la dernière position d'un élément

1. Nouvelle méthode : printLastCharIndex()
2. Déclarer un tableau { 'N', 'a', 't', 'h', 'a', 'l', 'i', 'e' }
3. Itérer dessus pour retrouver la position (index) du dernier 'a'
4. On peut décrémenter (--) dans une boucle au même titre qu'on a l'habitude d'incrémenter (++) donc faire attention aux valeurs et conditions
   de la boucle (initialisation, terminaison, decrementation)...
5. Typiquement on déclare une variable avant la boucle (par exemple index) dont on change la valeur (réassigner) dans une condition (if) avec un break; 
   pour sortir de la boucle, si on a trouvé le "premier" 'a' en parcourant à l'envers, on a donc trouvé le dernier et il devient 
   inutile de poursuivre l'itération
6. On print dans la console la valeur de la variable index
7. Résultat attendue :

- char a last index: 4

Étape D (précisions)

- On déclare un tableau de char avec le prénom Nathalie (soit 8 caractères dans le tableau)
- On déclare une variable position de type int (c'est la variable qui va représenter l'index où se trouve le char à trouver dans le tableau)
- On déclare une boucle avec comme valeur pour i intialisée à la "longueur du tableau -1", une condition de terminaison "tant que i est supérieur à 0", on décrémente (cela indique qu'on parcours le tableau à l'envers)
- Dans la boucle, on déclare une variable de type char qui va stocker la valeur de chaque élément du tableau récupérer grâce à l'index i
- On teste si le caractère est == 'a', si oui on assigne la valeur de l'index i à position puis on break
- Après la boucle on imprime le résultat dans la console

#################################################################################################

Étape E - Renforcement des acquis sur les étapes précédentes

1. Nouvelle méthode : initAndPrintPrimitiveArray()
2. Déclarer un tableau de type int, de longueur 10 sans préciser les valeurs (pas de {...}), autrement dit avec des valeurs par défaut dans le tableau
3. Itérer du début à la fin sur le tableau pour que la valeur de chaque bucket (emplacement, case) soit égale à i + 10
4. Ecrire une 2ème boucle dans la même méthode mais en décrémentant pour afficher la valeur de chaque bucket dans la console

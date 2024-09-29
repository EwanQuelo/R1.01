 # R1.01 : TP3

**Nom :** QUÉLO

**Prénom :** Ewan

**Groupe :** C2

## Exercice 1 
### Version "while"
_Code :_
```java
/**
 * Décalle les éléments d'un tableau vers la droite et le dernier éléments
 * devient le premier
 * @author Ewan QUÉLO
 */

class Exo1 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 4, 1, 35, 25, 8, 3 };

        // AVANT
        System.out.print("Avant décallage\t : ");
        displayTab(t);

        // DECALLAGE :
        int derniereVal = t[t.length - 1];
        int i = t.length - 1;

        while (i > 0) {
            t[i] = t[i - 1];
            i--;
        }
        t[0] = derniereVal;

        // APRES
        System.out.print("Apres décallage\t : ");
        displayTab(t);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
Avant décallage	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Apres décallage	 : {3,5,7,0,6,10,8,4,1,35,25,8}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Avant décallage	 : {5,6,9,10,28,0,0,4}
Apres décallage	 : {4,5,6,9,10,28,0,0}


------------------
(program exited with code: 0)
```
### Version "for"
_Code :_
```java
/**
 * Décalle les éléments d'un tableau vers la droite et le dernier éléments
 * devient le premier
 * @author Ewan QUÉLO
 */

class Exo1 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 4, 1, 35, 25, 8, 3 };

        // AVANT
        System.out.print("Avant\t : ");
        displayTab(t);

        // DECALLAGE :
        int derniereVal = t[t.length - 1];

        for (int i = (t.length - 1); i > 0; i--) {
            t[i] = t[i - 1];
        }
        t[0] = derniereVal;

        // APRES
        System.out.print("Apres\t : ");
        displayTab(t);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
Avant	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Apres	 : {3,5,7,0,6,10,8,4,1,35,25,8}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Avant	 : {5,6,9,10,28,0,0,4}
Apres	 : {4,5,6,9,10,28,0,0}


------------------
(program exited with code: 0)
```

## Exercice 2 
### Version "while"
_Code :_
```java
/**
 * Créé un tableau cumulatif qui a chaque élément du tab t ajoute les précédents
 * @author Ewan QUÉLO
 */

class Exo2 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 4, 1, 35, 25, 8, 3 };

        // AVANT
        System.out.print("NORMAL\t : ");
        displayTab(t);

        // CODE :
        int[] cumul = new int[t.length];
        int i = 0;
        int total = 0;

        while (i < t.length) {
            total += t[i];
            cumul[i] = total;
            i++;
        }

        // APRES
        System.out.print("CUMUL\t : ");
        displayTab(cumul);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
NORMAL	 : {5,7,0,6,10,8,4,1,35,25,8,3}
CUMUL	 : {5,12,12,18,28,36,40,41,76,101,109,112}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
NORMAL	 : {1,2,3,4,5,6,7,8,9,10}
CUMUL	 : {1,3,6,10,15,21,28,36,45,55}


------------------
(program exited with code: 0)

```

### Version "for"
_Code :_
```java
/**
 * Créé un tableau cumulatif qui a chaque élément du tab t ajoute les précédents
 * @author Ewan QUÉLO
 */

class Exo2 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 4, 1, 35, 25, 8, 3 };

        // AVANT
        System.out.print("NORMAL\t : ");
        displayTab(t);

        // CODE :
        int[] cumul = new int[t.length];
        int total = 0;

        for (int i = 0; i < t.length; i++) {
            total += t[i];
            cumul[i] = total;
        }

        // APRES
        System.out.print("CUMUL\t : ");
        displayTab(cumul);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
NORMAL	 : {5,7,0,6,10,8,4,1,35,25,8,3}
CUMUL	 : {5,12,12,18,28,36,40,41,76,101,109,112}


------------------
(program exited with code: 0)
```

_Exemple d'exécution 2_
```
NORMAL	 : {1,2,3,4,5,6,7,8,9,10}
CUMUL	 : {1,3,6,10,15,21,28,36,45,55}


------------------
(program exited with code: 0)

```

## Exercice 3
_Boucle for ou boucle while :_
La boucle while est plus adapter lorsqu'il y a plusieurs conditions à vérifier

_Code avec boucle "while" :_
```java
/**
 * ROLE
 * @author Ewan QUÉLO
 */

class Exo3 {
    void principal() {
        // int[] t = { 4, 3, 2, 1 }; // 5
        int[] t = { 5, 7, 0, 6, 10, 8, 9, 10, 35}; // REP 4
        // int[] t = { 5, 7, 0, 6, 10, 8, 9, 10, 35, 0 }; // REP 4
        // int[] t = { 5 }; //1
        // int[] t = {1, 2, 3, 4, 0, 1, 2, 3, 4}; // REP 5
        // int[] t = {4, 0, 5, 6, 10, 3, 4}; 

        int actuelleSerie = 1;  
        int recordSerie = 1; 
        int i = 0; 
        boolean continuation = true;

 
        while (i < t.length - 1 && continuation ) {
            if (t[i + 1] > t[i]) {
                actuelleSerie++;
            } else {
                actuelleSerie = 1; 
                if ((t.length - i) <= recordSerie) {
					continuation = false;
				}
           
            }

            if (actuelleSerie > recordSerie) {
                recordSerie = actuelleSerie;
            }
            i++; 
           
		}
		displayTab(t);
		System.out.println("Plus grande série de nb: " + recordSerie);	
		System.out.println("Indice actuel d'arrêt: " + i);	
		// System.out.println(  i);	
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
{5,7,0,6,10,8,9,10,35}
Plus grande série de nb: 4
Indice actuel d'arrêt: 8


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
{4,3,2,1}
Plus grande série de nb: 1
Indice actuel d'arrêt: 3


------------------
(program exited with code: 0)
```
_Exemple d'exécution 3_
```
{5,7,0,6,10,8,9,10,35,0}
Plus grande série de nb: 4
Indice actuel d'arrêt: 9


------------------
(program exited with code: 0)
```

_Exemple d'exécution 5_
```
{5}
Plus grande série de nb: 1
Indice actuel d'arrêt: 0


------------------
(program exited with code: 0)
```
_Exemple d'exécution 6_
```
{4,0,5,6,10,3,4,2}
Plus grande série de nb: 4
Indice actuel d'arrêt: 5


------------------
(program exited with code: 0)
```
## Exercice 4
_Code :_
```java
/**
 * Recherche la plus grande série d'entiers strictement croissants dans un tableau donné
 * Et affiche l'indice de départ de la série et de fin
 * 
 * @author Ewan QUÉLO
 */

class Exo4 {
    void principal() {
        // int[] t = { 4, 3, 2, 1 }; // 5
        int[] t = { 5, 7, 0, 6, 10, 8, 9, 10, 35 }; // REP 4
        // int[] t = { 5, 7, 0, 6, 10, 8, 9, 10, 35, 0 }; // REP 4
        // int[] t = { 5 }; //1

        int actuelleSerie = 1;
        int recordSerie = 1;
        int i = 0;
        boolean continuation = true;

        int indiceDebut = 0;
        int indiceFin = 0;
        int indiceActuelle = 0;

        while (i < t.length - 1 && continuation) {
            if (t[i + 1] > t[i]) {
                actuelleSerie++;
            } else {
                actuelleSerie = 1;
                indiceActuelle = i + 1;

                if ((t.length - i) <= recordSerie) {
                    continuation = false;
                }
            }

            if (actuelleSerie > recordSerie) {
                recordSerie = actuelleSerie;
                indiceDebut = indiceActuelle;
                indiceFin = i + 1;
            }
            i++;

        }
        displayTab(t);
        System.out.println("Plus grande série de nb: " + recordSerie);
        System.out.println("La série commence à l'indice: " + indiceDebut + " et termine: " + indiceFin);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
{5,7,0,6,10,8,9,10,35}
Plus grande série de nb: 4
La série commence à l'indice: 5 et termine: 8


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
{4,3,2,1}
Plus grande série de nb: 1
La série commence à l'indice: 0 et termine: 0


------------------
(program exited with code: 0)
```
_Exemple d'exécution 3_
```
{5}
Plus grande série de nb: 1
La série commence à l'indice: 0 et termine: 0


------------------
(program exited with code: 0)
```
_Exemple d'exécution 4_
```
{5,7,0,6,10,8,9,10,35,0}
Plus grande série de nb: 4
La série commence à l'indice: 5 et termine: 8


------------------
(program exited with code: 0)
```

## Exercice 5
_Code :_
```java
/**
 * Affiche un tableau qui dit selon un tirage de 1000 fois le nb de fois ou sont
 * sortis les nb de 0 à 9
 * @author Ewan QUÉLO
 */

class Exo5 {
    void principal() {
        int[] t = new int[10];
        for (int i = 0; i < 1000; i++) {
            int nbRandom = (int) (Math.random() * 10);
            t[nbRandom]++;
        }
        displayTab(t);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
{88,88,94,102,106,103,104,107,102,106}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
{92,105,117,96,109,93,87,98,97,106}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 3_
```
{95,88,110,97,110,110,94,88,97,111}


------------------
(program exited with code: 0)
```

## Exercice 6

_Boucle for ou boucle while :_
La boucle while est plus adapter lorsqu'il y a plusieurs conditions à vérifier

_Code :_
```java
/**
 * Selon le nb strictement supérieur à 0 choisi par l'utilisateur on lui affiche le
 * nb de fois qu'il faut d'étapes pour arrive à 1
 * 
 * @author Ewan QUÉLO
 */

class Exo6 {
    void principal() {
        int nbChoisi = 0;

        do {
            nbChoisi = SimpleInput.getInt("Donnez un nombre strictement positif: ");
        } while (nbChoisi < 1);

        int nbEtape = 0;
        int nbMaxRencontre = 0;

        while (nbChoisi != 1) {
            if (nbChoisi % 2 == 0) {
                nbChoisi = nbChoisi / 2;
            } else {
                nbChoisi = (nbChoisi * 3) + 1;
            }

            if (nbChoisi > nbMaxRencontre) {
                nbMaxRencontre = nbChoisi;
            }

            nbEtape++;
        }

        System.out.println("Nb étapes pour arriver à 1 : " + nbEtape);
        System.out.println("Nb max rencontré : " + nbMaxRencontre);

    }
}
```

_Exemple d'exécution 1_
```
Donnez un nombre strictement positif: 7
Nb étapes pour arriver à 1 : 16
Nb max rencontré : 52


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Donnez un nombre strictement positif: 2
Nb étapes pour arriver à 1 : 1
Nb max rencontré : 1


------------------
(program exited with code: 0)

```
_Exemple d'exécution 3_
```
Donnez un nombre strictement positif: 27
Nb étapes pour arriver à 1 : 111
Nb max rencontré : 9232


------------------
(program exited with code: 0)
```

## Exercice 7
_Code :_
```java
/**
 * On regarde si les nb donnés dans un ordre par l'utilisateur sont dans le tableau dans le même ordre
 * 
 * @author Ewan QUÉLO
 */

class Exo7 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 9, 10, 35, 0 };

        System.out.println("Donnez 2 nombres et je vérifie s'ils sont dans l'ordre dans le tableau t");
        int nbA = SimpleInput.getInt("Votre nombre a: ");
        int nbB = SimpleInput.getInt("Votre nombre b: ");

        boolean aAtteint = false;
        boolean bAtteint = false;

        int i = 0;
        while (i < t.length) {
            if (!aAtteint && t[i] == nbA) {
                aAtteint = true;
            } else if (aAtteint && t[i] == nbB) {
                bAtteint = true;
            }
            i++;
        }
        if (aAtteint && bAtteint) {
            System.out.println(nbA + " et " + nbB + " sont présents dans cet ordre dans le tableau t suivant:");
        } else {
            System.out.println(nbA + " et " + nbB + " ne sont pas dans l'ordre dans le tableau t suivant:");
        }
        displayTab(t);
    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
Donnez 2 nombres et je vérifie s'ils sont dans l'ordre dans le tableau t
Votre nombre a: 5
Votre nombre b: 35
5 et 35 sont présents dans cet ordre dans le tableau t suivant
{5,7,0,6,10,8,9,10,35,0}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Donnez 2 nombres et je vérifie s'ils sont dans l'ordre dans le tableau t
Votre nombre a: 0
Votre nombre b: 7
0 et 7 ne sont pas dans l'ordre dans le tableau t suivant:
{5,7,0,6,10,8,9,10,35,0}


------------------
(program exited with code: 0)

```
_Exemple d'exécution 3_
```
Donnez 2 nombres et je vérifie s'ils sont dans l'ordre dans le tableau t
Votre nombre a: 8
Votre nombre b: 9
8 et 9 sont présents dans cet ordre dans le tableau t suivant:
{5,7,0,6,10,8,9,10,35,0}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 4_
```
Donnez 2 nombres et je vérifie s'ils sont dans l'ordre dans le tableau t
Votre nombre a: 24
Votre nombre b: 19
24 et 19 ne sont pas dans l'ordre dans le tableau t suivant:
{5,7,0,6,10,8,9,10,35,0}


------------------
(program exited with code: 0)

```
## Exercice 8
_Code :_
```java
/**
 * On entrelace 2 tableaux en prenant en compte leurs longueur respectives
 * @author Ewan QUÉLO
 */

class Exo8 {
    void principal() {
        int[] t1 = { 1, 5, 3, 6, 7, 8 };
        // int[] t2 = {1, 2, 4};
        int[] t2 = { 1, 2, 4, 5, 6, 6 };
        int[] tMix = new int[t1.length + t2.length];

        // mélange
        int i1 = 0;
        int i2 = 0;
        int iMix = 0;

        while (i1 < t1.length && i2 < t2.length) {

            tMix[iMix++] = t1[i1++];

            tMix[iMix++] = t2[i2++];
        }

        while (i1 < t1.length) {
            tMix[iMix++] = t1[i1++];
        }

        while (i2 < t2.length) {
            tMix[iMix++] = t2[i2++];
        }

        // on affiche
        System.out.println("Tableau 1: ");
        displayTab(t1);
        System.out.println("Tableau 2: ");
        displayTab(t2);
        System.out.println("Le mix des 2 tableaux : ");
        displayTab(tMix);

    }

    void displayTab(int[] t) {
        int i = 0;
        System.out.print("{");
        while (i < t.length - 1) {
            System.out.print(t[i] + ",");
            i = i + 1;
        }
        System.out.println(t[i] + "}");
    }
}
```

_Exemple d'exécution 1_
```
Tableau 1: 
{1,5,3,6,7,8}
Tableau 2: 
{1,2,4,5,6,6}
Le mix des 2 tableaux : 
{1,1,5,2,3,4,6,5,7,6,8,6}


------------------
(program exited with code: 0)

```
_Exemple d'exécution 2_
```
Tableau 1: 
{1,5,3,6,7,8}
Tableau 2: 
{1,2,4}
Le mix des 2 tableaux : 
{1,1,5,2,3,4,6,7,8}


------------------
(program exited with code: 0)
```
_Exemple d'exécution 3_
```
Tableau 1: 
{1}
Tableau 2: 
{1}
Le mix des 2 tableaux : 
{1,1}


------------------
(program exited with code: 0)
```


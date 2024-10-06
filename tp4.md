# R1.01 : TP4  

**Nom :** QUÉLO

**Prénom :** Ewan

**Groupe :** C2

## Exercice 1 
_Code :_
```java
/**
 * ROLE
 * 
 * @author Ewan QUÉLO
 */

class Exo1 {
    void principal() {
        // System.out.println(combinaison(25,24));
        // System.out.println(factorielle(4));
        // testCasFactorielle(4, 24);

        System.out.println("Résultat: " + combinaison(8, 4));
        // System.out.println("Résultat: " + factorielle(4));
        // testCombinaison ();
        // testFactorielle();
    }

    /**
     * calcul de la factorielle du paramètre
     * 
     * @param n valeur de la factoriel à calculer, n>=0
     * @return factorielle de n
     */
    int factorielle(int n) {
        int resultat = 1;
        for (int i = 1; i <= n; i++) {
            resultat *= i;
        }

        return resultat;
    }

    /**
     * calcul de la combinaison k parmi n
     * 
     * @param n cardinalité de l’ensemble
     * @param k nombre d’éléments dans n avec 0<=k<=n
     * @return nombre de combinaisons de k parmi n
     */
    int combinaison(int n, int k) {
        return factorielle(n) / (factorielle(k) * factorielle(n - k));
    }

    // LES METHODES DE TESTS

    /**
     * Teste la méthode factorielle()
     */
    void testFactorielle() {
        System.out.println();
        System.out.println("*** testFactorielle()");
        testCasFactorielle(5, 120);
        testCasFactorielle(0, 1);
        testCasFactorielle(1, 1);
        testCasFactorielle(2, 2);
    }

    /**
     * teste un appel de factorielle
     * 
     * @param n      valeur de la factorielle à calculer
     * @param result resultat attendu
     **/
    void testCasFactorielle(int n, int result) {
        // Affichage
        System.out.print("factorielle (" + n + ") \t= " + result + "\t : ");
        // Appel
        int resExec = factorielle(n);
        // Verification
        if (resExec == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }

    /**
     * Test la méthode combinaison()
     */
    void testCombinaison() {
        System.out.println();
        System.out.println("*** testCombinaison()");
        testCasCombinaison(4, 2, 6);
        testCasCombinaison(10, 10, 1);
        testCasCombinaison(25, 24, -2); // erreur de java
        testCasCombinaison(9, 14, 2002);
        testCasCombinaison(0, 0, 1);

    }

    /**
     * Test un appel de la combinaison
     * 
     * @param n      valeur de la factorielle à calculer
     * @param k
     * @param result resultat attendu
     */
    void testCasCombinaison(int n, int k, int result) {
        // Affichage
        System.out.print("Combinaison (" + n + ") et de(" + k + ") \t= " + result + "\t : ");
        // Appel
        int resExec = combinaison(n, k);
        // Verification
        if (resExec == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }

    }

}
```

_Execution factorielle(4)_
```
La factorielle de 4 est: 24


------------------
(program exited with code: 0)
```
_Execution factorielle(8)_
```
La factorielle de 8 est: 40320


------------------
(program exited with code: 0)
```
_Exécution combinaison(4 parmis 8)_
```
La combinaison de 4 parmi 8 donne : 70


------------------
(program exited with code: 0)
```
_Execution testFactorielle()_
```
*** testFactorielle()
factorielle (5) 	= 120	 : OK
factorielle (0) 	= 1	 : OK
factorielle (1) 	= 1	 : OK
factorielle (2) 	= 2	 : OK


------------------
(program exited with code: 0)
```

_Exécution testCombinaison()_
```
*** testCombinaison()
Combinaison (4) et de(2) 	= 6	 : OK
Combinaison (10) et de(10) 	= 1	 : OK
Combinaison (0) et de(0) 	= 1	 : OK


------------------
(program exited with code: 0)
```



## Exercice 2
_Code :_
```java
/**
 * ROLE
 * 
 * @author Ewan QUÉLO
 */

class Exo2 {
    void principal() {
        System.out.println("Est ce que divise: " + estDiviseur(10, 5));
        testEstDiviseur();
    }

    /**
     * teste la divisibilité de deux entiers
     * 
     * @param p entier positif à tester pour la divisibilité
     * @param q diviseur strictement positif
     * @return vrai ssi q divise p
     */
    boolean estDiviseur(int p, int q) {
        boolean verif = false;
        if (q != 0) {
            int res = p % q;
            if (res == 0) {
                verif = true;
            }
        }
        return verif;
    }

    void testEstDiviseur() {
        System.out.println();
        System.out.println("*** testEstdiviseur()");
        testCasEstDiviseur(10, 5, true);
        testCasEstDiviseur(12, 2, true);
        testCasEstDiviseur(26, 38, false);
        testCasEstDiviseur(0, 0, false);
    }

    void testCasEstDiviseur(int p, int q, boolean result) {
        // Affichage
        System.out.print(q + " divise " + p + " \t= " + result + "\t : ");

        // Verification
        if (estDiviseur(p, q) == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }
}
```

_Exemple d'exécution_
```
Est ce que divise: true

*** testEstdiviseur()
5 divise 10 	= true	 : OK
2 divise 12 	= true	 : OK
38 divise 26 	= false	 : OK
0 divise 0 	= false	 : OK


------------------
(program exited with code: 0)

```

## Exercice 3
_Code :_
```java
/**
 * ROLE
 * 
 * @author Ewan QUÉLO
 */

class Exo3 {
    void principal() {
        /*
         * System.out.println("Est ce que 6 est parfait: " + estParfait(6));
         * System.out.println("Est ce que 28 est parfait: " + estParfait(28));
         * System.out.println("Est ce que 496 est parfait: " + estParfait(496));
         * System.out.println("Est ce que 1 est parfait: " + estParfait(1));
         * System.out.println("Est ce que 4745 est parfait: " + estParfait(4745));
         */
        // System.out.println("Est ce que 6 est parfait: " + estParfait(6));
        // System.out.println("Est ce que 1 est parfait: " + estParfait(1));
        // testParfait();
        quatreNbParfaits();
    }

    /**
     * teste la divisibilité de deux entiers
     * 
     * @param p entier positif à tester pour la divisibilité
     * @param q diviseur strictement positif
     * @return vrai ssi q divise p
     */
    boolean estDiviseur(int p, int q) {
        boolean verif = false;
        if (q != 0) {
            int res = p % q;
            if (res == 0) {
                verif = true;
            }
        }
        return verif;
    }

    /**
     * teste si un nombre est parfait
     * 
     * @param a entier positif
     * @return vrai ssi a est un nombre parfait
     */
    boolean estParfait(int a) {
        int somme = 0;

        for (int i = 1; i < a; i++) {
            if (estDiviseur(a, i)) {
                somme += i;
            }
        }

        return somme == a;

    }

    void testParfait() {
        System.out.println();
        System.out.println("*** testEstParfait()");
        testCasEstParfait(6, true);
        testCasEstParfait(28, true);
        testCasEstParfait(496, true);
        testCasEstParfait(23, false);
        testCasEstParfait(1, false);
        testCasEstParfait(43, false);
    }

    void testCasEstParfait(int n, boolean result) {
        // Affichage
        System.out.print(n + " est un nombre parfait " + " \t= " + result + "\t : ");

        // Verification
        if (estParfait(n) == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }

    /**
     * Affiche les quatre premiers nombres parfaits
     */
    void quatreNbParfaits() {
        int i = 0;
        int nombre = 0;
        System.out.println("Voici les 4 premiers nombres parfaits: ");
        while (i < 4) {
            if (estParfait(nombre)) {
                System.out.println(nombre);
                i++;
            }
            nombre++;
            if (nombre % 10000 == 0) {
                System.out.println(nombre);
            }
        }
    }

}
```

_Execution méthode `estParfait()`_
```
Est ce que 6 est parfait: true
Est ce que 1 est parfait: false


------------------
(program exited with code: 0)
```
_Execution méthode `testEstParfait()`_
```
*** testEstParfait()
6 est un nombre parfait  	= true	 : OK
28 est un nombre parfait  	= true	 : OK
496 est un nombre parfait  	= true	 : OK
23 est un nombre parfait  	= false	 : OK
1 est un nombre parfait  	= false	 : OK
43 est un nombre parfait  	= false	 : OK


------------------
(program exited with code: 0)

```
_Execution méthode `quatreNbParfaits()`_
```
Voici les 4 premiers nombres parfaits: 
0
6
28
496


------------------
(program exited with code: 0)
```

## Exercice 4
_Code :_
```java
/**
 * ROLE
 * 
 * @author Ewan QUÉLO
 */

class Exo4 {
    void principal() {
        // int[] tab1 = {1, 2, 3, 4, 5};
        // int[] tab1 = {5, 3, 2, 1};
        // int[] tab1 = {2, 2, 2, 2};
        // int[] tab1 = {7};
        // int[] tab1 = {};
        // int[] tab1 = {1, 3, 2, 4};
        // System.out.println("Tab1 est t'il croissant: " + estCroissant(tab1));

        testEstCroissant();
    }

    /**
     * Vérifie si les valeurs d'un tableau sont triées en ordre croissant.
     * 
     * @param t tableau d'entiers
     * @return vrai si et seulement si les valeurs du tableau sont en ordre
     *         croissant
     */
    boolean estCroissant(int[] t) {
        boolean estTrie = true; // Initialiser la variable de retour à true
        for (int i = 0; i < t.length - 1; i++) {
            if (t[i] > t[i + 1]) {
                estTrie = false;
            }
        }
        return estTrie; // Un seul return ici
    }

    /**
     * Exécute plusieurs tests de estCroissant()
     */
    void testEstCroissant() {
        System.out.println();
        System.out.println("*** testEstCroissant()");
        int[] tab1 = { 1, 2, 3, 4, 5 };
        testCasEstCroissant(tab1, true);
        int[] tab2 = { 5, 3, 2, 1 };
        testCasEstCroissant(tab2, false);
        int[] tab3 = { 2, 2, 2, 2 };
        testCasEstCroissant(tab3, true);
        int[] tab4 = { 7 };
        testCasEstCroissant(tab4, true);
        int[] tab5 = {};
        testCasEstCroissant(tab5, true);
        int[] tab6 = { 1, 3, 2, 4 };
        testCasEstCroissant(tab6, false);

    }

    /**
     * Teste un cas et affiche le résultat du test.
     * 
     * @param tab    le tableau à tester
     * @param result le résultat attendu (true si trié, false sinon)
     */
    void testCasEstCroissant(int[] tab, boolean result) {
        // Affichage
        displayTab(tab);
        System.out.print(" Le tableau est t'il croissant " + " \t= " + result + "\t : ");

        // Verification
        if (estCroissant(tab) == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }

    /**
     * Affichage d'un tableau
     * 
     * @param t tableau d'entiers
     */
    void displayTab(int[] t) {
        System.out.print("{");
        if (t.length != 0) {
            for (int i = 0; i < t.length; i++) {
                System.out.print(t[i]);
                if (i < t.length - 1) {
                    System.out.print(", ");
                }
            }
        }
        System.out.print("}");
    }
}
```


_Execution méthode `testEstCroissant()`_
```
*** testEstCroissant()
{1, 2, 3, 4, 5} Le tableau est t'il croissant  	= true	 : OK
{5, 3, 2, 1} Le tableau est t'il croissant  	= false	 : OK
{2, 2, 2, 2} Le tableau est t'il croissant  	= true	 : OK
{7} Le tableau est t'il croissant  	= true	 : OK
{} Le tableau est t'il croissant  	= true	 : OK
{1, 3, 2, 4} Le tableau est t'il croissant  	= false	 : OK


------------------
(program exited with code: 0)
```

## Exercice 5
_Code :_
```java
/**
 * ROLE
 * 
 * @author Ewan QUÉLO
 */

class Exo5 {
    void principal() {
        // System.out.println("Nombre de fois ou le caractère 'e' apparait dans 'je
        // mange': " + nbOcc("je mange", 'e'));
        testNbOcc();
    }

    /**
     * Cherche combien de fois un caractère est présent dans une chaîne de
     * caractères
     * 
     * @param chaine Chaine de caractères
     * @param car    Caractère à rechercher
     * @return Nombre d'occurrences de car dans la chaine
     */
    int nbOcc(String chaineCara, char car) {
        int compteur = 0;
        for (int i = 0; i < chaineCara.length(); i++) {
            if (chaineCara.charAt(i) == car) {
                compteur++;
            }
        }
        return compteur;
    }

    /**
     * Exécute les tests de nbOcc()
     */
    void testNbOcc() {
        System.out.println();
        System.out.println("*** testNbOcc()");
        testCasNbOcc("", 'a', 0);
        testCasNbOcc("avion", 'a', 1);
        testCasNbOcc("avion", 'z', 0);
        testCasNbOcc("aaaa", 'a', 4);
        testCasNbOcc("apparaît", 'a', 3);
        testCasNbOcc("1299202//..?/", 'h', 0);
    }

    /**
     * Teste un cas particulier et affiche le résultat du test.
     * 
     * @param chaine la chaîne à tester
     * @param car    le caractère à rechercher
     * @param result le résultat attendu (nombre d'occurrences)
     */
    void testCasNbOcc(String chaine, char car, int result) {
        System.out.print(
                "Dans la chaîne \"" + chaine + "\", le caractère '" + car + "' apparaît \t= " + result + "\t : ");

        if (nbOcc(chaine, car) == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }
}
```


_Execution méthode `testCasNbOcc()`_
```
*** testNbOcc()
Dans la chaîne "", le caractère 'a' apparaît 	= 0	 : OK
Dans la chaîne "avion", le caractère 'a' apparaît 	= 1	 : OK
Dans la chaîne "avion", le caractère 'z' apparaît 	= 0	 : OK
Dans la chaîne "aaaa", le caractère 'a' apparaît 	= 4	 : OK
Dans la chaîne "apparaît", le caractère 'a' apparaît 	= 3	 : OK
Dans la chaîne "1299202//..?/", le caractère 'h' apparaît 	= 0	 : OK


------------------
(program exited with code: 0)
```


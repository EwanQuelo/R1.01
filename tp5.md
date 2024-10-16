 # R1.01 : TP5

**Nom :** QUÉLO

**Prénom :** Ewan

**Groupe :** C2

## Exercice 1 
_Code :_
```java
/**
 * Permet de savoir si toutes les valeurs d'un tableau n'ont aucune valeur
 * commmune
 * 
 * @author Ewan QUÉLO
 */

class Exo1 {
    void principal() {
        // int[] t1 = { 1, 2, 3, 4, 5, 6 };
        // int[] t2 = { 25,45,65};
        // System.out.println("Ont des valeurs communes :" + sontTousDiff(t1, t2));
        // displayTab(t1);

        testSontTousDiff();
    }

    /**
     * vérifie si deux tableaux n’ont aucune valeur commune
     * 
     * @param tab1 premier tableau
     * @param tab2 deuxième tableau
     * @return vrai si les tableaux tab1 et tab2 n’ont aucune valeur commune, faux
     *         sinon
     */
    boolean sontTousDiff(int[] tab1, int[] tab2) {
        boolean response = true;
        for (int i = 0; i < tab1.length; i++) {
            for (int j = 0; j < tab2.length; j++) {
                if (tab1[i] == tab2[j]) {
                    response = false;
                }
            }
        }
        return response;
    }

    /**
     * Exécute plusieurs tests de sontTousDiff()
     */
    void testSontTousDiff() {
        System.out.println();
        System.out.println("*** sontTousDiff()");
        int[] t1 = { 1, 2, 3, 4, 5, 6 };
        int[] t2 = { 25, 45, 65 };
        testCasSontTousDiff(t1, t2, true);
        int[] t3 = {};
        int[] t4 = {};
        testCasSontTousDiff(t3, t4, true);
        int[] t5 = { 0 };
        int[] t6 = { 0 };
        testCasSontTousDiff(t5, t6, false);
        int[] t7 = { 8, 9, 10, 11, 12, 13 };
        int[] t8 = { 8, 9, 10, 11, 12 };
        testCasSontTousDiff(t7, t8, false);
        int[] t9 = { 1 };
        int[] t10 = { 1, 1, 1, 1, 1, 1 };
        testCasSontTousDiff(t9, t10, false);

    }

    /**
     * Teste un cas et affiche le résultat du test.
     * 
     * @param tab1   le tableau à tester
     * @param tab2
     * @param result le résultat attendu (OK si la le test est identique au
     *               résultat, erreur sinon)
     */
    void testCasSontTousDiff(int[] tab1, int[] tab2, boolean result) {
        // Affichage

        System.out.print("sontTousDiff(");
        displayTab(tab1);
        displayTab(tab2);

        System.out.print(") \t= " + result + "\t : ");

        // Verification
        if (sontTousDiff(tab1, tab2) == result) {
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

_Exemple d'exécution_
```
*** sontTousDiff()
sontTousDiff({1, 2, 3, 4, 5, 6}{25, 45, 65}) 	= true	 : OK
sontTousDiff({}{}) 	= true	 : OK
sontTousDiff({0}{0}) 	= false	 : OK
sontTousDiff({8, 9, 10, 11, 12, 13}{8, 9, 10, 11, 12}) 	= false	 : OK
sontTousDiff({1}{1, 1, 1, 1, 1, 1}) 	= false	 : OK


------------------
(program exited with code: 0)
```

## Exercice 2
_Code :_
```java
/**
 * permet plusieurs choses sur un tableau:
 * Décaler une valeur de 1 a gauche; de N vers la gauche
 * Chercher l'indice d'une valeur dans un tab; remettre la valeur souhaitée
 * jusqu'à l'indice 0
 * 
 * @author Ewan QUÉLO
 */

class Exo2 {
    void principal() {
        // decalerGauche
        int[] tab1 = { 3, 10, 6, 20, 7 };
        System.out.println("Decaler a gauche d'une 1 valeur: ");
        System.out.print("avant: ");
        displayTab(tab1);
        System.out.println();
        System.out.print("après: ");
        decalerGauche(tab1);
        displayTab(tab1);

        // decalerGaucheN
        int[] tab2 = { 3, 10, 6, 20, 7 };
        System.out.println();
        System.out.println("********************************");
        System.out.println("Decaler a gauche de valeur n = 3:");
        System.out.print("avant: ");
        displayTab(tab2);
        System.out.println();
        System.out.print("après: ");
        decalerGaucheN(tab2, 3);
        displayTab(tab2);
        System.out.println();

        // cherche l'indice de la première occurrence
        int[] tab3 = { 3, 10, 6, 20, 5, 92, 93, 75, 7 };
        System.out.println("********************************");
        displayTab(tab3);
        System.out.println();
        System.out.println("cherche l'indice de la première occurrence de 92:");
        System.out.print("A l'indice : " + indiceTab(tab3, 92));

        // decale pour ramener la valeur souhaiter en premier
        int[] tab4 = { 3, 10, 6, 20, 5, 92, 93, 75, 7 };
        System.out.println("********************************");
        System.out.print("avant: ");
        displayTab(tab4);
        System.out.println();
        System.out.print("après: ");
        decaleValeur(tab4, 92);
        displayTab(tab4);
        System.out.println();

    }

    /**
     * décale les entiers d’un tableau d’une position vers la gauche
     * L’élément en 0 se retrouve à la fin du tableau
     * 
     * @param tab tableau d’entiers
     */
    void decalerGauche(int[] tab) {
        // verif si pas de longueur 0
        if (tab.length != 0) {
            int stock = tab[0];
            for (int i = 0; i < tab.length - 1; i++) {
                tab[i] = tab[i + 1];
            }
            tab[tab.length - 1] = stock;
        }
    }

    /**
     * décale les entiers d’un tableau de n positions vers la gauche
     * 
     * @param tab tableau d’entiers
     * @param n   entier nombre de cases à décaler
     */
    void decalerGaucheN(int[] tab, int n) {
        for (int i = 0; i < n; i++) {
            decalerGauche(tab);
        }

    }

    /**
     * cherche l’indice de la premiere occurrence d’une valeur dans un tableau
     * 
     * @param tab tableau d’entiers
     * @param v   valeur à chercher
     * @return l’indice de la première valeur v dans tab si v est dans tab, -1 sinon
     */
    int indiceTab(int[] tab, int v) {
        int response = -1;
        for (int i = 0; i < tab.length && response == -1; i++) {
            if (tab[i] == v) {
                response = i;
            }
        }
        return response;
    }

    /**
     * décale les valeurs d’un tableau de manière à ramener la valeur cherchée
     * à l’indice 0
     * Si la valeur n’est pas présente, le tableau n’est pas modifié
     * 
     * @param tab tableau d’entiers
     * @param v   valeur à chercher
     */
    void decaleValeur(int[] tab, int v) {
        int nbRepeat = indiceTab(tab, v);
        decalerGaucheN(tab, nbRepeat);
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

_Exemple d'exécution_
```
Decaler a gauche d'une 1 valeur: 
avant: {3, 10, 6, 20, 7}
après: {10, 6, 20, 7, 3}
********************************
Decaler a gauche de valeur n = 3:
avant: {3, 10, 6, 20, 7}
après: {20, 7, 3, 10, 6}
********************************
{3, 10, 6, 20, 5, 92, 93, 75, 7}
cherche l'indice de la première occurrence de 92:
A l'indice : 5********************************
avant: {3, 10, 6, 20, 5, 92, 93, 75, 7}
après: {92, 93, 75, 7, 3, 10, 6, 20, 5}


------------------
(program exited with code: 0)
```

## Exercice 3
_Code :_
```java
/**
 * Permet de savoir combien il y a de différentes valeurs dans un tableau
 * 
 * @author Ewan QUÉLO
 */

class Exo3 {
    void principal() {
        // int[] compteDiffVal = {0, 0, 2, 3, 0, 2, 1, 3, 3, 0};
        // displayTab(compteDiffVal);

        // System.out.println("Nb différents: " + compteDiffVal(compteDiffVal));
        testCompteDiffVal();
    }

    /**
     * compte le nombre de valeurs différentes dans un tableau
     * 
     * @param tab tableau d’entiers
     * @return le nombre de valeurs différentes du tableau
     */
    int compteDiffVal(int[] tab) {
        int[] stockDiff = new int[tab.length];
        int compteurDiff = 0;

        for (int i = 0; i < tab.length; i++) {
            boolean trouve = false;
            for (int j = 0; j < compteurDiff; j++) {
                if (stockDiff[j] == tab[i]) {
                    trouve = true;
                }
            }
            // si il n'est pas dans le stock
            if (!trouve) {
                stockDiff[compteurDiff++] = tab[i];
            }
        }

        return compteurDiff;
    }

    /**
     * Exécute plusieurs tests de compteDiffVal()
     */
    void testCompteDiffVal() {
        System.out.println();
        System.out.println("*** sontTousDiff()");
        int[] t1 = { 1, 2, 3, 4, 5, 6 };
        testCasCompteDiffVal(t1, 6);
        int[] t2 = {};
        testCasCompteDiffVal(t2, 0);
        int[] t3 = { 0 };
        testCasCompteDiffVal(t3, 1);
        int[] t4 = { 8, 8, 8, 8, 4, 8, 8, 8 };
        testCasCompteDiffVal(t4, 2);
        int[] t5 = { 1 };
        testCasCompteDiffVal(t5, 1);

    }

    /**
     * Teste un cas et affiche le résultat du test.
     * 
     * @param tab1   le tableau à tester
     * @param tab2
     * @param result le résultat attendu (OK si la le test est identique au
     *               résultat, erreur sinon)
     */
    void testCasCompteDiffVal(int[] tab1, int result) {
        // Affichage

        System.out.print("testCasCompteDiffVal(");
        displayTab(tab1);

        System.out.print(") \t= " + result + "\t : ");

        // Verification
        if (compteDiffVal(tab1) == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }
}
```

_Exemple d'exécution_
```
*** sontTousDiff()
testCasCompteDiffVal({1, 2, 3, 4, 5, 6}) 	= 6	 : OK
testCasCompteDiffVal({}) 	= 0	 : OK
testCasCompteDiffVal({0}) 	= 1	 : OK
testCasCompteDiffVal({8, 8, 8, 8, 4, 8, 8, 8}) 	= 2	 : OK
testCasCompteDiffVal({1}) 	= 1	 : OK


------------------
(program exited with code: 0)
```

## Exercice 4
_Code :_
```java
/**
 * pour tester si une chaîne est une sous-chaîne d'une autre.
 * 
 * @author Ewan QUÉLO
 */

class Exo4 {
    void principal() {
        // System.out.println("la chaîne 'ses' est t'elle contenu dans 'absesavion': " +
        // estSousChaine("ses","absesavion"));
        testEstSousChaine();
    }

    /**
     * teste si une chaîne est une sous-chaîne d’une autre
     * 
     * @param mot    chaîne de caractères
     * @param phrase chaîne de carectères
     * @return vrai ssi mot est présent dans phrase
     */
    boolean estSousChaine(String mot, String phrase) {
        boolean estTrouve = false;
        for (int i = 0; i <= phrase.length() - mot.length(); i++) {
            boolean correspondance = true;
            for (int j = 0; j < mot.length(); j++) {
                if (phrase.charAt(i + j) != mot.charAt(j)) {
                    correspondance = false;
                }
            }
            if (correspondance) {
                estTrouve = true;
            }
        }
        return estTrouve;
    }

    /**
     * Exécute plusieurs tests de estSousChaine()
     */
    void testEstSousChaine() {
        System.out.println();
        System.out.println("*** estSousChaine()");

        testCasEstSousChaine("ses", "absesavion", true);
        testCasEstSousChaine("test", "absesavion", false);
        testCasEstSousChaine("", "absesavion", true);
        testCasEstSousChaine("ses", "", false);
        testCasEstSousChaine("", "", true);
        testCasEstSousChaine("absesavion", "ses", false);
    }

    /**
     * Teste un cas et affiche le résultat du test.
     * 
     * @param mot    le mot à tester
     * @param phrase la phrase à tester
     * @param result le résultat attendu (OK si le test est identique au résultat,
     *               erreur sinon)
     */
    void testCasEstSousChaine(String mot, String phrase, boolean result) {
        // Affichage
        System.out.print("testCasEstSousChaine(\"" + mot + "\", \"" + phrase + "\") \t= " + result + "\t : ");

        if (estSousChaine(mot, phrase) == result) {
            System.out.println("OK");
        } else {
            System.err.println("ERREUR");
        }
    }
}
```

_Exemple d'exécution_
```
*** estSousChaine()
testCasEstSousChaine("ses", "absesavion") 	= true	 : OK
testCasEstSousChaine("test", "absesavion") 	= false	 : OK
testCasEstSousChaine("", "absesavion") 	= true	 : OK
testCasEstSousChaine("ses", "") 	= false	 : OK
testCasEstSousChaine("", "") 	= true	 : OK
testCasEstSousChaine("absesavion", "ses") 	= false	 : OK


------------------
(program exited with code: 0)
```

## Exercice 5
_Code :_
```java
/**
 * Trie les entiers donnés par l'user et les classe par ordre croissant
 * 
 * @author Ewan QUÉLO
 */

class Exo5 {
    final int LG_TAB = 4;

    void principal() {
        int[] tableauTrie = saisirEtTrier();
        displayTab(tableauTrie);
    }

    /**
     * Crée et saisit un tableau trié de LG_TAB entiers
     * 
     * @return tableau trié de LG-TAB entiers
     */
    int[] saisirEtTrier() {
        int[] t = new int[LG_TAB];
        int i = 0;

        while (i < t.length) {
            t[i] = SimpleInput.getInt("Entrer un entier");

            int j = i;
            while (j > 0 && t[j - 1] > t[j]) {

                int tmp = t[j];
                t[j] = t[j - 1];
                t[j - 1] = tmp;
                j--;
            }
            i++;
        }

        return t;
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

_Exemple d'exécution 1_
```
Entrer un entier28
Entrer un entier0
Entrer un entier1
Entrer un entier1
{0, 1, 1, 28}

------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Entrer un entier5
Entrer un entier3
Entrer un entier29
Entrer un entier33330303
{3, 5, 29, 33330303}

------------------
(program exited with code: 0)

```


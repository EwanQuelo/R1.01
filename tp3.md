 # R1.01 : TP3

**Nom :** QUÉLO
**Prénom :** Ewan
**Groupe :** C2

## Exercice 1 
### Version "while"
_Code :_
```java
/**
 * ROLE
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
        int i = t.length - 1;

        while (i > 0) {
            t[i] = t[i - 1];
            i--;
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
### Version "for"
_Code :_
```java
/**
 * ROLE
 * 
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
 * ROLE
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
		
		while(i< t.length) {
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

_Exemple d'exécution_
```
NORMAL	 : {5,7,0,6,10,8,4,1,35,25,8,3}
CUMUL	 : {5,12,12,18,28,36,40,41,76,101,109,112}


------------------
(program exited with code: 0)
```

### Version "for"
_Code :_
```java
/**
 * ROLE
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
		
		for(int i = 0; i < t.length; i++) {
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

_Exemple d'exécution_
```
NORMAL	 : {5,7,0,6,10,8,4,1,35,25,8,3}
CUMUL	 : {5,12,12,18,28,36,40,41,76,101,109,112}


------------------
(program exited with code: 0)
```

## Exercice 3
_Boucle for ou boucle while :_
La boucle while est plus adapter lorsqu'il y a plusieurs conditions à vérifier

_Code avec boucle "while" :_
```java

```

_Exemple d'exécution 1_
```

```
_Exemple d'exécution 2_
```

```
_Exemple d'exécution 3_
```

```

## Exercice 4
_Code avec boucle "for" :_
```java

```

_Exemple d'exécution_
```

```

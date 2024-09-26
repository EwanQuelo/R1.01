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

_Exemple d'exécution_
```
Avant	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Apres	 : {3,5,7,0,6,10,8,4,1,35,25,8}


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

_Exemple d'exécution_
```
Avant	 : {5,7,0,6,10,8,4,1,35,25,8,3}
Apres	 : {3,5,7,0,6,10,8,4,1,35,25,8}


------------------
(program exited with code: 0)
```

## Exercice 2
_Code :_
```java
METTRE LE CODE ICI
```

_Exemple d'exécution_
```
3

------------------
(program exited with code: 0)

Appuyez sur une touche pour continuer...
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
_Code avec boucle "for" :_
```java
/**
 * ROLE
 * @author Ewan QUÉLO
 */

class Exo3 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 4, 1, 35, 25, 8, 3 };

		int maxSerie = 0; 
		int recordSerie = 0;
		
        for(int i = 0; i < t.length - 1; i++ ) {
			
			if (t[i + 1] > t[i]) {
				maxSerie++;
			} else {
				maxSerie = 1;
			}
			
			if(maxSerie > recordSerie ) {
				recordSerie = maxSerie;
			}	
		}
		
		displayTab(t);
		System.out.println("record: " + recordSerie);	
		
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
{5,7,0,6,10,8,4,1,35,25,8,3}
record: 3


------------------
(program exited with code: 0)

```
### S'arrête quand ce n'est plus possible d'avancer:
_Code :_
```java
/**
 * ROLE
 * @author Ewan QUÉLO
 */

class Exo3 {
    void principal() {
        int[] t = { 5, 7, 0, 6, 10, 8, 4, 1, 35, 25, 8, 3 };

		int maxSerie = 0; 
		int recordSerie = 0;
		
        for(int i = 0; i < t.length - 1 && recordSerie < (t.length - i); i++ ) {
			
			if (t[i + 1] > t[i]) {
				maxSerie++;
			} else {
				maxSerie = 1;
			}
			
			if(maxSerie > recordSerie ) {
				recordSerie = maxSerie;
			}
		}
		
		displayTab(t);
		System.out.println("record: " + recordSerie);	
		
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
{5,7,0,6,10,8,4,1,35,25,8,3}
record: 3


------------------
(program exited with code: 0)

```

## Exercice 4
_Code avec boucle "for" :_
```java

```

_Exemple d'exécution_
```

```

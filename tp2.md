# R1.01 : TP2

**Nom :** QUÉLO
**Prénom :** Ewan
**Groupe :** C2

## Exercice 1 
### Partie 1:
_Code version "while" :_
```java
/**
 * Ce programme affiche les nombres que l'utilisateur saisi tant que ce n'est pas -1
 *  @author Ewan QUÉLO
 */

class Exo1 {
	void principal() {
		int nb = 1;
		while(nb != -1) {
			nb = SimpleInput.getInt("Votre nb: ");
			if (nb != -1) {
				System.out.println(nb);
			}
		}
	}
}

```
_Exemple d'exécution_
```
Votre nb: 1
1
Votre nb: 2
2
Votre nb: -1


------------------
(program exited with code: 0)

```

_Code version "do while" :_
```java
/**
 * Ce programme affiche les nombres que l'utilisateur saisi tant que ce n'est pas -1
 *  @author Ewan QUÉLO
 */

class Exo1 {
	void principal() {
		int nb;
		do {
			nb = SimpleInput.getInt("Votre nb: ");
			if (nb != -1) {
				System.out.println(nb);
			}
		} while (nb != -1);
	}
}

```

_Exemple d'exécution_
```
Votre nb: 10
10
Votre nb: 4
4
Votre nb: 3
3
Votre nb: -1


------------------
(program exited with code: 0)

```

### Partie 2:
_Code version "while" modifié avec la moyenne :_
```java
/**
 * Ce programme affiche les nombres que l'utilisateur saisi tant que ce n'est pas -1, ainsi que la moyenne
 * des nb saisis si elle n'est pas divisé par 0 et sans prendre en compte -1
 *  @author Ewan QUÉLO
 */

class Exo1 {
	void principal() {
		int nb = 0;
		int compteur = 0 ;
		int total = 0;
		do {
			nb = SimpleInput.getInt("Votre nb: ");
			if (nb != -1) {
				System.out.println(nb);
				total += nb;
				compteur ++;
			}
		} while (nb != -1);
		
		if (compteur != 0) {
			System.out.println("Voici la moyenne des nombres saisis: " + (total / compteur));
		}
	}
}
```
_Exemple d'exécution 1_
```
Votre nb: 3
3
Votre nb: 3
3
Votre nb: 3
3
Votre nb: -1
Voici la moyenne des nombres saisis: 3


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Votre nb: -1


------------------
(program exited with code: 0)
```

## Exercice 2
### Partie 1:

_Rôle du programme :_
Calcule le pgcd des 2 valeurs saisis par l'utilisateur. 

_Exemple d'exécution qui se terminent 1_
```
Première valeur : 10
Deuxième valeur : 5
Le résultat est : 5


------------------
(program exited with code: 0)
```
_Exemple d'exécution qui se terminent 2_
```
Première valeur : 20
Deuxième valeur : 5
Le résultat est : 5


------------------
(program exited with code: 0)

```
_Exemple d'exécution qui ne se terminent pas 1_
```
Première valeur : 0
Deuxième valeur : 3


```
_Exemple d'exécution qui ne se terminent pas 2_
```
Première valeur : -5
Deuxième valeur : 10

```

### Partie 2:
_Code version "while" :_
```java
/**
 * Trouver le pgcd des 2 valeurs saisis par l'utilisateur
 *  @author Ewan QUÉLO
 */


class Exo2 {
	
	void principal() {
		int val1 = 0;
		int val2 = 0;
		
		while (val1 <= 0) {
			val1 = SimpleInput.getInt ("Première valeur : ");
		}
		
		while (val2 <= 0) {
			val2 = SimpleInput.getInt ("Deuxième valeur : ");
		}
		
		
		while (val1 != val2) {
			if (val1 > val2) {
				val1 = val1 - val2;
			} else {
				val2 = val2 - val1;
			}
		}
        System.out.println("Le résultat est : " + val1);
     }
}

```
_Exemple d'exécution 1_
```
Première valeur : 1
Deuxième valeur : 3
Le résultat est : 1


------------------
(program exited with code: 0)

```
_Exemple d'exécution 2_
```
Première valeur : 0
Première valeur : 3
Deuxième valeur : 2
Le résultat est : 1


------------------
(program exited with code: 0)

```
_Code version "do while" :_
```java
/**
 * Trouver le pgcd des 2 valeurs saisis par l'utilisateur
 *  @author Ewan QUÉLO
 */


class Exo2 {
	
	void principal() {
		int val1;
		int val2;
		
		do {
			val1 = SimpleInput.getInt ("Première valeur : ");
		} while (val1 <= 0);
		
		do {
			val2 = SimpleInput.getInt ("Deuxième valeur : ");
		} while (val2 <= 0);
		
		
		while (val1 != val2) {
			if (val1 > val2) {
				val1 = val1 - val2;
			} else {
				val2 = val2 - val1;
			}
		}
        System.out.println("Le résultat est : " + val1);
     }
}

```
_Exemple d'exécution_
```
Première valeur : 0
Première valeur : 3
Deuxième valeur : 0
Deuxième valeur : -4
Deuxième valeur : 2
Le résultat est : 1


------------------
(program exited with code: 0)

```

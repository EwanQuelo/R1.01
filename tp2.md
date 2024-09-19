# R1.01 : TP2

**Nom :** QUÉLO
**Prénom :** Ewan
**Groupe :** C2

## Exercice 1 
### Partie 1:
_Code version "while" :_
```java
/**
 * Ce programme affiche les nombres que l'utilisateur saisi sauf quand c'est -1
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
 * Ce programme affiche les nombres que l'utilisateur saisi sauf quand c'est -1
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
 * Ce programme affiche les nombres que l'utilisateur saisi sauf quand c'est -1 ainsi que la moyenne
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
Voici ma réponse ...


_Exemple d'exécution qui se terminent_
```
Execution

```
_Exemple d'exécution qui ne se terminent pas_
```
Execution

```

### Partie 2:
_Code :_
```java
CODE

```
_Exemple d'exécution_
```
Execution

```
_Exemple d'exécution_
```
Execution

```

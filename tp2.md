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
		double total = 0;
		do {
			nb = SimpleInput.getInt("Votre nb: ");
			if (nb != -1) {
				System.out.println(nb);
				total += nb;
				compteur ++;
			}
		} while (nb != -1);
		double moyenne = total / compteur;
		if (compteur != 0) {
			System.out.println("Voici la moyenne des nombres saisis: " + moyenne);
		}
	}
}
```
_Exemple d'exécution 1_
```
Votre nb: 15
15
Votre nb: 10
10
Votre nb: -1
Voici la moyenne des nombres saisis: 12.5


------------------
(program exited with code: 0)

```
_Exemple d'exécution 2_
```
Votre nb: 20
20
Votre nb: 18
18
Votre nb: 16
16
Votre nb: 15
15
Votre nb: -1
Voici la moyenne des nombres saisis: 17.25


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
## Exercice 3
```java
/**
 * Tant que le nb saisi n'est pas inférieur au précédent l'utilisateur 
 * continue de saisir un nb 
 *  @author Ewan QUÉLO
 */


class Exo3 {
	
	void principal() {
		int val1 = SimpleInput.getInt("Saissisez votre valeur: ");
		int val2 = SimpleInput.getInt("Saissisez votre valeur: ");
		
		while (val2 >= val1) {
			val1 = val2;
			val2 = SimpleInput.getInt("Saissisez votre valeur: ");
			
		}
		
		
		System.out.println("Le nombre saisi est inférieur au précédent");
     	}
}


```

_Exemple d'exécution 1_
```
Saissisez votre valeur: 20
Saissisez votre valeur: 22
Saissisez votre valeur: 18
Le nombre saisi est inférieur au précédent


------------------
(program exited with code: 0)

```

_Exemple d'exécution 2_
```
Saissisez votre valeur: 20
Saissisez votre valeur: 10
Le nombre saisi est inférieur au précédent


------------------
(program exited with code: 0)

```

## Exercice 4
```java
/**
 * En fonction du prix et du montant donné dans la machine 
 * on calcule le nombres de chaque pièces et billets rendus
 *  @author Ewan QUÉLO
 */


class Exo4 {
	void principal() {
		int prix = SimpleInput.getInt("Quel est le prix du produit: ");
		int montantTotalInsere = 0;
        
        while (montantTotalInsere < prix) {
            int montantInsere = SimpleInput.getInt("Combien vous donnez: ");
            montantTotalInsere += montantInsere;
            
            if (montantTotalInsere < prix) {
                System.out.println("Voleur, il manque " + (prix - montantTotalInsere) + "€");
            }
		}
		
		if (montantTotalInsere == prix ) {
			System.out.println("Pas de rendue de monnaie");
		}
		
		if (montantTotalInsere > prix) {
			
			int diffPrix = montantTotalInsere - prix;
			
			if (diffPrix >= 50) {
            int billet50 = diffPrix / 50;
            diffPrix %= 50;
            System.out.println(billet50 + " billet(s) de 50€");
			}
			
			if (diffPrix >= 20) {
            int billet20 = diffPrix / 20;
            diffPrix %= 20;
            System.out.println(billet20 + " billet(s) de 20€");   
			}
			
			if (diffPrix >= 10) {
            int billet10 = diffPrix / 10;
            diffPrix %= 10;
            System.out.println(billet10 + " billet(s) de 10€");
			}
			
			if (diffPrix >= 5) {
            int billet5 = diffPrix / 5;
            diffPrix %= 5;
            System.out.println(billet5 + " billet(s) de 5€");
			}
			
			if (diffPrix >= 2) {
            int piece2 = diffPrix / 2;
            diffPrix %= 2;
            System.out.println(piece2 + " pièce(s) de 2€");
			}
			
			if (diffPrix >= 1) {
            int piece1 = diffPrix / 1;
            diffPrix %= 1;
            System.out.println(piece1 + " pièce(s) de 1€");
			}
		}
    }
}
```

_Exemple d'exécution 1_
```
Quel est le prix du produit: 15
Combien vous donnez: 320
6 billet(s) de 50€
1 billet(s) de 5€


------------------
(program exited with code: 0)
```

_Exemple d'exécution 2_
```
Quel est le prix du produit: 14
Combien vous donnez: 0
Voleur, il manque 14€
Combien vous donnez: 14
Pas de rendue de monnaie


------------------
(program exited with code: 0)
```
## Exercice 5
```java
/**
 * L'ordinateur choisi un nb aléatoire entre 1 et 100
 * et l'utilisateur doit le trouver
 *  @author Ewan QUÉLO
 */


class Exo5 {
	
	void principal() {
		int nbRandom = (int) (Math.random() * 100);
		int nbPick = 101;
		int essais = 0;
		
		do {
			essais++;
			nbPick = SimpleInput.getInt("Quel nb: ");
			
			if(nbPick > nbRandom){
				System.out.println("Trop grand !");
			} else if (nbPick < nbRandom) {
				System.out.println("Trop petit !");
			}
		} while (nbPick != nbRandom);
		System.out.println("Bravo ! Le nombre correct était bien " + nbRandom);
		System.out.println("Vous avez trouvé en " + essais + " essai(s)");	
     }
}
```

_Exemple d'exécution 1_
```
Quel nb: 40
Trop grand !
Quel nb: 30
Trop grand !
Quel nb: 20
Trop petit !
Quel nb: 25
Trop grand !
Quel nb: 23
Trop petit !
Quel nb: 24 
Bravo ! Le nombre correct était bien 24
Vous avez trouvé en 8 essai(s)


------------------
(program exited with code: 0)
```

_Exemple d'exécution 2_
```
Quel nb: 30
Trop petit !
Quel nb: 50
Trop grand !
Quel nb: 40
Trop grand !
Quel nb: 35
Trop grand !
Quel nb: 33
Trop petit !
Quel nb: 34
Bravo ! Le nombre correct était bien 34
Vous avez trouvé en 6 essai(s)


------------------
(program exited with code: 0)

```

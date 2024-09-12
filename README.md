é# STOCKAGE 
# R1.01 : TP1

**Nom :** QUÉLO
**Prénom :** Ewan
**Groupe :** C2

## Exercice 1 
_Code :_
```java
METTRE LE CODE ICI
```

_Réponse rédigée :_
Voici ma réponse ...

_Exemple d'exécution_
```
3

------------------
(program exited with code: 0)

Appuyez sur une touche pour continuer...
```
# test

# TP1 -->
 
# R1.01 : TP1

**Nom :** QUÉLO
**Prénom :** Ewan
**Groupe :** C2

## Exercice 2
_Code :_
```java
/*
* @author Ewan QUELO
* Compare 3 valeurs et trouve celui qui est le plus grand
*/

class Syntaxe{
	void principal(){
	int val1, Val2;
	int val3;
	val1 = SimpleInput.getInt("Premier entier :");
	Val2 = SimpleInput.getInt("Deuxième entier :");
	val3 = SimpleInput.getInt("Troisième entier :");
	
		if (val1<val3 && Val2<val3) {
			System.out.println("Le troisième entier " + val3 + " est le plus grand");
		} else if (val1<Val2 && val3<Val2) {
		System.out.println("Le deuxième entier " + Val2 + " est le plus grand");
		} else if (Val2<val1 && val3<val1) {
		System.out.println("Le premier entier " + val1 + " est le plus grand");
		}
	}
}

```
_Exemple d'exécution_
```
Premier entier :5
Deuxième entier :4
Troisième entier :3
Le premier entier 5 est le plus grand


------------------
(program exited with code: 0)

Appuyez sur une touche pour continuer...
```

## Exercice 3
_Code :_
```java
/*
* @author Ewan QUELO
* Permet le calcul de l'aire et du périmètre à partir du rayon fourni
*/

class Cercle{
	void principal(){
		double rayon; 
		double perimetre;
		double aire;
		
		rayon = SimpleInput.getDouble("Quel est le rayon de votre cercle en cm:");
		
		aire = rayon * rayon * Math.PI;
		
		System.out.println("L'aire de ce cercle est: " + aire + "scm");
		
		perimetre = Math.PI * 2 * rayon;
		System.out.println("\nSon périmètre est le suivant: " + perimetre + "cm");
		
	}
}



```
_Exemple d'exécution 1_
```
Quel est le rayon de votre cercle en cm:10
L'aire de ce cercle est: 314.1592653589793scm

Son périmètre est le suivant: 62.83185307179586cm


------------------
(program exited with code: 0)
```
_Exemple d'exécution 2_
```
Quel est le rayon de votre cercle en cm:30
L'aire de ce cercle est: 2827.4333882308138scm

Son périmètre est le suivant: 188.49555921538757cm


------------------
(program exited with code: 0)
```
_Exemple d'exécution 3_
```
Quel est le rayon de votre cercle en cm:3 
L'aire de ce cercle est: 28.274333882308138scm

Son périmètre est le suivant: 18.84955592153876cm


------------------
(program exited with code: 0)

```
## Exercice 4
_Code :_
```java
/**
* @author Ewan QUELO
* Le joueur rentre un nombre de quilles renversés avec chacune des 2 boules
*/

class Bowling{
	void principal(){
		int nbQui1;
		int nbQui2;
		int quilleActuelle = 10;
		
		nbQui1 = SimpleInput.getInt("Votre premier lancé :");
		
		if(nbQui1 > 10 || nbQui1 < 0) {
			System.out.println("Vous avez rentré(e) un nombre incorrect !");
		} else {
			quilleActuelle = quilleActuelle - nbQui1;
		
			if(quilleActuelle == 0){
				System.out.println("Strike !");
			} else {
				System.out.println("Il vous reste " + quilleActuelle + " quille(s) !" );
				nbQui2 = SimpleInput.getInt("Votre Deuxième lancé :");
			
				if(quilleActuelle == 0) {
					System.out.println("Spare !");
				} else if(nbQui2 > quilleActuelle) {
					System.out.println("Vous avez fait tomber plus de quilles qu'il n'y en a :) ");
				} else {
					System.out.println("Dommage vous y étiez presque !");
					System.out.println("Votre nombre total de quilles renversés est: " + (nbQui1 + nbQui2)+ "!");
				}
			} 
		}
	} 
}
```
_Exemple d'exécution 1_
```
Votre premier lancé :1
Il vous reste 9 quille(s) !
Votre Deuxième lancé :3
Dommage vous y étiez presque !
Votre nombre total de quilles renversés est: 4!


------------------
(program exited with code: 0)

```
_Exemple d'exécution 2_
```
Votre premier lancé :-2
Vous avez rentré(e) un nombre incorrect !


------------------
(program exited with code: 0)

```

_Exemple d'exécution 3_
```
Votre premier lancé :3
Il vous reste 7 quille(s) !
Votre Deuxième lancé :10
Vous avez fait tomber plus de quilles qu'il n'y en a :) 


------------------
(program exited with code: 0)
```
## Exercice 5
_Code :_
```java
/**
* @author Ewan QUELO
* L'utilisateur rentre un salaire brut, on calcul sa fiche de salaire et ses détails
*/

class Salaire{
	void principal(){
		
		double salaireUser = SimpleInput.getDouble("Rentrer votre salaire brut: ");
		
		double assuranceMaladie = salaireUser * 0.0075;
		double assuranceVieilleDepla = salaireUser * 0.001;
		double assuranceVieilllePla = salaireUser * 0.0675;
		double fraisPro = salaireUser * 0.0175;
		double contriSocialeGene = (salaireUser - fraisPro) * 0.075;
		double crds = (salaireUser - fraisPro) * 0.005;
		double chomage = salaireUser * 0.024;
		
		
		
		System.out.println("Voici votre fiche de paie");
		/* On affiche le salaire brut */ 
		System.out.println("Salaire brut:" + salaireUser);
		
		/* On affiche les prélèvements */ 
		System.out.println("Assurance maladie:" + assuranceMaladie);
		System.out.println("Assurance vieillesse déplafonnée:" + assuranceVieilleDepla);
		System.out.println("Assurance vieillesse plafonnée:" + assuranceVieilllePla);
		System.out.println("Frais professionnels:" + fraisPro);
		System.out.println("Contribution sociale généralisée:" + contriSocialeGene);
		System.out.println("CRDS:" + crds);
		System.out.println("Chômage:" + chomage);
		
		
		/* On affiche le salaire net  et total prélèvements */ 
		double prelevements = assuranceMaladie + assuranceVieilleDepla + assuranceVieilllePla + fraisPro + contriSocialeGene + crds + chomage;
		double salaireNet = salaireUser - prelevements;
		
		System.out.println("Prélèvement:" + prelevements);
		System.out.println("Salaire net:" + salaireNet);
	}		
}

```
_Exemple d'exécution_
```
Rentrer votre salaire brut: 2000
Voici votre fiche de paie
Salaire brut:2000.0
Assurance maladie:15.0
Assurance vieillesse déplafonnée:2.0
Assurance vieillesse plafonnée:135.0
Frais professionnels:35.0
Contribution sociale généralisée:147.375
CRDS:9.825000000000001
Chômage:48.0
Prélèvement:392.2
Salaire net:1607.8


------------------
(program exited with code: 0)

```
## Exercice 6
_Code :_
```java
/**
* @author Ewan QUELO
* D'après les notes fourni pour chaque compétences
* on calcul si il a son année et le nb de compétence
*/

class Note{
	void principal(){
		int competenceDessous8et10 = 0;
		int competenceValid = 0;
		boolean anneeFoiree = false;
		
		/* Questions  */
		double noteC1 = SimpleInput.getDouble("Quel est votre moyenne dans la compétence 1: ");
		double noteC2 = SimpleInput.getDouble("Quel est votre moyenne dans la compétence 2: ");
		double noteC3 = SimpleInput.getDouble("Quel est votre moyenne dans la compétence 3: ");
		double noteC4 = SimpleInput.getDouble("Quel est votre moyenne dans la compétence 4: ");
		double noteC5 = SimpleInput.getDouble("Quel est votre moyenne dans la compétence 5: ");
		double noteC6 = SimpleInput.getDouble("Quel est votre moyenne dans la compétence 6: ");
		
		/*calculs */
		if (noteC1 >= 10) {
			competenceValid++;
		} else if (noteC1 >= 8) {
			competenceDessous8et10++;
		} else {
			anneeFoiree = true;
		}
		
		if (noteC2 >= 10) {
			competenceValid++;
		} else if (noteC2 >= 8) {
			competenceDessous8et10++;
		} else {
			anneeFoiree = true;
		}
		
		if (noteC3 >= 10) {
			competenceValid++;
		} else if (noteC3 >= 8) {
			competenceDessous8et10++;
		} else {
			anneeFoiree = true;
		}
		
		if (noteC4 >= 10) {
			competenceValid++;
		} else if (noteC4 >= 8) {
			competenceDessous8et10++;
		} else {
			anneeFoiree = true;
		}
		
		if (noteC5 >= 10) {
			competenceValid++;
		} else if (noteC5 >= 8) {
			competenceDessous8et10++;
		} else {
			anneeFoiree = true;
		}
		
		if (noteC6 >= 10) {
			competenceValid++;
		} else if (noteC6 >= 8) {
			competenceDessous8et10++;
		} else {
			anneeFoiree = true;
		}
		
		/* résultat */
		if (!anneeFoiree && (competenceDessous8et10 <= 1) && (competenceValid >= 4) ) {
			System.out.println("Bravo vous avez validé votre année !");
			System.out.println("Vous avez " + competenceDessous8et10 + " compétence(s) entre 8 et 10.");
		} else {
			System.out.println("Vous avez foirée votre année !");
			
			if (competenceDessous8et10 > 0) {
				System.out.println("Vous avez " + competenceDessous8et10 + " compétences entre 8 et 10" );
				System.out.println("C'est trop !");
			} else if (competenceValid < 4 ) {
				System.out.println("Vous avez " + (6 - competenceValid) + " compétences en dessous de 10" );
				System.out.println("C'est trop !");
			} else if (anneeFoiree) {
				System.out.println("Vous avez " + competenceDessous8et10 + " compétences en dessous de 8" );
				System.out.println("C'est trop !");
			} 
		}
		
		System.out.println("--------Vos notes-----------");
		System.out.println("Compétence 1: " + noteC1 + " /Réaliser un développement d’application");
		System.out.println("Compétence 2: " + noteC2 + " /Optimiser des applications");
		System.out.println("Compétence 3: " + noteC3 + " /Administrer des systèmes informatiques communicants complexes");
		System.out.println("Compétence 4: " + noteC4 + " /Gérer des données de l’information");
		System.out.println("Compétence 5: " + noteC5 + " /Conduire un projet");
		System.out.println("Compétence 6: " + noteC6 + " /Collaborer au sein d’une équipe informatique");
		System.out.println("----------------------------");
		
	}
}


```
_Exemple d'exécution_ 1
```
Quel est votre moyenne dans la compétence 1: 10
Quel est votre moyenne dans la compétence 2: 10
Quel est votre moyenne dans la compétence 3: 10
Quel est votre moyenne dans la compétence 4: 10
Quel est votre moyenne dans la compétence 5: 8
Quel est votre moyenne dans la compétence 6: 10
Bravo vous avez validé votre année !
Vous avez 1 compétence(s) entre 8 et 10.
--------Vos notes-----------
Compétence 1: 10.0 /Réaliser un développement d’application
Compétence 2: 10.0 /Optimiser des applications
Compétence 3: 10.0 /Administrer des systèmes informatiques communicants complexes
Compétence 4: 10.0 /Gérer des données de l’information
Compétence 5: 8.0 /Conduire un projet
Compétence 6: 10.0 /Collaborer au sein d’une équipe informatique
----------------------------


------------------
(program exited with code: 0)

```

_Exemple d'exécution_ 2
```
Quel est votre moyenne dans la compétence 1: 15
Quel est votre moyenne dans la compétence 2: 12
Quel est votre moyenne dans la compétence 3: 13
Quel est votre moyenne dans la compétence 4: 8
Quel est votre moyenne dans la compétence 5: 8
Quel est votre moyenne dans la compétence 6: 10
Vous avez foirée votre année !
Vous avez 2 compétences entre 8 et 10
C'est trop !
--------Vos notes-----------
Compétence 1: 15.0 /Réaliser un développement d’application
Compétence 2: 12.0 /Optimiser des applications
Compétence 3: 13.0 /Administrer des systèmes informatiques communicants complexes
Compétence 4: 8.0 /Gérer des données de l’information
Compétence 5: 8.0 /Conduire un projet
Compétence 6: 10.0 /Collaborer au sein d’une équipe informatique
----------------------------


------------------
(program exited with code: 0)

```

_Exemple d'exécution_ 3
```
Quel est votre moyenne dans la compétence 1: 3
Quel est votre moyenne dans la compétence 2: 3
Quel est votre moyenne dans la compétence 3: 3
Quel est votre moyenne dans la compétence 4: 3
Quel est votre moyenne dans la compétence 5: 3
Quel est votre moyenne dans la compétence 6: 3
Vous avez foirée votre année !
Vous avez 6 compétences en dessous de 10
C'est trop !
--------Vos notes-----------
Compétence 1: 3.0 /Réaliser un développement d’application
Compétence 2: 3.0 /Optimiser des applications
Compétence 3: 3.0 /Administrer des systèmes informatiques communicants complexes
Compétence 4: 3.0 /Gérer des données de l’information
Compétence 5: 3.0 /Conduire un projet
Compétence 6: 3.0 /Collaborer au sein d’une équipe informatique
----------------------------


------------------
(program exited with code: 0)

```

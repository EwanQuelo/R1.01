# STOCKAGE 
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

/*
* @author Ewan QUELO
* Permet le calcul de l'aire et du périmètre à partir du rayon fourni
*/

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
/*
 * @author: Ewan QUELO
 * Le joueur rentre un nombre de quilles renversés avec chacune des 2 boules
 * */

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
## Exercice 5
_Code :_
```java
/**
* @author Ewan QUELO
* L'utilisateur rentre un salaire brut, on calcul sa fiche de salaire et ses détails
*/

class Salaire{
	void principal(){
		double salaireUser;
		
		salaireUser = SimpleInput.getDouble("Rentrer votre salaire brut: ");
		
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


```
_Exemple d'exécution_
```

```

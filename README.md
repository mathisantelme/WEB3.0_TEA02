# WEB3.0_TEA02 - Ontologie et Logiques de description

### ANTELME Mathis

## Exercice 1

> 1. Identifier la **T-Box** et la **A-Box**;

Ici, la **T-Box** correspond à la définition des propriétés et des classes. La **A-Box**, elle, correspond aux données (la suite de l'annexe).

> 2. Pourquoi l'existance d'un humain `unknown` est-elle nécessaire ?

Un humain `unknown` permet de définir le concept d'humain dans son ensemble (plus générique), on appelle cela la *subsomption*.

## Exercice 2

> 1. Montrez que la vache folle est un concept inconsistant;

```
VacheFolle ≡ Vache∃mange.Mouton
VacheFolle ≡ Vache∃mange.Mouton ⊑ Animal
VacheFolle ≡ Animal ⊓ Vegetarien ∃mange.Mouton ⊑ Animal
VacheFolle ≡ Animal ⊓ ∀mange.¬Animal ∃mange.Mouton ⊑ Animal
```

> 2. Montrer qu’il existe des animaux non végétariens;

```
VacheFolle ≡ Vache∃mange.Mouton
VacheFolle ≡ Vache∃mange.Mouton ⊑ Animal
```

## Exercice 3

> Donner les formules logiques d´ecrivant les concepts suivants:

- Un homme est un humain;
- Une femme est un humain;
- Un homme n'est pas une femme et vice-versa;
- Une équipe est définie par un set d'au minimum 2 membres humains;
- Une petite équipe est définie comme une équipe d'au maximum 5 membres;
- Une équipe moderne est définie comme une petite équipe comportant au moins un leader, qui correspond à un membre, et tout les leaders sont des femmes;

```
Man ⊑ Human
Woman ⊑ Human
∀ ¬Man = Woman, ∀ ¬Woman = Man
Team ≡ >2 ∀member ⊑ Human
SmallTeam ≡ Team ⊓ (≤ 5.Member)
Leader≡ Member
ModernTeam ≡ SmallTeam ∃Leader : ∀Leader ⊑ Woman
```
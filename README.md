
#  TP 1 : Programmation Dynamique et Réflexion en Java

## Réalisé par

**Abla MARGHOUB**

## Encadré par

**Pr. Mohamed LACHGAR**

## Module

**Techniques de Programmation Avancée**

## Établissement

**École Normale Supérieure - Université Cadi Ayyad**

---
##  Objectif du TP
L’objectif principal de ce TP est de comprendre et mettre en pratique la programmation dynamique et la réflexion en Java à travers la création d’une application simple et modulaire.  
Plus précisément, ce TP vise à :

-  Comprendre le concept de chargement dynamique des classes à l’exécution.  
-  Apprendre à injecter des dépendances via la réflexion, sans instanciation directe.  
-  Mettre en œuvre une architecture basée sur les interfaces pour découpler les différentes couches (DAO, Métier, Présentation).  
-  Manipuler un fichier de configuration externe pour définir les classes à utiliser.  
-  Comprendre comment ces techniques améliorent la flexibilité et la maintenabilité du code.

---
##  Structure du TP
<img width="315" height="546" alt="image" src="https://github.com/user-attachments/assets/8a37b581-f788-40d0-912d-6a38a01cc6b6" />


##  Description des interfaces et classes

| **Nom** | **Type** | **Package** | **Rôle / Description** |
|----------|-----------|--------------|--------------------------|
| `IDao` | Interface | `dao` | Définit une méthode `getValue()` qui retourne une valeur de type `double`. Elle représente la couche d’accès aux données. |
| `DaoImpl` | Classe | `dao` | Implémente l’interface `IDao`. Retourne une valeur fixe (100.0). Elle simule une source de données. |
| `IMetier` | Interface | `metier` | Déclare la méthode `calcul()` de type `double`. Représente la logique métier abstraite. |
| `MetierImpl` | Classe | `metier` | Implémente `IMetier` et contient une variable `IDao`. La méthode `calcul()` retourne le double de la valeur obtenue via `dao.getValue()`. |
| `Presentation2` | Classe | `presentation` | Point d’entrée de l’application. Utilise la réflexion pour charger les classes `DaoImpl` et `MetierImpl`, injecter la dépendance et exécuter la méthode `calcul()`. |
| `config.txt` | Fichier texte | Racine du projet | Contient les noms complets des classes à instancier : `dao.DaoImpl` et `metier.MetierImpl`. Permet de configurer l’application sans modifier le code source. |

---

##  Résultat d’exécution

<img width="772" height="298" alt="image" src="https://github.com/user-attachments/assets/62ec39fe-7f19-425b-b70f-3226e2376d48" />


---


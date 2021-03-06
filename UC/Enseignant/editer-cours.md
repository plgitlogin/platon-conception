# Cas d'utilisation N° 32 :  editer  assets /editer cours
Niveau 1

##	Description

La modification d'un **[cours](https://github.com/PremierLangage/platon-conception/blob/master/concept/cours.md)** se fait directement sur la page du cours en question. Modifier un cours consiste à ajouter/supprimer des sections, ajouter/supprimer des ressources dans les sections, modifier le titre des sections/ressources, modifier les **[métadonnées](https://github.com/PremierLangage/platon-conception/blob/master/concept/metadonnees.md)** des ressources.

> **Déclencheur** : Clique sur le bouton **éditer** présent sur la page du cours.
> **Acteur Primaire**: Enseignant   
> **Acteurs secondaires**: -   
> **Parties Prenantes concernées** : Les autres enseignants du cours   
 
 
## Préconditions
- L'utilisateur doit être enseignant du cours.

## Scenario Nominal

1. L'enseignant clique sur le bouton **éditer**
2. L'interface du cours se bascule en mode édition avec au **minimum** les fonctionnalités suivantes indépendamment de l'organisation d'IHM.
   - la possibilité d'ajouter une section (bouton qui ouvre une boite de dialogue permettant de saisir le titre de la section)
    - la possibilité de supprimer une section (**confirmation obligatoire**)
   -  la possibilité de changer l'ordre des sections/ressources (drap & drop **explicitement indiqué par la présence d'une icône par exemple**)
   - la possibilité d'accéder à une page/boîte de dialogue dédiée à la modification du contenu et des métadonnées de chaque ressource du cours (via un bouton à coté de la ressource par exemple).
   - la possibilité de supprimer une ressource (**confirmation obligatoire**)
   - la possibilité d'ajouter une ressource 
     - l'utilisateur selection une version d'activité avec l'interface de recherche des activité le système 
     - récupère l'identifiant de ressource version de l'activité. 
     - le système lance la compilation de la ressource (voire scénario, messages warning, vérification de la ressource est correct)
     - si la ressource est correcte on optien un json de l'activité contenant les exercices 
     - La ressource est "loaded" sur la sandbox dans le répertoire /cours_courrant/ACTIVITYID avec ACTIVITYID définie par la sandbox.
     - L'activité est ajouté au cours
     - l'utilisateur peut modifier les élements assets associés à l'activité.
3. L'enseignant clique sur un bouton permettant de  quitter le mode édition

### Scenario alternatifs 

La compilation échoue et donc l'activité n'est pas ajouter.



## Post Conditions
### Conditions de succès 
Une modification est considérée comme réussie uniquement si aucune notification n'indique pas le contraire.

### Minimal Guarantees
- Une notification doit indiquer la réussite ou l’échec de chaque modification.

### Conditions final en cas d'échec
- Une notification indique l'échec de la modification

### Frequence
Souvent

### Problèmes et étapes suivantes


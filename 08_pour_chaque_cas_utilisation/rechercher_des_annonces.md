AutoLoge - Cas d'utilisation : rechercher des annonces
==========

## Acteur principal  
Un Visiteur ou Utilisateur.

## Description
Un visiteur ou utilisateur peut effectuer une recherche pour afficher les annonces de logement en fonction des caractéristique de sa recherche.

## Pré-condition
Un Visiteur est sur la page de recherche.

## Post-condition
Le Système affiche une page contenant une liste de resultats d'annonces.

## Scenarios

### Scénario nominal

1. Le Visiteur ou Utilisateur saisit les critère de sa recherche
    - Il doit saisir un lieu qui peut correspondre à une ville (par nom ou code postal), un département (par nom ou numéro).
    - Il peut également définir une zone de recherche en kilomètre.
    - Il doit choisir le nombre de mètre carré minimum et maximum.
    - Il doit choisir le type de logement : appartement ou maison
    - Il peut choisir si le logement est prêt d'un transport en commun
    - Il peut choisir le taux de DPE qu'il souhaite au minium.
    - Il peut cocher s'il veut un ascenseur.
    - Il peut cocher s'il veut un parking.
1. Le Visiteur ou Utilisateur valide ses critères
1. Le Système effectue les recherche auprès des API des sites suivants :
    1. LeBonCoin
    1. PAP.fr
    1. SeLoger
1. Les APIs lui renvoie les résultats
1. Le Système traite les résultats
1. Le Système affiche les resutlats au Visiteur

### Scénarios alternatifs

Aucun.

### Scénarios exceptionnels

#### E1 - Aucun résultat
A partir de l'étape 4 :  
1. Les API renvoie une liste ne contenant aucun résultat
1. Le Système affiche un message informant qu'il n'y a pas d'annonces avec les critère défini précédament.

#### E2 - Erreur des API
A partir de l'étape 4 :  
1. Les API générent des erreurs.
1. Le Système affiche un message informant l'utilisateur qu'il n'a pu effectuer la recherche.


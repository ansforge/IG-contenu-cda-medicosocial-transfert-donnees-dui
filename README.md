![Logo_LEF_CI-SIS](https://user-images.githubusercontent.com/48218773/227532484-eff82649-4e42-49c6-966a-dc3ea78cf59c.png)

[![Workflow Init](https://github.com/ansforge/IG-contenu-cda-medicosocial-transfert-donnees-dui/actions/workflows/fhir-workflows.yml/badge.svg)](https://github.com/ansforge/IG-contenu-cda-medicosocial-transfert-donnees-dui/actions/workflows/fhir-workflows.yml)

# Contexte

## Contexte métier du projet

Le Programme ESMS numérique, porté par la Caisse Nationale de Solidarité pour l'Autonomie (CNSA), vise à généraliser l’utilisation du numérique dans les Établissements et Services Sociaux et Médico-Sociaux (ESSMS). Il repose principalement sur le déploiement d’un Dossier Usager Informatisé (DUI) pour chaque personne accompagnée. Ce DUI centralise l’ensemble des informations qui concerne la personne accompagnée en structure et service sociale et médico-sociale, et son parcours de santé et de vie. Ce dossier unique comprend :
*	Des données administratives ;
*	Des données liées à l’accompagnement de l’usager ;
*	Des données liées à la coordination des différents acteurs ;
*	Des données médicales.
  
Les logiciels DUI doivent permettre, entre autres, de mieux construire et de suivre le projet personnalisé de la personne accompagnée, d’éviter les ruptures de parcours en cas d’évolution des besoins, de changement d’établissement médico-social, de retour à domicile ou d’hospitalisation. 
Dans la continuité des travaux menés dans le cadre du programme ESMS numérique, la CNSA et l’ANS créent un nouveau volet « Transfert de données DUI ». L’objectif de ce volet est de définir le contenu CDA des données à transmettre lors d’un export de données portant sur l’activité des Services de soins infirmiers à domicile (SSIAD) destinés aux personnages âgées et aux personnes handicapées, à un SI tiers.


## Contexte technique du projet

Les données du DUI seront transportées dans un document CDA.
Le transport de ce document CDA s'effectuera par échange d'une ressource FHIR DocumentReference entre 2 acteurs.
Il n'existe pas à l'heure actuelle d'architecture qui permettrait de stocker ces données médico-sociales, et donc de s'orienter vers une gestion telle que celle décrite dans le volet PDSm. 

# CI/CD

Les workflows associés à ce repository (.github/workflows) permettent :

* D'executer Sushi pour vérifier la grammaire
* De faire les tests avec le validator_cli
* De publier les pages : https://ansforge.github.io/IG-contenu-cda-medicosocial-transfert-donnees-dui/{nom de la branche}/ig

# Notes

Ce repo a été créé à partir du repo [sample-ig](https://github.com/FHIR/sample-ig) de l'organisation GitHub FHIR.

## Acronymes

* IG : Implementation Guide
* FHIR : Fast Healthcare Interoperability Resources
* FIG : FHIR Implementation Guide
* FIG : FHIR Implementation Guide
* HL7 : Health Level Seven
* ANS : L’Agence du Numérique en Santé
* CI-SIS : Cadre d’Interopérabilité des Systèmes d’Information de Santé
* CNSA : Caisse Nationale de Solidarité pour l’Autonomie
* DUI : Dossier Usager Informatisé
* ESSMS : Etablissement et Services sociaux ou Médico-Sociaux
* SIDOBA : Système d’Information de l’Offre de la Branche Autonomie
* ANS : L’Agence du Numérique en Santé
* CI-SIS : Cadre d’Interopérabilité des Systèmes d’Information de Santé
* CNSA : Caisse Nationale de Solidarité pour l’Autonomie
* DUI : Dossier Usager Informatisé
* ESSMS : Etablissement et Services sociaux ou Médico-Sociaux
* SIDOBA : Système d’Information de l’Offre de la Branche Autonomie

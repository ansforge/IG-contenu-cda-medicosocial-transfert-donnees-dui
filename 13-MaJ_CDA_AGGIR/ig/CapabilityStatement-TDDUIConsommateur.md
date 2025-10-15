# TDDUI-Consommateur - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* [**Ressources FHIR**](artifacts.md)
* **TDDUI-Consommateur**

## CapabilityStatement: TDDUI-Consommateur 

| | |
| :--- | :--- |
| *Official URL*:https://interop.esante.gouv.fr/ig/cda/tddui/CapabilityStatement/TDDUIConsommateur | *Version*:1.0.0 |
| Active as of 2024-06-20 | *Computable Name*:TDDUIConsommateur |

 
Le rôle du consommateur est de recueillir les données du Dossier Usager Informatisé. Il peut recevoir un unique dossier ou un ensemble de dossiers, ainsi que des mises à jour de dossiers. Il correspond à un logiciel DUI ou un SI tiers. 

 [Raw OpenAPI-Swagger Definition file](TDDUIConsommateur.openapi.json) | [Download](TDDUIConsommateur.openapi.json) 

## TDDUI-Consommateur

* Version du guide dimplémentation : {0} 
* Version de FHIR : 4.0.1 
* Supported Formats: `application/fhir+xml`, `application/fhir+json`
* Publié sur : 2024-06-20 09:51:35+0200 
* Publié par : Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris 

> **Note aux implémenteurs : capacités FHIR**Any FHIR capability may be 'allowed' by the system unless explicitly marked as 'SHALL NOT'. A few items are marked as MAY in the Implementation Guide to highlight their potential relevance to the use case.

### DOIT prendre en charge les guides d’implémentation suivants.

* https://interop.esante.gouv.fr/ig/fhir/tddui

## FHIR RESTful Capabilities

### Mode: client

Réception de données exportées depuis un logiciel DUI (flux 1).

**Security**

> 

L’ANS propose des référentiels dédiés à la politique de sécurité (la PGSSI-S) et des mécanismes de sécurisation sont définis dans les volets de la couche Transport du Cadre d’Interopérabilité des systèmes d’information de santé (CI-SIS)


**Summary of System-wide Interactions**

* Supports the `transaction`Les interactions sont décrites comme suit :

https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-bundle


### Capabilities by Resource/Profile

#### Résumé

Le tableau récapitulatif liste les ressources faisant partie de cette configuration, et pour chaque ressource, il liste :

* The relevant profiles (if any)
* Les interactions supportées par chaque ressource (**R**ead, **S**earch, **U**pdate, and **C**reate, are always shown, while **VR**ead, **P**atch, **D**elete, **H**istory on **I**nstance, or **H**istory on **T**les types sont seulement présents si au moins une des ressources les prend en charge.
* Les paramètres de recherche (SearchParameters) requis, recommandés, optionnels (le cas échéant).
* The linked resources enabled for `_include`
* The other resources enabled for `_revinclude`
* The operations on the resource (if any)

| | | | | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [DocumentReference](#DocumentReference1-1) | https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference | y |  |  |  |  |  |  |  |

-------

#### Resource Conformance: supported DocumentReference

Base System Profile

`https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference`

Conformité au Profil

**SHALL**

Reference Policy

Résumé des interactions

* Supports `read`.



## Resource Content

```json
{
  "resourceType" : "CapabilityStatement",
  "id" : "TDDUIConsommateur",
  "url" : "https://interop.esante.gouv.fr/ig/cda/tddui/CapabilityStatement/TDDUIConsommateur",
  "version" : "1.0.0",
  "name" : "TDDUIConsommateur",
  "title" : "TDDUI-Consommateur",
  "status" : "active",
  "experimental" : false,
  "date" : "2024-06-20T09:51:35+02:00",
  "publisher" : "Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris",
  "contact" : [
    {
      "name" : "Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris",
      "telecom" : [
        {
          "system" : "url",
          "value" : "https://esante.gouv.fr"
        }
      ]
    }
  ],
  "description" : "Le rôle du consommateur est de recueillir les données du Dossier Usager Informatisé. Il peut recevoir un unique dossier ou un ensemble de dossiers, ainsi que des mises à jour de dossiers. Il correspond à un logiciel DUI ou un SI tiers.",
  "jurisdiction" : [
    {
      "coding" : [
        {
          "system" : "urn:iso:std:iso:3166",
          "code" : "FR",
          "display" : "FRANCE"
        }
      ]
    }
  ],
  "kind" : "requirements",
  "fhirVersion" : "4.0.1",
  "format" : ["application/fhir+xml", "application/fhir+json"],
  "implementationGuide" : ["https://interop.esante.gouv.fr/ig/fhir/tddui"],
  "rest" : [
    {
      "mode" : "client",
      "documentation" : "Réception de données exportées depuis un logiciel DUI (flux 1).",
      "security" : {
        "cors" : false,
        "description" : "L’ANS propose des référentiels dédiés à la politique de sécurité (la PGSSI-S) et des mécanismes de sécurisation sont définis dans les volets de la couche Transport du Cadre d’Interopérabilité des systèmes d’information de santé (CI-SIS)"
      },
      "resource" : [
        {
          "type" : "DocumentReference",
          "profile" : "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference",
          "interaction" : [
            {
              "code" : "read"
            }
          ]
        }
      ],
      "interaction" : [
        {
          "code" : "transaction",
          "documentation" : "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-bundle"
        }
      ]
    }
  ]
}

```

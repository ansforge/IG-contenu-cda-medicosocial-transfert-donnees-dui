# TDDUI-Producteur - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* [**Ressources FHIR**](artifacts.md)
* **TDDUI-Producteur**

## CapabilityStatement: TDDUI-Producteur 

| | |
| :--- | :--- |
| *Official URL*:https://interop.esante.gouv.fr/ig/cda/tddui/CapabilityStatement/TDDUIProducteur | *Version*:1.0.0 |
| Active as of 2024-06-20 | *Computable Name*:TDDUIProducteur |

 
Le rôle du producteur est de créer et transmettre un document ou lots de Documents portant les informations du Dossier Usager Informatisé. Il correspond à un logiciel DUI. 

 [Raw OpenAPI-Swagger Definition file](TDDUIProducteur.openapi.json) | [Download](TDDUIProducteur.openapi.json) 

## TDDUI-Producteur

* Version du guide dimplémentation : {0} 
* Version de FHIR : 4.0.1 
* Supported Formats: `application/fhir+xml`, `application/fhir+json`
* Publié sur : 2024-06-20 15:51:35+0200 
* Publié par : Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris 

> **Note aux implémenteurs : capacités FHIR**Any FHIR capability may be 'allowed' by the system unless explicitly marked as 'SHALL NOT'. A few items are marked as MAY in the Implementation Guide to highlight their potential relevance to the use case.

### DOIT prendre en charge les guides d’implémentation suivants.

* https://interop.esante.gouv.fr/ig/fhir/tddui

## FHIR RESTful Capabilities

### Mode: client

Export de données DUI vers un autre logiciel DUI ou SI tiers (flux 1).

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
| [DocumentReference](#DocumentReference1-1) | https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference |  |  |  | y |  |  |  |  |

-------

#### Resource Conformance: supported DocumentReference

Base System Profile

`https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference`

Conformité au Profil

**SHALL**

Reference Policy

Résumé des interactions

* Supports `create`.



## Resource Content

```json
{
  "resourceType" : "CapabilityStatement",
  "id" : "TDDUIProducteur",
  "url" : "https://interop.esante.gouv.fr/ig/cda/tddui/CapabilityStatement/TDDUIProducteur",
  "version" : "1.0.0",
  "name" : "TDDUIProducteur",
  "title" : "TDDUI-Producteur",
  "status" : "active",
  "experimental" : false,
  "date" : "2024-06-20T15:51:35+02:00",
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
  "description" : "Le rôle du producteur est de créer et transmettre un document ou lots de Documents portant les informations du Dossier Usager Informatisé. Il correspond à un logiciel DUI.",
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
      "documentation" : "Export de données DUI vers un autre logiciel DUI ou SI tiers (flux 1).",
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
              "code" : "create"
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

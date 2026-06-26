# TDDUI-Producteur - Médicosocial - Transfert de données DUI CDA v1.0.1

## CapabilityStatement: TDDUI-Producteur 

 
Le rôle du producteur est de créer et transmettre un document ou lots de Documents portant les informations du Dossier Usager Informatisé. Il correspond à un logiciel DUI. 

 [Raw OpenAPI-Swagger Definition file](../TDDUIProducteur.openapi.json) | [Download](../TDDUIProducteur.openapi.json) 



## Resource Content

```json
{
  "resourceType" : "CapabilityStatement",
  "id" : "TDDUIProducteur",
  "url" : "https://interop.esante.gouv.fr/ig/cda/tddui/CapabilityStatement/TDDUIProducteur",
  "version" : "1.0.1",
  "name" : "TDDUIProducteur",
  "title" : "TDDUI-Producteur",
  "status" : "active",
  "experimental" : false,
  "date" : "2024-06-20T15:51:35+02:00",
  "publisher" : "Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris",
  "contact" : [{
    "name" : "Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris",
    "telecom" : [{
      "system" : "url",
      "value" : "https://esante.gouv.fr"
    }]
  }],
  "description" : "Le rôle du producteur est de créer et transmettre un document ou lots de Documents portant les informations du Dossier Usager Informatisé. Il correspond à un logiciel DUI.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "FR",
      "display" : "FRANCE"
    }]
  }],
  "kind" : "requirements",
  "fhirVersion" : "4.0.1",
  "format" : ["application/fhir+xml", "application/fhir+json"],
  "implementationGuide" : ["https://interop.esante.gouv.fr/ig/fhir/tddui"],
  "rest" : [{
    "mode" : "client",
    "documentation" : "Export de données DUI vers un autre logiciel DUI ou SI tiers (flux 1).",
    "security" : {
      "cors" : false,
      "description" : "L’ANS propose des référentiels dédiés à la politique de sécurité (la PGSSI-S) et des mécanismes de sécurisation sont définis dans les volets de la couche Transport du Cadre d’Interopérabilité des systèmes d’information de santé (CI-SIS)"
    },
    "resource" : [{
      "type" : "DocumentReference",
      "profile" : "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference",
      "interaction" : [{
        "code" : "create"
      }]
    }],
    "interaction" : [{
      "code" : "transaction",
      "documentation" : "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-bundle"
    }]
  }]
}

```

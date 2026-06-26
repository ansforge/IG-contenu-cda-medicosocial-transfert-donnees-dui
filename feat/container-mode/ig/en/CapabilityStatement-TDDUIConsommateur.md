# TDDUI-Consommateur - Médicosocial - Transfert de données DUI CDA v1.0.1

## CapabilityStatement: TDDUI-Consommateur 

 
Le rôle du consommateur est de recueillir les données du Dossier Usager Informatisé. Il peut recevoir un unique dossier ou un ensemble de dossiers, ainsi que des mises à jour de dossiers. Il correspond à un logiciel DUI ou un SI tiers. 

 [Raw OpenAPI-Swagger Definition file](../TDDUIConsommateur.openapi.json) | [Download](../TDDUIConsommateur.openapi.json) 



## Resource Content

```json
{
  "resourceType" : "CapabilityStatement",
  "id" : "TDDUIConsommateur",
  "url" : "https://interop.esante.gouv.fr/ig/cda/tddui/CapabilityStatement/TDDUIConsommateur",
  "version" : "1.0.1",
  "name" : "TDDUIConsommateur",
  "title" : "TDDUI-Consommateur",
  "status" : "active",
  "experimental" : false,
  "date" : "2024-06-20T09:51:35+02:00",
  "publisher" : "Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris",
  "contact" : [{
    "name" : "Agence du Numérique en Santé (ANS) - 2-10 Rue d'Oradour-sur-Glane, 75015 Paris",
    "telecom" : [{
      "system" : "url",
      "value" : "https://esante.gouv.fr"
    }]
  }],
  "description" : "Le rôle du consommateur est de recueillir les données du Dossier Usager Informatisé. Il peut recevoir un unique dossier ou un ensemble de dossiers, ainsi que des mises à jour de dossiers. Il correspond à un logiciel DUI ou un SI tiers.",
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
    "documentation" : "Réception de données exportées depuis un logiciel DUI (flux 1).",
    "security" : {
      "cors" : false,
      "description" : "L’ANS propose des référentiels dédiés à la politique de sécurité (la PGSSI-S) et des mécanismes de sécurisation sont définis dans les volets de la couche Transport du Cadre d’Interopérabilité des systèmes d’information de santé (CI-SIS)"
    },
    "resource" : [{
      "type" : "DocumentReference",
      "profile" : "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference",
      "interaction" : [{
        "code" : "read"
      }]
    }],
    "interaction" : [{
      "code" : "transaction",
      "documentation" : "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-bundle"
    }]
  }]
}

```

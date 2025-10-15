# TDDUI Bundle - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* [**Ressources FHIR**](artifacts.md)
* **TDDUI Bundle**

## Resource Profile: TDDUI Bundle 

| | |
| :--- | :--- |
| *Official URL*:https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-bundle | *Version*:1.0.0 |
| Active as of 2025-10-15 | *Computable Name*:TDDUIBundle |

 
Profil générique créé dans le contexte du transfert de données DUI pour véhiculer un lot de documents au format CDA. 

**Usages:**

* Examples for this Profile: [Bundle/TDDUIBundleExample](Bundle-TDDUIBundleExample.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/ans.cda.fr.tddui|current/StructureDefinition/tddui-bundle)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-tddui-bundle.csv), [Excel](StructureDefinition-tddui-bundle.xlsx), [Schematron](StructureDefinition-tddui-bundle.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "tddui-bundle",
  "url" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-bundle",
  "version" : "1.0.0",
  "name" : "TDDUIBundle",
  "title" : "TDDUI Bundle",
  "status" : "active",
  "date" : "2025-10-15T07:51:55+00:00",
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
  "description" : "Profil générique créé dans le contexte du transfert de données DUI pour véhiculer un lot de documents au format CDA.",
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
  "fhirVersion" : "4.0.1",
  "mapping" : [
    {
      "identity" : "v2",
      "uri" : "http://hl7.org/v2",
      "name" : "HL7 v2 Mapping"
    },
    {
      "identity" : "rim",
      "uri" : "http://hl7.org/v3",
      "name" : "RIM Mapping"
    },
    {
      "identity" : "cda",
      "uri" : "http://hl7.org/v3/cda",
      "name" : "CDA (R2)"
    },
    {
      "identity" : "w5",
      "uri" : "http://hl7.org/fhir/fivews",
      "name" : "FiveWs Pattern Mapping"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Bundle",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Bundle",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "Bundle",
        "path" : "Bundle"
      },
      {
        "id" : "Bundle.type",
        "path" : "Bundle.type",
        "patternCode" : "transaction"
      },
      {
        "id" : "Bundle.entry",
        "path" : "Bundle.entry",
        "slicing" : {
          "discriminator" : [
            {
              "type" : "profile",
              "path" : "resource"
            }
          ],
          "description" : "Slicing based on the profile conformance of the entry",
          "rules" : "open"
        },
        "min" : 1
      },
      {
        "id" : "Bundle.entry:DUIDocumentReference",
        "path" : "Bundle.entry",
        "sliceName" : "DUIDocumentReference",
        "short" : "DocumentReference conforming to the TDDUIDocumentReference profile, used to convey a document in CDA format.",
        "min" : 1,
        "max" : "*"
      },
      {
        "id" : "Bundle.entry:DUIDocumentReference.resource",
        "path" : "Bundle.entry.resource",
        "min" : 1,
        "type" : [
          {
            "code" : "DocumentReference",
            "profile" : [
              "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
            ]
          }
        ]
      },
      {
        "id" : "Bundle.entry:DUIDocumentReference.request",
        "path" : "Bundle.entry.request",
        "min" : 1
      },
      {
        "id" : "Bundle.entry:DUIDocumentReference.request.method",
        "path" : "Bundle.entry.request.method",
        "patternCode" : "POST"
      }
    ]
  }
}

```

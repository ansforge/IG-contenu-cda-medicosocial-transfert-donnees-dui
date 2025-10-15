# TDDUIDocumentReferenceExample - Médicosocial - Transfert de données DUI CDA v1.0.1

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* [**Ressources FHIR**](artifacts.md)
* **TDDUIDocumentReferenceExample**

## Example DocumentReference: TDDUIDocumentReferenceExample

version: 1; Dernière mise à jour : 2023-11-07 10:19:37+0000

Profils: [TDDUI Document Reference](StructureDefinition-tddui-documentreference.md), `https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference`

**masterIdentifier**: 2569874526325

**status**: Current

**type**: Export DUI

**category**: Document de gestion

> **content**

### Attachments

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| - | **ContentType** | **Language** | **Data** | **Title** |
| * | text/plain | French | `SGVsbG8gd29ybGQ=` | DocumentReference TDDUI |




## Resource Content

```json
{
  "resourceType" : "DocumentReference",
  "id" : "TDDUIDocumentReferenceExample",
  "meta" : {
    "versionId" : "1",
    "lastUpdated" : "2023-11-07T10:19:37.350+00:00",
    "profile" : [
      "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference",
      "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference"
    ]
  },
  "masterIdentifier" : {
    "value" : "2569874526325"
  },
  "status" : "current",
  "type" : {
    "coding" : [
      {
        "system" : "https://mos.esante.gouv.fr/NOS/TRE_A05-TypeDocComplementaire/FHIR/TRE-A05-TypeDocComplementaire",
        "code" : "EXPORT_DUI"
      }
    ]
  },
  "category" : [
    {
      "coding" : [
        {
          "system" : "https://mos.esante.gouv.fr/NOS/TRE_A03-ClasseDocument/FHIR/TRE-A03-ClasseDocument",
          "code" : "95"
        }
      ]
    }
  ],
  "content" : [
    {
      "attachment" : {
        "contentType" : "text/plain",
        "language" : "fr",
        "data" : "SGVsbG8gd29ybGQ=",
        "title" : "DocumentReference TDDUI"
      }
    }
  ]
}

```

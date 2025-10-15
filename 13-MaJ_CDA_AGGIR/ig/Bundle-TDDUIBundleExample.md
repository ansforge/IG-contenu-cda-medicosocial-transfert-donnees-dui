# TDDUIBundleExample - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* [**Ressources FHIR**](artifacts.md)
* **TDDUIBundleExample**

## Example Bundle: TDDUIBundleExample

Profil: [TDDUI Bundle](StructureDefinition-tddui-bundle.md)

Bundle TDDUIBundleExample de type transaction

-------

Entry 1

Ressource DocumentReference :

> 

version: 1; Dernière mise à jour : 2023-11-07 10:19:37+0000

Profils: [TDDUI Document Reference](StructureDefinition-tddui-documentreference.md), `https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference`

**identifier**: 2569874526325**status**: Current**type**:Export DUI**category**:Document de gestion
> **content**

### Attachments

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| - | **ContentType** | **Language** | **Data** | **Title** |
| * | text/plain | fr | `SGVsbG8gd29ybGQ=` | DocumentReference TDDUI |



Requête :

```
POST TDDUIDocumentReference1

```

-------

Entry 2

Ressource DocumentReference :

> 

version: 1; Dernière mise à jour : 2023-11-07 10:19:37+0000

Profils: [TDDUI Document Reference](StructureDefinition-tddui-documentreference.md), `https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference`

**identifier**: 2569874526326**status**: Current**type**:Export DUI**category**:Document de gestion
> **content**

### Attachments

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| - | **ContentType** | **Language** | **Data** | **Title** |
| * | text/plain | fr | `SGVsbG8gd29ybGQ=` | DocumentReference TDDUI |



Requête :

```
POST TDDUIDocumentReference2

```



## Resource Content

```json
{
  "resourceType" : "Bundle",
  "id" : "TDDUIBundleExample",
  "meta" : {
    "profile" : [
      "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-bundle"
    ]
  },
  "type" : "transaction",
  "entry" : [
    {
      "resource" : {
        "resourceType" : "DocumentReference",
        "id" : "TDDUIDocumentReference1",
        "meta" : {
          "versionId" : "1",
          "lastUpdated" : "2023-11-07T10:19:37.350+00:00",
          "profile" : [
            "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference",
            "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference"
          ]
        },
        "text" : {
          "status" : "generated",
          "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><a name=\"DocumentReference_TDDUIDocumentReference1\"> </a><p class=\"res-header-id\"><b>Narratif généré : RéférenceDocument TDDUIDocumentReference1</b></p><a name=\"TDDUIDocumentReference1\"> </a><a name=\"hcTDDUIDocumentReference1\"> </a><div style=\"display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%\"><p style=\"margin-bottom: 0px\">version: 1; Dernière mise à jour : 2023-11-07 10:19:37+0000</p><p style=\"margin-bottom: 0px\">Profils: <a href=\"StructureDefinition-tddui-documentreference.html\">TDDUI Document Reference</a>, <code>https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference</code></p></div><p><b>masterIdentifier</b>: 2569874526325</p><p><b>status</b>: Current</p><p><b>type</b>: <span title=\"Codes:{https://mos.esante.gouv.fr/NOS/TRE_A05-TypeDocComplementaire/FHIR/TRE-A05-TypeDocComplementaire EXPORT_DUI}\">Export DUI</span></p><p><b>category</b>: <span title=\"Codes:{https://mos.esante.gouv.fr/NOS/TRE_A03-ClasseDocument/FHIR/TRE-A03-ClasseDocument 95}\">Document de gestion</span></p><blockquote><p><b>content</b></p><h3>Attachments</h3><table class=\"grid\"><tr><td style=\"display: none\">-</td><td><b>ContentType</b></td><td><b>Language</b></td><td><b>Data</b></td><td><b>Title</b></td></tr><tr><td style=\"display: none\">*</td><td>text/plain</td><td>French</td><td><code>SGVsbG8gd29ybGQ=</code></td><td>DocumentReference TDDUI</td></tr></table></blockquote></div>"
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
                "code" : "95",
                "display" : "Document de gestion"
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
      },
      "request" : {
        "method" : "POST",
        "url" : "TDDUIDocumentReference1"
      }
    },
    {
      "resource" : {
        "resourceType" : "DocumentReference",
        "id" : "TDDUIDocumentReference2",
        "meta" : {
          "versionId" : "1",
          "lastUpdated" : "2023-11-07T10:19:37.350+00:00",
          "profile" : [
            "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference",
            "https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference"
          ]
        },
        "text" : {
          "status" : "generated",
          "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><a name=\"DocumentReference_TDDUIDocumentReference2\"> </a><p class=\"res-header-id\"><b>Narratif généré : RéférenceDocument TDDUIDocumentReference2</b></p><a name=\"TDDUIDocumentReference2\"> </a><a name=\"hcTDDUIDocumentReference2\"> </a><div style=\"display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%\"><p style=\"margin-bottom: 0px\">version: 1; Dernière mise à jour : 2023-11-07 10:19:37+0000</p><p style=\"margin-bottom: 0px\">Profils: <a href=\"StructureDefinition-tddui-documentreference.html\">TDDUI Document Reference</a>, <code>https://interop.esante.gouv.fr/ig/fhir/tddui/StructureDefinition/tddui-documentreference</code></p></div><p><b>masterIdentifier</b>: 2569874526326</p><p><b>status</b>: Current</p><p><b>type</b>: <span title=\"Codes:{https://mos.esante.gouv.fr/NOS/TRE_A05-TypeDocComplementaire/FHIR/TRE-A05-TypeDocComplementaire EXPORT_DUI}\">Export DUI</span></p><p><b>category</b>: <span title=\"Codes:{https://mos.esante.gouv.fr/NOS/TRE_A03-ClasseDocument/FHIR/TRE-A03-ClasseDocument 95}\">Document de gestion</span></p><blockquote><p><b>content</b></p><h3>Attachments</h3><table class=\"grid\"><tr><td style=\"display: none\">-</td><td><b>ContentType</b></td><td><b>Language</b></td><td><b>Data</b></td><td><b>Title</b></td></tr><tr><td style=\"display: none\">*</td><td>text/plain</td><td>French</td><td><code>SGVsbG8gd29ybGQ=</code></td><td>DocumentReference TDDUI</td></tr></table></blockquote></div>"
        },
        "masterIdentifier" : {
          "value" : "2569874526326"
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
                "code" : "95",
                "display" : "Document de gestion"
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
      },
      "request" : {
        "method" : "POST",
        "url" : "TDDUIDocumentReference2"
      }
    }
  ]
}

```

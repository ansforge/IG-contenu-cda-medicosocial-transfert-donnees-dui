# TDDUI Document Reference - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* [**Ressources FHIR**](artifacts.md)
* **TDDUI Document Reference**

## Resource Profile: TDDUI Document Reference 

| | |
| :--- | :--- |
| *Official URL*:https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference | *Version*:1.0.0 |
| Active as of 2025-10-09 | *Computable Name*:TDDUIDocumentReference |

 
Profil générique créé dans le contexte du transfert de données DUI pour véhiculer un document au format CDA, inclus dans DocumentReference.attachment.data. 

**Usages:**

* Use this Profile: [TDDUI Bundle](StructureDefinition-tddui-bundle.md)
* Examples for this Profile: [DocumentReference/TDDUIDocumentReferenceExample](DocumentReference-TDDUIDocumentReferenceExample.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/ans.cda.fr.tddui|current/StructureDefinition/tddui-documentreference)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-tddui-documentreference.csv), [Excel](StructureDefinition-tddui-documentreference.xlsx), [Schematron](StructureDefinition-tddui-documentreference.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "tddui-documentreference",
  "url" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference",
  "version" : "1.0.0",
  "name" : "TDDUIDocumentReference",
  "title" : "TDDUI Document Reference",
  "status" : "active",
  "date" : "2025-10-09T12:00:32+00:00",
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
  "description" : "Profil générique créé dans le contexte du transfert de données DUI pour véhiculer un document au format CDA, inclus dans DocumentReference.attachment.data.",
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
      "identity" : "workflow",
      "uri" : "http://hl7.org/fhir/workflow",
      "name" : "Workflow Pattern"
    },
    {
      "identity" : "fhircomposition",
      "uri" : "http://hl7.org/fhir/composition",
      "name" : "FHIR Composition"
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
    },
    {
      "identity" : "v2",
      "uri" : "http://hl7.org/v2",
      "name" : "HL7 v2 Mapping"
    },
    {
      "identity" : "xds",
      "uri" : "http://ihe.net/xds",
      "name" : "XDS metadata equivalent"
    }
  ],
  "kind" : "resource",
  "abstract" : false,
  "type" : "DocumentReference",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/DocumentReference",
  "derivation" : "constraint",
  "differential" : {
    "element" : [
      {
        "id" : "DocumentReference.meta.versionId",
        "path" : "DocumentReference.meta.versionId",
        "short" : "Numéro de version de la fiche d’un document attribué par le système cible. La valeur de la métadonnée version est égale à 1 pour la première version de la fiche. Cet élément est requis lorsque le flux envoyé correspond à une mise à jour des données d’une fiche.",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.modifierExtension",
        "path" : "DocumentReference.modifierExtension",
        "max" : "0"
      },
      {
        "id" : "DocumentReference.masterIdentifier",
        "path" : "DocumentReference.masterIdentifier",
        "short" : "Représente l’identifiant unique global affecté au document par son créateur. Il est utilisable comme référence externe dans d’autres documents.",
        "min" : 1,
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.identifier",
        "path" : "DocumentReference.identifier",
        "max" : "0",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.status",
        "path" : "DocumentReference.status",
        "patternCode" : "current",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.docStatus",
        "path" : "DocumentReference.docStatus",
        "max" : "0"
      },
      {
        "id" : "DocumentReference.type",
        "path" : "DocumentReference.type",
        "definition" : "Représente le type du document.",
        "constraint" : [
          {
            "key" : "constr-bind-type",
            "severity" : "warning",
            "human" : "Les valeurs possibles pour cet élément doivent provenir d’une des terminologies de référence suivantes :\n\r\n TRE_A05-TypeDocComplementaireCISIS, OID : 1.2.250.1.213.1.1.4.12\n\r\n TRE_A12-NomenclatureASTM, OID : ASTM\n\r\nLes valeurs possibles peuvent être restreintes en fonction du jeu de valeurs correspondant mis à disposition par le projet (exemple : JDV_J66-TypeCode-DMP).\r\nEn l’absence de spécifications complémentaires, le jeu de valeurs JDV_J07-XdsTypeCode-CISIS peut être utilisé.",
            "xpath" : "f:type",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "https://mos.esante.gouv.fr/NOS/JDV_J07-XdsTypeCode-CISIS/FHIR/JDV-J07-XdsTypeCode-CISIS"
        }
      },
      {
        "id" : "DocumentReference.category",
        "path" : "DocumentReference.category",
        "short" : "Représente la classe du document (compte rendu, imagerie médicale, traitement, certificat,...).",
        "max" : "1",
        "constraint" : [
          {
            "key" : "constr-bind-category",
            "severity" : "warning",
            "human" : "Les valeurs possibles pour cet élément doivent provenir d’une des terminologies de référence suivantes :\n-\tTRE_A03-ClasseDocument-CISIS, OID : 1.2.250.1.213.1.1.4.1\n-\tTRE_A10-NomenclatureURN, OID : URN\nLes valeurs possibles peuvent être restreintes en fonction du jeu de valeurs correspondant mis à disposition par le projet (exemple : JDV_J57-ClassCode-DMP).\nEn l’absence de spécifications complémentaires, le jeu de valeurs JDV_J06-XdsClassCode-CISIS peut être utilisé.",
            "xpath" : "f:category",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "https://mos.esante.gouv.fr/NOS/JDV_J06-XdsClassCode-CISIS/FHIR/JDV-J06-XdsClassCode-CISIS"
        }
      },
      {
        "id" : "DocumentReference.subject",
        "path" : "DocumentReference.subject",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "https://hl7.fr/ig/fhir/core/StructureDefinition/fr-core-patient"
            ]
          }
        ]
      },
      {
        "id" : "DocumentReference.date",
        "path" : "DocumentReference.date",
        "short" : "Représente la date de création de la ressource DocumentReference dans FHIR",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.author",
        "path" : "DocumentReference.author",
        "short" : "Personnes physiques ou morales et/ou les dispositifs auteurs d'un document.",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.authenticator",
        "path" : "DocumentReference.authenticator",
        "short" : "Cet attribut représente l’acteur validant le document et prenant la responsabilité du contenu médical de celui-ci. Il peut s’agir de l’auteur du document si celui-ci est une personne et s’il endosse la responsabilité du contenu médical de ses documents. Si l’auteur est un dispositif, cet attribut doit représenter la personne responsable de l’action effectuée par le dispositif.",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.relatesTo",
        "path" : "DocumentReference.relatesTo",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.description",
        "path" : "DocumentReference.description",
        "short" : "Commentaire associé au document.",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.securityLabel",
        "path" : "DocumentReference.securityLabel",
        "short" : "Contient les informations définissant le niveau de confidentialité d'un document.",
        "constraint" : [
          {
            "key" : "constr-bind-securityLabel",
            "severity" : "warning",
            "human" : "Les codes pour cet élément doivent provenir du ValueSet spécifié par le standard. Lorsqu’aucun code ne correspond au concept recherché, un code provenant de la terminologie de référence TRE_A07-StatusVisibiliteDocument, OID : 1.2.250.1.213.1.1.4.13 peut être utilisé.",
            "xpath" : "f:securityLabel",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ],
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content",
        "path" : "DocumentReference.content",
        "short" : "Document contenu.",
        "definition" : "The document and format referenced.",
        "max" : "1",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.attachment.contentType",
        "path" : "DocumentReference.content.attachment.contentType",
        "min" : 1
      },
      {
        "id" : "DocumentReference.content.attachment.language",
        "path" : "DocumentReference.content.attachment.language",
        "short" : "Pour tous les documents produits par les systèmes initiateurs français, le code est \"fr-FR'.",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.attachment.data",
        "path" : "DocumentReference.content.attachment.data",
        "short" : "Le document est contenu dans l'élément .data au format base64.",
        "min" : 1
      },
      {
        "id" : "DocumentReference.content.attachment.url",
        "path" : "DocumentReference.content.attachment.url",
        "max" : "0"
      },
      {
        "id" : "DocumentReference.content.attachment.size",
        "path" : "DocumentReference.content.attachment.size",
        "short" : "Représente la taille du document."
      },
      {
        "id" : "DocumentReference.content.attachment.hash",
        "path" : "DocumentReference.content.attachment.hash",
        "short" : "Représente le résultat de hachage du document (SHA 1)."
      },
      {
        "id" : "DocumentReference.content.attachment.title",
        "path" : "DocumentReference.content.attachment.title",
        "min" : 1
      },
      {
        "id" : "DocumentReference.content.attachment.creation",
        "path" : "DocumentReference.content.attachment.creation",
        "short" : "Représente la date et l’heure de création du document.",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.content.format",
        "path" : "DocumentReference.content.format",
        "short" : "Format technique détaillé du document.",
        "constraint" : [
          {
            "key" : "constr-bind-format",
            "severity" : "warning",
            "human" : "Les valeurs possibles pour cet élément doivent provenir d’une des terminologies de référence suivantes :\n- TRE_A06-FormatCodeComplementaire, OID : 1.2.250.1.213.1.1.4.2.282\n- TRE_A11-IheFormatCode, OID : 1.3.6.1.4.1.19376.1.2.3\n- TRE_A09-DICOMuidRegistry, OID : 1.2.840.10008.2.6.1\n- TRE_A10-NomenclatureURN, OID : URN\nLes valeurs possibles peuvent être restreintes en fonction du jeu de valeurs correspondant mis à disposition par le projet (exemple : JDV_J60-FormatCode-DMP).\nEn l’absence de spécifications complémentaires, le jeu de valeurs JDV_J10-XdsFormatCode-CISIS peut être utilisé.",
            "xpath" : "f:content/f:format",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "https://mos.esante.gouv.fr/NOS/JDV_J10-XdsFormatCode-CISIS/FHIR/JDV-J10-XdsFormatCode-CISIS"
        }
      },
      {
        "id" : "DocumentReference.context",
        "path" : "DocumentReference.context",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.context.event",
        "path" : "DocumentReference.context.event",
        "short" : "Représente les actes et les pathologies en rapport avec le document.",
        "max" : "1",
        "constraint" : [
          {
            "key" : "constr-bind-context-event",
            "severity" : "warning",
            "human" : "Nomenclatures utilisées :\n- CCAM pour les actes médicaux (OID=\"1.2.250.1.213.2.5\");\n- CIM-10 pour les diagnostics de pathologie (OID=\"2.16.840.1.113883.6.3\").\n- TRE_A00-ProducteurDocNonPS pour les documents d'expression personnelle du patient.",
            "xpath" : "f:context/f:event",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ]
      },
      {
        "id" : "DocumentReference.context.period",
        "path" : "DocumentReference.context.period",
        "mustSupport" : true
      },
      {
        "id" : "DocumentReference.context.facilityType",
        "path" : "DocumentReference.context.facilityType",
        "short" : "Secteur d'activité lié à la prise en charge de la personne, en lien avec le document produit.",
        "constraint" : [
          {
            "key" : "constr-bind-ProducteurDoc-simplified",
            "severity" : "warning",
            "human" : "L’utilisation de cette nomenclature est recommandée mais non obligatoire (prefered) :\n-\tTRE_R02-SecteurActivite, OID : 1.2.250.1.71.4.2.4 (lorsque l’auteur du document est un professionnel ou un équipement sous sa responsabilité)\nLes valeurs possibles peuvent être restreintes en fonction du jeu de valeurs correspondant mis à disposition par le projet (exemple : JDV_J61-HealthcareFacilityTypeCode-DMP).\nEn l’absence de spécifications complémentaires, le jeu de valeurs JDV_J02-XdsHealthcareFacilityTypeCode-CISIS peut être utilisé.",
            "xpath" : "f:context/f:practiceSetting or f:context/f:facilityType",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "https://mos.esante.gouv.fr/NOS/JDV_J02-XdsHealthcareFacilityTypeCode-CISIS/FHIR/JDV-J02-XdsHealthcareFacilityTypeCode-CISIS"
        }
      },
      {
        "id" : "DocumentReference.context.practiceSetting",
        "path" : "DocumentReference.context.practiceSetting",
        "short" : "Cadre d’exercice de l’acte qui a engendré la création du document.",
        "constraint" : [
          {
            "key" : "constr-bind-ProducteurDoc-simplified",
            "severity" : "warning",
            "human" : "L’utilisation de cette nomenclature est recommandée mais non obligatoire (prefered) :\n-\tTRE_R02-SecteurActivite, OID : 1.2.250.1.71.4.2.4 (lorsque l’auteur du document est un professionnel ou un équipement sous sa responsabilité)\nLes valeurs possibles peuvent être restreintes en fonction du jeu de valeurs correspondant mis à disposition par le projet (exemple : JDV_J61-HealthcareFacilityTypeCode-DMP).\nEn l’absence de spécifications complémentaires, le jeu de valeurs JDV_J02-XdsHealthcareFacilityTypeCode-CISIS peut être utilisé.",
            "xpath" : "f:context/f:practiceSetting or f:context/f:facilityType",
            "source" : "https://interop.esante.gouv.fr/ig/cda/tddui/StructureDefinition/tddui-documentreference"
          }
        ],
        "mustSupport" : true,
        "binding" : {
          "strength" : "preferred",
          "valueSet" : "https://mos.esante.gouv.fr/NOS/JDV_J04-XdsPracticeSettingCode-CISIS/FHIR/JDV-J04-XdsPracticeSettingCode-CISIS"
        }
      },
      {
        "id" : "DocumentReference.context.sourcePatientInfo",
        "path" : "DocumentReference.context.sourcePatientInfo",
        "short" : "Référence vers la ressource Patient titulaire du dossier.",
        "type" : [
          {
            "code" : "Reference",
            "targetProfile" : [
              "https://hl7.fr/ig/fhir/core/StructureDefinition/fr-core-patient"
            ]
          }
        ],
        "mustSupport" : true
      }
    ]
  }
}

```

# Structure générale du document CDA - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Structure générale du document CDA**

## Structure générale du document CDA

Cette section présente la structure générale du document CDA transporté dans le cadre du volet Transfert de données DUI.

La structure de ce document se conforme aux contraintes et définitions présentées dans :

* le [Volet Structuration minimale des documents de santé](https://esante.gouv.fr/volet-structuration-minimale-de-documents-de-sante) pour l'entête du document ;
* les [Modèles de contenus CDA](https://esante.gouv.fr/volet-de-reference-modeles-de-contenus-cda) pour le corps du document

Les éléments apparaissant en bleu correspondent aux règles spécifiques à ce volet.

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| 0 | clinicalDocument |  |  | **Document CDA**@classCode = "DOCCLIN"@moodCode = "EVN" |
| 1 | realmCode | CS | [1..1] | **Périmètre d'utilisation : France**@code = "FR" |
| 1 | typeID | II | [1..1] | **Référence au standard CDA R2**@root = 2.16.840.1.113883.1.3@extension = « POCD_HD000040 » |
| 1 | templateID | II | [1..1] | **Déclaration de conformité du document aux spécifications HL7 France**@root = 2.16.840.1.113883.2.8.2.1 |
| 1 | templateID | II | [1..1] | **Déclaration de conformité du document aux spécifications CI-SIS**@root = 1.2.250.1.213.1.1.1.1 |
| 1 | templateID | II | [1..1] | **Déclaration de conformité du document au modèle de document structuré EXPORT_DUI (Export de données d'un logiciel DUI)**@root = 1.2.250.1.213.1.1.1.58@extension (facultatif) = version du guide d'implémentation utilisé |
| 1 | id | II | [1..1] | **Identifiant unique du document**@root (obligatoire) = valeur d'un OID propre à l'émetteur, formé d'un OID complet identifiant l'instance du document. |
| 1 | code | CE | [1..1] | **Type de document**@code = « EXPORT_DUI »@displayName = « Export du Dossier Usager Informatisé »@codeSystem = 1.2.250.1.213.1.1.4.12@codeSystemName = JDV_J07-XdsTypeCode-CISIS |
| 1 | title | ST | [1..1] | **Titre du document**Le titre provient soit de la saisie directe par le PS, soit d'une valeur par défaut générée par le logiciel à partir d'autres éléments (comme le type et la date du document par exemple) et modifiable par le PS. |
| 1 | effectiveTime | TS | [1..1] | **Date et heure de création du document (précisée à la seconde)**@value = Horodatage généré automatiquement par le logiciel lors de la création du document. |
| 1 | confidentialityCode | CE | [1..1] | **Niveau de confidentialité du document.**Ni le standard CDA, ni le CI-SIS ne précisent la manière dont chaque niveau doit être interprété. Ces règles d'usage sont à préciser par le système d'information qui donne les accès aux documents. Le niveau de confidentialité peut-être sélectionné par le LPS ou choisi par l'auteur ou encore configuré par défaut à la valeur "N" (normal).@code = à définir@codeSystem = 2.16.840.1.113883.5.25@displayName = à définir@codeSystemName = Confidentiality |
| 1 | languageCode | CS | [1..1] | **Langue principale du document**"fr-FR" pour français métropolitain (la casse des caractères doit être respectée)@code = « fr-FR » |
| 1 | setID | II | [1..1] | **Identification du lot de versions du même document**@root = valeur d'un OID propre à l'émetteur, formée d'un OID identifiant le lot de versions du document |
| 1 | versionNumber | INT | [1..1] | **Numéro de version d'un document permettant de suivre son évolution**@value = entier incrémenté à partir de 1 par pas de 1 à chaque nouvelle version du document |
| 1 | recordTarget |  | [1..1] | **Information sur l'identité de l'usager concerné par le document**Le contenu de l'élément est décrit dans la rubrique[recordTarget](contenu_dossier_entete_cda.md#recordtarget) |
| 1 | author |  | [1..*] | **Auteur du document**Le contenu de l'élément est décrit dans la rubrique[author](contenu_dossier_entete_cda.md#author) |
| 1 | custodian |  | [1..1] | **Structure conservant le document et garantissant son cycle de vie**Le contenu de l'élément est décrit dans la rubrique[custodian](contenu_dossier_entete_cda.md#custodian) |
| 1 | legalAuthenticator |  | [1..1] | **Responsable légal du document**Le contenu de l'élément est décrit dans la rubrique[legalAuthenticator](contenu_dossier_entete_cda.md#legalauthentificator) |
| 1 | documentationOf |  | [1..*] | **Evènement documenté**Le contenu de l'élément est décrit dans la rubrique[documentationOf](contenu_dossier_entete_cda.md#documentationof) |
| 1 | relatedDocument |  | [0..1] | **Document de référence à remplacer, transformer**Le contenu de l'élément est décrit dans la rubrique[relatedDocument](contenu_dossier_entete_cda.md#relateddocument) |
| 1 | componentOf |  | [1..1] | **Association du document à un transfert de données DUI**Le contenu de l'élément est décrit dans la rubrique[componentOf](contenu_dossier_entete_cda.md#componentof) |
| 1 | component |  | [1..1] | Représente le corps du document CDA |
| 2 | structuredBody |  | [1..1] |  |
| 3 | component |  | [0..1] |  |
| 4 | section FR-Couvertures-sociales |  | [0..1] | **Description de la couverture sociale du patient.**Le contenu de l'élément est décrit dans la rubrique[Section FR-Evaluation-du-statut-fonctionnel](contenu_dossier_corps_cda.md#section-fr-couvertures-sociales) |
| 3 | component |  | [0..1] |  |
| 4 | section FR-Sejours |  | [0..1] | **Cette section contient les informations relatives au séjour d’un usager au sein d’une structure.**Le contenu de l'élément est décrit dans la rubrique[Section FR-Sejours](contenu_dossier_corps_cda.md#section-fr-sejours) |
| 3 | component |  | [0..1] |  |
| 4 | section FR-Evenements |  | [0..1] | **Liste les évènements liés à la prise en charge du patient dans un domaine défini.**Le contenu de l'élément est décrit dans la rubrique[Section FR-Evenements](contenu_dossier_corps_cda.md#section-fr-evenements) |
| 3 | component |  | [0..1] |  |
| 4 | section FR-Statut-fonctionnel |  | [0..1] | **Cette section permet de décrire des résultats d'évaluation du statut fonctionnel du patient.**Le contenu de l'élément est décrit dans la rubrique[Section FR-Statut-fonctionnel](contenu_dossier_corps_cda.md#section-fr-statut-fonctionnel) |
| 3 | component |  | [0..1] |  |
| 4 | section FR-Documents-ajoutes |  | [0..1] | **Informations sur les pièces jointes ajoutées au document**Le contenu de l'élément est décrit dans la rubrique[FR-Documents-ajoutes](contenu_dossier_corps_cda.md#section-fr-documents-ajoutes) |


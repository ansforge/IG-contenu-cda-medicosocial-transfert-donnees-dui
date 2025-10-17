# Entête du document CDA - Médicosocial - Transfert de données DUI CDA v1.0.1

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Entête du document CDA**

## Entête du document CDA

### RecordTarget

Le RecordTarget reprend l'identité de l'usager concerné par l'accompagnement détaillé dans le document CDA ainsi que, le cas échéant, l'identité de son représentant légal.

La structure du RecordTarget se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé**. Dans la mesure du possible, le RecordTarget doit également se conformer à l'annexe CI-SIS de [Prise en charge de l’identité nationale de santé (INS) dans les standards d’interopérabilité et les volets du CI-SIS](https://esante.gouv.fr/annexe-prise-en-charge-de-lins-dans-les-volets-du-ci-sis).

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.10-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="RecordTarget" height="400"></iframe>
Lien vers le template : [RecordTarget](./cda/tmp-1.2.250.1.213.1.1.1.1.10.10-DYNAMIC.md)

**Le tableau ci-dessous présente les contraintes spécifiques à l'entête TDDUI :**

| | | |
| :--- | :--- | :--- |
| patientRole/id | [1..*] | **Identifiants*** Matricule INS de l'usager (à véhiculer s'il est disponible) : 
* Si INS-NIR : @root="1.2.250.1.213.1.4.8"
* Si INS-NIA : @root="1.2.250.1.213.1.4.9"
 
* Numéro de sécurité sociale de l'usager : 
* Si NSS-NIR : @root="1.2.250.1.213.1.4.13"
* Si NSS-NIA : @root="1.2.250.1.213.1.4.14"
 
* Identifiant local de l'usager au sein de l'ESMS ; l'identifiant se forme en concaténant : 3+FINESS/identifiantLocalUsagerESSMS
* Identifiant initial attribué par la MDPH
 |
| patientRole/patient/name/family | [1..*] | Au moins un nom doit être transmis. L'attribut nullFlavor est interdit. |
| patientRole/patient/name/family@qualifier="BR" | [0..1] | **Nom de naissance*** Si le matricule INS de l'usager est présent, cet élément est obligatoire et l'attribut nullFlavor est interdit.
* Si le matricule INS de l'usager n'est pas présent, il est préconisé de renseigner le nom de naissance de l'usager. Cet élément est optionnel.
 |
| patientRole/patient/name/given | [1..*] | Au moins un prénom doit être transmis. L'attribut nullFlavor est interdit. |
| patientRole/patient/name/given (pas de qualifier) | [0..1] | **Liste des prénoms de l'acte de naissance*** Si le matricule INS de l'usager est présent, cet élément est obligatoire et l'attribut nullFlavor est interdit.
* Si le matricule INS de l'usager n'est pas présent, il est préconisé de renseigner la liste des prénoms de l'acte de naissance de l'usager. Cet élément est optionnel.
 |
| patientRole/patient/name/given@qualifier="BR" | [0..1] | **Premier prénom*** Si le matricule INS de l'usager est présent, cet élément est obligatoire et l'attribut nullFlavor est interdit.
* Si le matricule INS de l'usager n'est pas présent, il est préconisé de renseigner le premier prénom de l'usager. Cet élément est optionnel.
 |
| patientRole/patient/administrativeGenderCode | [1..1] | **Sexe*** Si le matricule INS de l'usager est présent, cet élément est obligatoire et l'attribut nullFlavor est interdit.
* Si le matricule INS de l'usager n'est pas présent, il est préconisé de renseigner cet élément. Si le sexe de l'usager n'est pas connu de votre système, l'attribut nullFlavor peut être utilisé.
 |
| patientRole/patient/birthTime | [1..1] | **Date de naissance*** Si le matricule INS de l'usager est présent, cet élément est obligatoire et l'attribut nullFlavor est interdit.
* Si le matricule INS de l'usager n'est pas présent, il est préconisé de renseigner cet élément. Si la date et l'heure de naissance de l'usager n'est pas connue de votre système, l'attribut nullFlavor peut être utilisé.
 |
| patientRole/patient/birthplace/place/addr/county | [0..1] | **Lieu de naissance*** Si le matricule INS de l'usager est présent, le lieu de naissance de l'usager est obligatoire et l'attribut nullFlavor est interdit.
* Si le matricule INS de l'usager n'est pas présent, il est préconisé de renseigner le lieu de naissance de l'usager. Cet élément est optionnel.
 |
| patientRole/patient/sdtc:multipleBirthOrderNumber | [0..1] | **Ordre d’enregistrement de la naissance dans le registre d’état civil de la commune de naissance**Si le matricule INS de l'usager n'est pas présent, l'ordre de naissance de l'usager est requis. |

### Author

L’Author permet d'enregistrer un auteur du document. Dans le contexte de ce volet, l’Author fait référence à un **logiciel DUI** (Dossier Usager Informatisé). Ce logiciel est responsable de la création du document.

La structure de l'Author se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.7-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="Author" height="400"></iframe>
Lien vers le template : [Author](./cda/tmp-1.2.250.1.213.1.1.1.1.10.7-DYNAMIC.md)

**Le tableau ci-dessous présente les contraintes spécifiques à l'entête TDDUI :**

| | | |
| :--- | :--- | :--- |
| assignedAuthor/id | [1..1] | **Identifiant de l'auteur**Attribut nullFlavor interdit@root = "1.2.250.1.71.4.2.1" (OID autorité d'attribution des systèmes et des professionnels)@extension = Valeur de l'identifiant :Concaténation de :- Identifiant de la structure (avec le préfixe indiqué dans l'annexe[Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)au paragraphe PS_IdNat)- Caractère "/"- Identifiant interne du système dans la structure |
| assignedAuthor/code | [1..1] | **Profession / savoir-faire ou rôle**@code = "LOGICIEL_DUI"@displayName = "Logiciel de Dossier Usager Informatisé"@codeSystem = "1.2.250.1.213.1.1.4.6" |
| assignedAuthor/assignedAuthoringDevice | [1..1] | **Informations complémentaires**• Obligatoire pour un système |
| assignedAuthor/representedOrganization | [1..1] | **Structure correspondante**• Obligatoire pour un système |
| assignedAuthor/representedOrganization/id | [0..1] | **Identifiant de la structure**@root = "1.2.250.1.71.4.2.2" (OID autorité d'attribution des identifiants des structures)@extension = Struct_idNat (voir[Annexe - Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)) |

### Custodian

Le Custodian représente la structure chargée de la conservation du document. Il s’agit dans le cadre de ce volet de l’**ESSMS** (Établissement ou Service Social et Médico-Social) qui est responsable de la garde et de la sécurité du document. En tant qu’entité juridique, l’ESSMS est le dépositaire du dossier de l’usager et garantit la confidentialité, l’intégrité et la sécurité des données.

La structure du Custodian se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.5-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="Custodian" height="400"></iframe>
Lien vers le template : [Custodian](./cda/tmp-1.2.250.1.213.1.1.1.1.10.5-DYNAMIC.md)

**Le tableau ci-dessous présente les contraintes spécifiques à l'entête TDDUI :**

| | | |
| :--- | :--- | :--- |
| assignedCustodian/representedCustodianOrganization/id | [1..1] | **Identifiant de la structure ESSMS**@root = "1.2.250.1.71.4.2.2" (OID autorité d'attribution des identifiants des structures)@extension = Struct_idNat (voir[Annexe - Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)) |
| assignedCustodian/representedCustodianOrganization/name | [0..1] | **Nom de la structure ESSMS**Valeur fixée à Struct_Nom (voir[Annexe - Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)) |

### LegalAuthentificator

Le LegalAuthentificator représente le responsable du document. Dans le cadre de ce volet, le rôle du legalAuthenticator est rempli par le **logiciel DUI** qui valide officiellement le document en lui conférant une valeur légale et authentique.

La structure du LegalAuthentificator se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.6-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="LegalAuthenticator" height="400"></iframe>
Lien vers le template : [LegalAuthentificator](./cda/tmp-1.2.250.1.213.1.1.1.1.10.6-DYNAMIC.md)

**Le tableau ci-dessous présente les contraintes spécifiques à l'entête TDDUI :**

| | | |
| :--- | :--- | :--- |
| assignedEntity/id | [1..1] | **Identifiant du système responsable de la production du document**Attribut nullFlavor interdit@root = "1.2.250.1.71.4.2.1" (OID autorité d'attribution des systèmes et des professionnels)@extension = Valeur de l'identifiant :Concaténation de :- Identifiant de la structure (avec le préfixe indiqué dans l'annexe[Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)au paragraphe PS_IdNat)- Caractère "/"- Identifiant interne du système dans la structure |
| assignedEntity/code | [0..1] | **Profession ou rôle du responsable**@code = "LOGICIEL_DUI"@displayName = "Logiciel de Dossier Usager Informatisé"@codeSystem = "1.2.250.1.213.1.1.4.6" |
| assignedEntity/representedOrganization/id | [0..*] | **Structure responsable du document**Attribut nullFlavor interdit@root = "1.2.250.1.71.4.2.2" (OID autorité d'attribution des identifiants des structures)@extension = Struct_idNat (voir[Annexe - Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)) |

### DocumentationOf

Le DocumentationOf documente le transfert de données depuis un logiciel DUI.

La structure du DocumentationOf se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.4-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="DocumentationOf" height="400"></iframe>
Lien vers le template : [DocumentationOf](./cda/tmp-1.2.250.1.213.1.1.1.1.10.4-DYNAMIC.md)

**Le tableau ci-dessous présente les contraintes spécifiques à l'entête TDDUI :**

| | | |
| :--- | :--- | :--- |
| serviceEvent/effectiveTime | [1..1] | **Date de création du document**Attribut nullFlavor interdit |
| serviceEvent/performer | [1..1] | **Système ayant réalisé le transfert de données**Attribut nullFlavor interdit |
| serviceEvent/performer/assignedEntity/id | [1..1] | **Identifiant du système responsable du transfert de données**@root = "1.2.250.1.71.4.2.1" (OID autorité d'attribution des systèmes et des professionnels)@extension = Valeur de l'identifiant :Concaténation de :- Identifiant de la structure (avec le préfixe indiqué dans l'annexe[Sources des données personnes et structures](https://esante.gouv.fr/annexe-sources-des-donnees-personnes-et-structures)au paragraphe PS_IdNat)- Caractère "/"- Identifiant interne du système dans la structure |
| serviceEvent/performer/assignedEntity/code | [0..1] | **Système utilisé**@code = "LOGICIEL_DUI"@displayName = "Logiciel de Dossier Usager Informatisé"@codeSystem = "1.2.250.1.213.1.1.4.6" |
| serviceEvent/performer/assignedEntity/representedOrganization/standardIndustryClassCode | [1..1] | **Structure**@code = "ESSMS"@displayName = "Etablissement ou Service Social ou Médico-Social"@codeSystem = "1.2.250.1.213.1.1.4.9" |

### RelatedDocument

L'élément RelatedDocument est facultatif dans le cas où le document actuel est initial, c’est-à-dire qu'il n'y a pas de document préexistant à remplacer. Cependant, lorsque le document est une nouvelle version d’un document déjà existant, cet élément devient obligatoire. Il permet alors de référencer précisément le document précédent qui est mis à jour ou remplacé. Cela garantit une continuité dans la gestion des informations, en identifiant clairement la relation entre les versions successives d’un même document. Le système doit inclure un identifiant unique du document précédent afin d'assurer la traçabilité et l'intégrité des données dans le parcours médico-social de l'usager.

La structure du RelatedDocument se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.3-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="RelatedDocument" height="400"></iframe>
Lien vers le template : [RelatedDocument](./cda/tmp-1.2.250.1.213.1.1.1.1.10.3-DYNAMIC.md)

### ComponentOf

Le ComponentOf permet de lier le document à un transfert de données DUI.

La structure du ComponentOf se conforme aux contraintes et définitions présentées dans le **Volet Structuration minimale des documents de santé** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.1.10.2-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="ComponentOf" height="400"></iframe>
Lien vers le template : [ComponentOf](./cda/tmp-1.2.250.1.213.1.1.1.1.10.2-DYNAMIC.md)

**Le tableau ci-dessous présente les contraintes spécifiques à l'entête TDDUI :**

| | | |
| :--- | :--- | :--- |
| componentOf/encompassingEncounter/location/healthCareFacility/code | [1..1] | Le code issu du JDV_J02_XdsHealthcareFacilityTypeCode_CISIS prend l'une des valeurs suivantes :* @code = "SA16" et @codeSystem = "1.2.250.1.71.4.2.4" @displayName = "Etablissement pour personnes handicapées"
* @code = "SA18" et @codeSystem = "1.2.250.1.71.4.2.4" @displayName = "Etablissement aide à la famille"
* @code = "SA41" et @codeSystem = "1.2.250.1.71.4.2.4" @displayName = "Autre établissement du domaine social ou médico-social"
(voir[Table de correspondance entre secteur d'activité et catégorie d'établissement](https://esante.gouv.fr/sites/default/files/media_entity/documents/Tableau_secteurs_activite_RPPS.pdf)) |
| componentOf/encompassingEncounter/location/healthCareFacility/code/translation | [1..1] | La catégorie de l'établissement est issue du JDV_J254_CategorieEtablissementESSMSPH. |


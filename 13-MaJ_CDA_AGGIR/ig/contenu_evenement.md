# Evénement - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Evénement**

## Evénement

### Section FR-Evenements

Cette section contient l'ensemble des évènements (passés ou à venir) d'un usager.

La structure de la section se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.2.248-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Evenements" height="400"></iframe>
Lien vers le template : [FR-Evenements](./cda/tmp-1.2.250.1.213.1.1.2.248-DYNAMIC.md)

#### Entrée FR-Evenement

Cette entrée permet de décrire un évènement de l'usager passé ou à venir.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.215-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Evenement" height="400"></iframe>
Lien vers le template : [FR-Evenement](./cda/tmp-1.2.250.1.213.1.1.3.215-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Evenement :**

| | | |
| :--- | :--- | :--- |
| id | [1..1] | **Identifiant unique de l'évènement**L'identifiant se forme en concaténant : 3+FINESS/identifiantLocalUsagerESSMS-EVN-numEvenement |
| code | [1..1] | Valeur fixée à :@code = "GEN-367"@codeSystem = "1.2.250.1.213.1.1.4.322"@displayName = "Agenda de l'usager" |
| code/qualifier/name | [0..1] | **Type évènement SSIAD**S'il s'agit d'un évènement SSIAD, la valeur de l'élément name est fixée à :@code = "GEN-364"@codeSystem = "1.2.250.1.213.1.1.4.322"@displayName = "Réforme SSIAD"**Type évènement SERAFIN**S'il s'agit d'un évènement SERAFIN, la valeur de l'élément name est fixée à :@code = "GEN-363"@codeSystem = "1.2.250.1.213.1.1.4.322"@displayName = "Réforme SERAFIN" |
| code/qualifier/value | [1..1] | **Type évènement SSIAD**Valeur issue du JDV_TypeEvenementSSIAD_CISIS**Type évènement SERAFIN**Valeur issue du JDV_J283-PrestationsIndirects_SERAFIN ou du JDV_J284-PrestationsDirects_SERAFIN |
| code/originalText | [0..1] | **Type évènement non structuré**Référence le texte décrivant les types d'évènements au format texte. |
| text | [0..1] | Référence le texte décrivant le libellé et/ou le motif de l'évènement |
| effectiveTime | [1..1] | L'attribut nullFlavor est interdit. |
| effectiveTime/low | [1..1] | L'attribut nullFlavor est interdit. |
| effectiveTime/high | [1..1] | L'attribut nullFlavor est interdit. |
| participant | [0..2] | L'évènement peut être attaché à deux participants : le lieu d'exécution et l'entité juridique responsable de l'évènement. |
| participant[@typeCode="RESP"]/participantRole/scopingEntity | [0..1] | **Entité juridique responsable de l'évènement**Si aucun séjour est renseigné, l'entité juridique responsable de l'évènement est requise. |
| participant[@typeCode="RESP"]/participantRole/scopingEntity/id | [1..1] | **Identifiant de l'entité juridique responsable de l'évènement**Si l'entité juridique responsable de l'évènement est renseignée, son identifiant est requis. |
| performer/assignedEntity/id | [1..1] | Si le professionnel est renseigné, son identifiant est requis. |
| entryRelationship/observation[templateId/@root="1.2.250.1.213.1.1.3.48"]/code | [1..1] | **Caractéristique de l'évènement**Dans l'entrée FR-Evenement, l'élément code de l'entrée FR-Simple-Observation doit prendre l'une des valeurs suivantes :* @code = "GEN-347" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Evènement hors prestation"
* @code = "GEN-349" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Type de ressource utilisée"
* @code = "GEN-350" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Repas inclus"
* @code = "38887-6" @codeSystem = "2.16.840.1.113883.6.1" @displayName = "Personne présente au moment de l'évènement"
* @code = "106177-9" @codeSystem = "2.16.840.1.113883.6.1" @displayName = "Date de dernière mise à jour"
 |
| entryRelationship/observation[templateId/@root="1.2.250.1.213.1.1.3.48"]/value | [1..1] | **Caractéristique de l'évènement**Le type de l'élément value de l'entrée FR-Simple-Observation est détaillé ci-dessous. |
| entryRelationship[observation/templateId/@root="1.2.250.1.213.1.1.3.217"] | [0..*] | **Statut métier de l’évènement**Dans l'entrée FR-Statut, l'élément value est limité aux valeurs suivantes :* @code = "PLANIFIE" @codeSystem = "1.2.250.1.213.3.3.250"
* @code = "REALISE" @codeSystem = "1.2.250.1.213.3.3.250"
* @code = "VALIDE" @codeSystem = "1.2.250.1.213.3.3.250"
* @code = "ANNULE" @codeSystem = "1.2.250.1.213.3.3.250"
 |

Dans les entrées FR-Simple-Observation, le type de l'élément value dépend de la valeur de l'élément code :

| | |
| :--- | :--- |
| GEN-347 (Evènement hors prestation) | BL |
| GEN-349 (Type de ressource utilisée) | CDValeur issue du JDV_RessourceUtilisee_CISIS* Si l'élément value/@code = "ORG-206" (Matériel spécialisé) alors la valeur de l'élément value/qualifier est issue du JDV_DetailMaterielSpecialise_CISIS.
* Si l'élément value/@code = "ORG-207" (Ressource immobilière) alors la valeur de l'élément value/qualifier est issue du JDV_DetailRessourceImmobiliereUtilisee_CISIS.
 |
| GEN-350 (Repas inclus) | BL |
| 38887-6 (Personne présente au moment de l'évènement) | BL |
| 106177-9 (Date de dernière mise à jour) | TS |

##### Entrée FR-Transport-du-patient

Cette entrée permet de décrire le transport de l'usager lors de l'évènement.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.24-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Transport-du-patient" height="400"></iframe>
Lien vers le template : [FR-Transport-du-patient](./cda/tmp-1.2.250.1.213.1.1.3.24-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Transport-du-patient :**

| | | |
| :--- | :--- | :--- |
| @moodCode | [1..1] | Valeur fixée à EVN |
| id | [1..1] | **Identifiant unique du transport**L'identifiant se forme en concaténant : 3+FINESS/identifiantLocalUsagerESSMS-TPPat-idTransport |
| code | [1..1] | Le code issu du JDV_ModeDeTransport_CISIS est restreint aux valeurs suivantes :* @code = "ORG-202" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Véhicule individuel"
* @code = "ORG-203" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Véhicule collectif"
* @code = "ORG-204" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Transport en commun" 
* @code = "ORG-205" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Modes doux" 
* @code = "GEN-092.06.08" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Autre mode de transport" 
 |
| code/qualifier[name/@code="GEN-346"] | [1..1] | **Type de motorisation**L'élément qualifier permettant de véhiculer le type de motorisation (l'attribut @code de l'élément name prend la valeur "GEN-346") ne doit pas être renseigné lorsque l'élément code de l'entrée FR-Transport-du-patient prend l'une des valeurs suivantes :* code/@code = "ORG-204" (Transport en commun)
* code/@code = "ORG-205" (Modes doux)
* code/@code = "GEN-092.06.08" (Autre mode de transport)
 |
| code/qualifier[name/@code="GEN-345"]/value | [1..1] | **Nature du transport**Valeur issue du JDV_J282-TransportsLiesAuProjetIndividuel_SERAFIN |
| effectiveTime/low | [1..1] | L'attribut nullFlavor est interdit. |
| effectiveTime/high | [1..1] | L'attribut nullFlavor est interdit. |
| performer/assignedEntity/representedOrganization/id | [1..1] | **Identifiant du transporteur**Si le transporteur est renseigné, son identifiant est requis. |
| entryRelationship/observation[templateId/@root="1.2.250.1.213.1.1.3.48"]/code | [1..1] | **Précision sur le trajet ou le transport du patient**Dans l'entrée FR-Transport-du-patient, l'élément code de l'entrée FR-Simple-Observation doit prendre l'une des valeurs suivantes :* @code = "MED-1124" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Patient nécessitant un accompagnement par un tiers"
* @code = "ORG-200" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Budget réel"
* @code = "ORG-201" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Budget prévisionnel"
* @code = "GEN-353" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Durée de transport théorique"
* @code = "275827007" @codeSystem = "2.16.840.1.113883.6.96" @displayName = "maintien de l'asepsie"
* @code = "103208-5" @codeSystem = "2.16.840.1.113883.6.1" @displayName = "Distance parcourue"
 |
| entryRelationship/observation[templateId/@root="1.2.250.1.213.1.1.3.48"]/value | [1..1] | **Précision sur le trajet ou le transport du patient**Le type de l'élément value de l'entrée FR-Simple-Observation est détaillé ci-dessous. |

Dans les entrées FR-Simple-Observation, le type de l'élément value dépend de la valeur de l'élément code :

| | |
| :--- | :--- |
| MED-1124 (Patient nécessitant un accompagnement par un tiers) | BL |
| ORG-200 (Budget réel) | MO |
| ORG-201 (Budget prévisionnel) | MO |
| GEN-353 (Durée de transport théorique) | IVL_TS |
| 275827007 (Maintien de l'asepsie) | BL |
| 103208-5 (Distance parcourue) | PQ |

##### Entrée FR-Transport-du-professionnel

Cette entrée permet de décrire le transport d'un professionnel lors de l'évènement.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.216-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Transport-du-professionnel" height="400"></iframe>
Lien vers le template : [FR-Transport-du-professionnel](./cda/tmp-1.2.250.1.213.1.1.3.216-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Transport-du-professionnel :**

| | | |
| :--- | :--- | :--- |
| @moodCode | [1..1] | Valeur fixée à EVN |
| id | [1..1] | **Identifiant unique du transport**L'identifiant se forme en concaténant : 3+FINESS/identifiantLocalUsagerESSMS-TPPro-idTransport |
| code | [1..1] | Le code issu du JDV_ModeDeTransport_CISIS est restreint aux valeurs suivantes :* @code = "ORG-202" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Véhicule individuel"
* @code = "ORG-203" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Véhicule collectif"
* @code = "ORG-204" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Transport en commun" 
* @code = "ORG-205" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Modes doux" 
* @code = "GEN-092.06.08" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Autre mode de transport" 
 |
| code/qualifier | [0..1] | **Type de motorisation**L'élément qualifier ne doit pas être renseigné lorsque l'élément code de l'entrée FR-Transport-du-professionnel prend l'une des valeurs suivantes :* @code = "ORG-204" (Transport en commun)
* @code = "ORG-205" (Modes doux)
* @code = "GEN-092.06.08" (Autre mode de transport)
 |
| effectiveTime/low | [1..1] | L'attribut nullFlavor est interdit. |
| effectiveTime/high | [1..1] | L'attribut nullFlavor est interdit. |
| participant[@typeCode="RCV"]/participantRole/id | [1..1] | **Identifiant du professionnel**L'identifiant du professionnel est requis. |
| participant[@typeCode="RCV"]/participantRole/scopingEntity/id | [1..1] | **Identifiant de l'établissement de rattachement du professionnel**Si l'établissement de rattachement du professionnel est renseigné, son identifiant est requis. |
| performer/assignedEntity/representedOrganization/id | [1..1] | **Identifiant du transporteur**Si le transporteur est renseigné, son identifiant est requis. |
| entryRelationship/observation[templateId/@root="1.2.250.1.213.1.1.3.48"]/code | [1..1] | **Précision sur le trajet ou le transport du professionnel**Dans l'entrée FR-Transport-du-professionnel, l'élément code de l'entrée FR-Simple-Observation doit prendre l'une des valeurs suivantes :* @code = "ORG-200" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Budget réel"
* @code = "ORG-201" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Budget prévisionnel"
* @code = "GEN-353" @codeSystem = "1.2.250.1.213.1.1.4.322" @displayName = "Durée de transport théorique"
* @code = "103208-5" @codeSystem = "2.16.840.1.113883.6.1" @displayName = "Distance parcourue"
 |
| entryRelationship/observation[templateId/@root="1.2.250.1.213.1.1.3.48"]/value | [1..1] | **Précision sur le trajet ou le transport du professionnel**Le type de l'élément value de l'entrée FR-Simple-Observation est détaillé ci-dessous. |

Dans les entrées FR-Simple-Observation, le type de l'élément value dépend de la valeur de l'élément code :

| | |
| :--- | :--- |
| ORG-200 (Budget réel) | MO |
| ORG-201 (Budget prévisionnel) | MO |
| GEN-353 (Durée de transport théorique) | IVL_TS |
| 103208-5 (Distance parcourue) | PQ |


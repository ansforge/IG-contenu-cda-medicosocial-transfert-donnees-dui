# Corps du document CDA - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Corps du document CDA**

## Corps du document CDA

### Section FR-Sejours

Cette section contient les informations relatives au(x) séjour(s) d'un usager dans une structure ESSMS.

La structure de la section se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.2.249-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Sejours" height="400"></iframe>
Lien vers le template : [FR-Sejours](./cda/tmp-1.2.250.1.213.1.1.2.249-DYNAMIC.md)

#### Entrée FR-Sejour

Cette entrée est un élément de type organizer permettant de décrire le séjour d’un usager.

La structure de l’entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.219-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Sejour" height="400"></iframe>
Lien vers le template : [FR-Sejour](./cda/tmp-1.2.250.1.213.1.1.3.219-DYNAMIC.md)

##### Entrée FR-Sejour-Admission

Cette entrée permet de décrire les données relatives à l'admission de l'usager au sein d'une structure.

La structure de l’entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.218-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Sejour-Admission" height="400"></iframe>
Lien vers le template : [FR-Sejour-Admission](./cda/tmp-1.2.250.1.213.1.1.3.218-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Sejour-Admission :**

| | | |
| :--- | :--- | :--- |
| id | [1..1] | **Identifiant unique du séjour**L'identifiant se forme en concaténant : 3+FINESS/identifiantLocalUsagerESSMS-SEJOUR-numeroDossier |
| code | [1..1] | Valeur fixée à :@code = GEN-351@codeSystem = 1.2.250.1.213.1.1.4.322@displayName = Établissement ou service social ou médico-social (ESSMS) (optionnel) |
| participant[@classCode=RESP]/participantRole/scopingEntity/id | [1..1] | **Identifiant de l'entité juridique responsable du séjour**L'identifiant de la structure est requis. |

##### Entrée FR-Modalite-entree

Cette entrée permet d'indiquer la modalité d'entrée d'un usager dans un établissement.

La structure de l’entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.48.6-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Modalite-entree" height="400"></iframe>
Lien vers le template : [FR-Modalite-entree](./cda/tmp-1.2.250.1.213.1.1.3.48.6-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Modalite-entree :**

| | | |
| :--- | :--- | :--- |
| text/reference | [0..1] | Référence le texte décrivant le libellé du mode d'entrée du séjour. |
| value | [1..1] | nullFlavor='NA' |

##### Entrée FR-Modalite-sortie

Cette entrée permet d'indiquer la modalité de sortie d'un usager dans un établissement.

La structure de l’entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.48.7-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Modalite-sortie" height="400"></iframe>
Lien vers le template : [FR-Modalite-sortie](./cda/tmp-1.2.250.1.213.1.1.3.48.7-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Modalite-sortie :**

| | | |
| :--- | :--- | :--- |
| text/reference | [0..1] | Référence le texte décrivant le libellé du mode de sortie du séjour. |
| value | [1..1] | nullFlavor='NA' |

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

### Section FR-Couvertures-sociales

Cette section contient les informations relatives à la couverture sociale du patient.

La structure de la section se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.2.79-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Couvertures-sociales" height="400"></iframe>
Lien vers le template : [FR-Couvertures-sociales](./cda/tmp-1.2.250.1.213.1.1.2.79-DYNAMIC.md)

#### Entrée FR-Couverture-sociale

Cette entrée de type act permet de lister les organismes d’assurance maladie du patient.

La structure de l’entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.61-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Couverture-sociale" height="400"></iframe>
Lien vers le template : [FR-Couverture-sociale](./cda/tmp-1.2.250.1.213.1.1.3.61-DYNAMIC.md)

#### Entrée FR-Organisme-assurance-maladie

Cette entrée de type act permet de décrire un organisme d’assurance maladie.

La structure de l’entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.94-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Organisme-assurance-maladie" height="400"></iframe>
Lien vers le template : [FR-Organisme-assurance-maladie](./cda/tmp-1.2.250.1.213.1.1.3.94-DYNAMIC.md)

### Section FR-Statut-fonctionnel

La section FR-Statut-fonctionnel permet de fournir les résultats d’évaluation de l’usager (AGGIR, évaluation de la situation SSIAD, SERAFIN…).

La structure de la section se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.2.246-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Statut-fonctionnel" height="400"></iframe>
Lien vers le template : [FR-Statut-fonctionnel](./cda/tmp-1.2.250.1.213.1.1.2.246-DYNAMIC.md)

#### Entrée FR-Groupe-de-questionnaires-d-evaluation

L'entrée FR-Groupe-de-questionnaires-d-evaluation permet de regrouper les évaluations par type.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.95-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Groupe-de-questionnaires-d-evaluation" height="400"></iframe>
Lien vers le template : [FR-Groupe-de-questionnaires-d-evaluation](./cda/tmp-1.2.250.1.213.1.1.3.95-DYNAMIC.md)

**Contrainte spécifique à l'entrée FR-Groupe-de-questionnaires-d-evaluation :**

Une entrée FR-Groupe-de-questionnaires-d-evaluation doit être créée par type d'évaluation véhiculé.

| | | |
| :--- | :--- | :--- |
| code | [1..1] | Valeur issue du JDV_TypeEvaluation_CISIS |

##### Entrée FR-Evaluation

L'entrée FR-Evaluation permet de véhiculer le résultat d'une évaluation de l'usager. Le détail de l'évaluation peut être transmis à travers des sous-entrées FR-Evaluation-Composant et FR-Evaluation-Composant-N2.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.25-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Evaluation" height="400"></iframe>
Lien vers le template : [FR-Evaluation](./cda/tmp-1.2.250.1.213.1.1.3.25-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Evaluation :**

| | | |
| :--- | :--- | :--- |
| id | [1..1] | **Identifiant unique de l'évaluation**L'identifiant se forme en concaténant : 3+FINESS/identifiantLocalUsagerESSMS-EVAL-numEvaluation |
| code | [1..1] | **Type d'évaluation**Valeur issue du JDV_TypeEvaluation_CISIS |
| performer/assignedEntity/id | [1..1] | **Identifiant de l'évaluateur**Si l'évaluateur est renseigné, son identifiant est requis. |
| performer/assignedEntity/representedOrganization/id | [1..1] | **Identifiant de l'établissement de rattachement de l'évaluateur**Si l'établissement de rattachement de l'évaluateur est renseigné, son identifiant est requis. |
| author/assignedAuthor/id | [1..1] | **Identifiant de l'auteur de l'évaluation**Si l'auteur de l'évaluation est renseigné, son identifiant est requis. |
| author/assignedAuthor/representedOrganization/id | [1..1] | **Identifiant de l'établissement de rattachement de l'auteur de l'évaluation**Si l'établissement de rattachement de l'auteur de l'évaluation est renseigné, son identifiant est requis. |
| participant[@typeCode=RESP]/participantRole/scopingEntity/id | [1..1] | **Identifiant du responsable de l'évaluation**Si le responsable de l'évaluation est renseigné, son identifiant est requis. |
| participant[@typeCode=RESP]/participantRole/scopingEntity/id | [1..1] | **Identifiant de l'établissement de rattachement du responsable de l'évaluation**Si l'établissement de rattachement du responsable de l'évaluation est renseigné, son identifiant est requis. |
| entryRelationship[observation/templateId/@root="1.2.250.1.213.1.1.3.214"] | [0..*] | **Champ évalué**Dans le cadre d'une évaluation de type "Evaluation AGGIR PH SSIAD"/"Evaluation AGGIR PA SSIAD", l'ensemble des composants des jeux de valeurs respectifs JDV_EvaluationAGGIRPH_CISIS/JDV_EvaluationAGGIRPA_CISIS doivent être évalués. Le nombre d'entrées FR-Evaluation-Composant est ainsi équivalent au nombre de composants présents dans les jeux de valeurs. |

Dans l'entrée FR-Evaluation, le résultat de l'évaluation (value) dépend du type de l'évaluation (code). Le type de l'évaluation doit quant à lui être identique au type du groupe d'évaluation (code) de l'entrée FR-Groupe-de-questionnaires-d-evaluation :

| | | |
| :--- | :--- | :--- |
| Evaluation AGGIR PH SSIAD | Evaluation AGGIR PH SSIAD | Valeur issue du JDV_GIR_CISISL'attribut nullFlavor est interdit. |
| Evaluation AGGIR PA SSIAD | Evaluation AGGIR PA SSIAD | Valeur issue du JDV_GIR_CISISL'attribut nullFlavor est interdit. |
| Evaluation de la situation SSIAD | Evaluation de la situation SSIAD | nullFlavor='NA' |
| Evaluation SERAFIN | Evaluation SERAFIN | nullFlavor='NA' |

##### Entrée FR-Evaluation-Composant

L'entrée FR-Evaluation-Composant permet de porter le résultat d'un champ évalué. Le détail de l’évaluation de ce champ peut être transmis à travers des sous-entrées FR-Evaluation-Composant-N2.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.214-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Evaluation-Composant" height="400"></iframe>
Lien vers le template : [FR-Evaluation-Composant](./cda/tmp-1.2.250.1.213.1.1.3.214-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Evaluation-Composant :**

Le champ évalué (code), le type de résultat de ce champ évalué (value) ainsi que le détail du champ évalué (FR-Evaluation-Composant-N2) dépendent du type d'évaluation (code) véhiculé dans l'entrée FR-Evaluation :

| | | | |
| :--- | :--- | :--- | :--- |
| Evaluation AGGIR PH SSIAD | Valeur issue du JDV_EvaluationAGGIRPH_CISISL'attribut nullFlavor est interdit | CDValeur issue du JDV_ResultatEvaluation_CISISL’attribut nullFlavor est autorisé | Chaque champ évalué doit être détaillé selon 4 critères : [4..4] |
| Evaluation AGGIR PA SSIAD | Valeur issue du JDV_EvaluationAGGIRPA_CISISL'attribut nullFlavor est interdit | CDValeur issue du JDV_ResultatEvaluation_CISISL’attribut nullFlavor est autorisé | Chaque champ évalué doit être détaillé selon 4 critères : [4..4] |
| Evaluation de la situation SSIAD | Valeur issue du JDV_EvaluationSSIAD_CISISL'attribut nullFlavor est interdit. | BL | [0..0] |
| Evaluation SERAFIN | Valeur issue du JDV_J285-Besoins_SERAFINL'attribut nullFlavor est interdit. | INT | [0..0] |

##### Entrée FR-Evaluation-Composant-N2

L'entrée FR-Evaluation-Composant-N2 permet d’associer à un champ évalué le résultat détaillé de l’évaluation.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.220-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Evaluation-Composant-N2" height="400"></iframe>
Lien vers le template : [FR-Evaluation-Composant-N2](./cda/tmp-1.2.250.1.213.1.1.3.220-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Evaluation-Composant-N2 :**

Le critère évalué (code) et le type de résultat de ce critère évalué (value) dépendent du type d’évaluation (code) véhiculé dans l’entrée FR-Evaluation :

| | | |
| :--- | :--- | :--- |
| Evaluation AGGIR PH SSIAD | Valeur issue du JDV_ResultatQuestionEvaluation_CISISL'attribut nullFlavor est interdit. | BL |
| Evaluation AGGIR PA SSIAD | Valeur issue du JDV_ResultatQuestionEvaluation_CISISL'attribut nullFlavor est interdit. | BL |

### Section FR-Documents-ajoutes

La section FR-Documents-ajoutes permet d’ajouter les documents ou pièces jointes qui sont spécifiques à ce volet.

La structure de la section se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.2.37-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Documents-ajoutes" height="400"></iframe>
Lien vers le template : [FR-Documents-ajoutes](./cda/tmp-1.2.250.1.213.1.1.2.37-DYNAMIC.md)

#### Entrée FR-Document-attache

L'entrée FR-Document-attache permet de regrouper dans une même entrée un élément qui porte le document attaché ainsi qu'une entrée définissant la nature du document attaché.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.18-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Document-attache" height="400"></iframe>
Lien vers le template : [FR-Document-attache](./cda/tmp-1.2.250.1.213.1.1.3.18-DYNAMIC.md)

#### Entrée FR-Type-document-attache

L'entrée FR-Type-document-attache définit le type de document attaché.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.48.18-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Type-document-attache" height="400"></iframe>
Lien vers le template : [FR-Type-document-attache](./cda/tmp-1.2.250.1.213.1.1.3.48.18-DYNAMIC.md)

### Eléments transversaux

#### Entrée FR-Statut

L’entrée FR-Statut permet de décrire et de suivre le statut métier d'un objet.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.217-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Statut" height="400"></iframe>
Lien vers le template : [FR-Statut](./cda/tmp-1.2.250.1.213.1.1.3.217-DYNAMIC.md)

**Contraintes spécifiques à l'entrée FR-Statut :**

| | | |
| :--- | :--- | :--- |
| value | [1..1] | **Statut métier**Valeur issue du JDV_J281-StatutsRessourcesMS |
| value[@code="ANNULE"]/qualifier/value | [1..1] | **Motif associé au statut de non-réalisation de l’évènement**Lorsque le statut est à "Annulé", le motif est issu du JDV_MotifNonRealisationEvenement_CISIS. |

#### Entrée FR-Simple-Observation

L’entrée FR-Simple-Observation est un élément générique permettant de décrire les caractéristiques d'un objet.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.48-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Simple-Observation" height="400"></iframe>
Lien vers le template : [FR-Simple-Observation](./cda/tmp-1.2.250.1.213.1.1.3.48-DYNAMIC.md)

#### Entrée FR-Commentaire-ER

L’entrée FR-Commentaire-ER est un élément qui permet de joindre un commentaire à une entrée ou à une section.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.32-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Commentaire-ER" height="400"></iframe>
Lien vers le template : [FR-Commentaire-ER](./cda/tmp-1.2.250.1.213.1.1.3.32-DYNAMIC.md)

#### Entrée FR-Reference-interne

L’entrée FR-Reference-interne permet de relier un élément à un autre élément du même document par l’intermédiaire son identifiant.

La structure de l'entrée se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.36-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Reference-interne" height="400"></iframe>
Lien vers le template : [FR-Reference-interne](./cda/tmp-1.2.250.1.213.1.1.3.36-DYNAMIC.md)

#### Elément FR-Participant

L'élément FR-Participant permet de décrire un participant dans une section ou une entrée.

La structure de l'élément se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.3.109-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Participant" height="400"></iframe>
Lien vers le template : [FR-Participant](./cda/tmp-1.2.250.1.213.1.1.3.109-DYNAMIC.md)

#### Elément FR-Performer

L'élément FR-Performer permet de décrire une personne ayant exécuté un acte.

La structure de l'élément se conforme aux contraintes et définitions présentées dans les **Modèles de contenus CDA** :

<iframe src="./cda/tmp-1.2.250.1.213.1.1.1.99.99.10.85-DYNAMIC.html" sandbox="allow-same-origin allow-scripts" style="border: 1px solid black" id="FR-Performer" height="400"></iframe>
Lien vers le template : [FR-Performer](./cda/tmp-1.2.250.1.213.1.1.1.99.99.10.85-DYNAMIC.md)

**Contrainte spécifique à l'élément FR-Performer :**

Certains rôles du professionnel sont à véhiculer en utilisant conjointement les éléments sdtc:functionCode et assignedEntity/code :

| | | |
| :--- | :--- | :--- |
| Infirmier coordinateur (IDEC) | @code = "330"@displayName = "Coordonnateur de parcours"@codeSystem = "1.2.250.1.213.1.6.1.107" | @code = "G15_60"@displayName = "Infirmier"@codeSystem = "1.2.250.1.213.1.1.4.5" |


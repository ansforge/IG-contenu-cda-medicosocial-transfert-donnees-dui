# Evaluation - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Evaluation**

## Evaluation

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


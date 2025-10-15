# Sejour - Médicosocial - Transfert de données DUI CDA v1.0.1

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Sejour**

## Sejour

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


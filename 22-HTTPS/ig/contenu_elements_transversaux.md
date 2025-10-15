# Eléments transversaux - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Contenu du dossier CDA**](contenu_dossier.md)
* **Eléments transversaux**

## Eléments transversaux

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


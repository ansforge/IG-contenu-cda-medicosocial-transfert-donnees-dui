# Ressources FHIR - Médicosocial - Transfert de données DUI CDA v1.0.1

* [**Table of Contents**](toc.md)
* [**Ressources de conformité**](ressources_conformite.md)
* **Ressources FHIR**

## Ressources FHIR

This page provides a list of the FHIR artifacts defined as part of this implementation guide.

### Behavior: Capability Statements 

The following artifacts define the specific capabilities that different types of systems are expected to have in order to comply with this implementation guide. Systems conforming to this implementation guide are expected to declare conformance to one or more of the following capability statements.

| | |
| :--- | :--- |
| [TDDUI-Consommateur](CapabilityStatement-TDDUIConsommateur.md) | Le rôle du consommateur est de recueillir les données du Dossier Usager Informatisé. Il peut recevoir un unique dossier ou un ensemble de dossiers, ainsi que des mises à jour de dossiers. Il correspond à un logiciel DUI ou un SI tiers. |
| [TDDUI-Producteur](CapabilityStatement-TDDUIProducteur.md) | Le rôle du producteur est de créer et transmettre un document ou lots de Documents portant les informations du Dossier Usager Informatisé. Il correspond à un logiciel DUI. |

### Structures: Resource Profiles 

These define constraints on FHIR resources for systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [TDDUI Bundle](StructureDefinition-tddui-bundle.md) | Profil générique créé dans le contexte du transfert de données DUI pour véhiculer un lot de documents au format CDA. |
| [TDDUI Document Reference](StructureDefinition-tddui-documentreference.md) | Profil générique créé dans le contexte du transfert de données DUI pour véhiculer un document au format CDA, inclus dans DocumentReference.attachment.data. |

### Example: Example Instances 

These are example instances that show what data produced and consumed by systems conforming with this implementation guide might look like.

| | |
| :--- | :--- |
| [TDDUIBundleExample](Bundle-TDDUIBundleExample.md) | Exemple de ressource Bundle suivant le profil TDDUIBundle |
| [TDDUIDocumentReferenceExample](DocumentReference-TDDUIDocumentReferenceExample.md) | Exemple de ressource DocumentReference suivant le profil TDDUIDocumentReference |


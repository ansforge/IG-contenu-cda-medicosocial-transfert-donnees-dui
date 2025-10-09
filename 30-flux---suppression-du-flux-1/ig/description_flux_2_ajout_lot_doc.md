# Flux 2 - Ajout d'un lot de documents - Médicosocial - Transfert de données DUI CDA v1.0.0

* [**Table of Contents**](toc.md)
* [**Description des flux FHIR**](description_flux.md)
* **Flux 2 - Ajout d'un lot de documents**

## Flux 2 - Ajout d'un lot de documents

Ce flux permet l'ajout d'un lot de documents.

### Flux 1.1 AjoutLotDocuments

L'ajout d'un lot de documents est assuré par l'interaction FHIR [transaction](https://hl7.org/fhir/R4/http.html#transaction). L'émetteur du lot de documents envoie une requête HTTP POST dont le corps contient une ressource de type Bundle conforme au profil [DUIBundle](StructureDefinition-tddui-bundle.md) :

`POST [base]`

Où `[base]` est le point de contact FHIR.

Le bundle contient plusieurs ressources DocumentReference conformes au profil "DUIDocumentReference" véhiculées via `Bundle.entry.ressource`, chacune contenant un document au format CDA.

### Flux 1.2 ResultatAjoutLotDocuments

Si la création des ressources DocumentReference est correctement effectuée, le récepteur doit retourner un code HTTPS 200 « OK » avec, dans le corps de la réponse, une ressource « Bundle » de type « transaction-response ». Chaque entrée (entry) du Bundle doit comporter un élément « response » qui contient le statut de l’opération.

En cas d’échec, le récepteur doit répondre avec le code HTTPS approprié tel que défini par l’API REST FHIR [(Http - FHIR v4.0.1 (hl7.org))](http://hl7.org/fhir/R4/http.html). Une ressource OperationOutcome doit également y être associé pour véhiculer les messages d’erreurs détaillant la raison de l’erreur [(OperationOutcome - FHIR v4.0.1 (hl7.org))](http://hl7.org/fhir/R4/operationoutcome.html).


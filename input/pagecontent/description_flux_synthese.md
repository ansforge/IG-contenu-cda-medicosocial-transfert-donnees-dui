<table style="width:100%">
  <tr>
    <th>Processus métier</th>
    <th>Flux techniques</th>
  </tr>
  <tr>
    <td rowspan="2">
      <ul>
      <li>Transférer les données d’un logiciel DUI vers un SI tiers</li>
      </ul>
    </td>
    <td>
      <ul>
      <li>Flux 1.1 - Ajout d'un document : interaction « create » de FHIR</li>
      <li>Flux 1.2 - Résultat de l'ajout d'un document : réponse à la requête HTTP POST</li>
      </ul>
      {%include flux1.svg%} <br>
      Lien vers la description détaillée : <a href="description_flux_1_ajout_doc.html">flux 1</a>
    </td>
  </tr>
  <tr>
    <td>
      <ul>
      <li>Flux 2.1 - Ajout d'un lot de documents : interaction « transaction » de FHIR</li>
      <li>Flux 2.2 - Résultat de l'ajout d'un lots documents : réponse à la requête HTTP POST</li>
      </ul>
      {%include flux2.svg%} <br>
      Lien vers la description détaillée : <a href="description_flux_2_ajout_lot_doc.html">flux 2</a>
    </td>
  </tr>
  
</table>
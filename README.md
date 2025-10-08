<section id="sechoir-solaire">
  <h2>Excel — Analyse thermique et modélisation de la propagation de la chaleur dans un séchoir solaire</h2>

  <h3>Résumé / Phrase d’accroche</h3>
  <p>
    Modélisation numérique et analyse expérimentale d’un séchoir solaire indirect (capteur + stockage sur lit de cailloux) 
    pour évaluer et optimiser la propagation de la chaleur et les performances de séchage. 
    Le travail combine bilans thermiques, simulations Excel/VBA et essais expérimentaux sur prototype.
  </p>

  <h3>Objectif du projet</h3>
  <p>
    L’objectif principal était d’évaluer l’efficacité thermique du dispositif (capteur solaire + stockage thermique) 
    en construisant un modèle numérique sous Excel capable d’estimer l’évolution des températures en fonction de paramètres 
    clefs (irradiance, débit d’air, propriétés des matériaux) et de valider ce modèle par des mesures expérimentales sur 
    prototype instrumenté. 
  </p>
  <p>
    Le livrable devait fournir un outil interactif pour simuler différents scénarios et proposer des pistes d’amélioration 
    (inertie du stockage, coefficients d’échange thermique, etc.).
  </p>

  <h3>Démarche (étapes principales)</h3>
  <h4>1. Définition des bilans thermiques</h4>
  <p>
    Établissement des bilans pour chaque élément : absorbeur, vitre, lames d’air, bois/structure et stockage. 
    Ces bilans gouvernent les équations à résoudre pour obtenir <em>Tab, Tv, Ts1, Ts2, Tb</em>, etc.
  </p>

  <h4>2. Construction du modèle numérique sous Excel & VBA</h4>
  <ul>
    <li>Discrétisation longitudinale du capteur en 10 segments (10 pas de calcul).</li>
    <li>Chaque pas est implémenté dans une feuille Excel distincte (paramètres, données fixes, résultats).</li>
    <li>Formulation du système linéaire <strong>AX = B</strong> (5 équations / segment) et résolution par inversion matricielle <strong>X = A⁻¹B</strong>.</li>
    <li>Automatisation et itération des calculs via macros VBA (boucles, mises à jour dynamiques).</li>
  </ul>

  <h4>3. Modélisation du stockage thermique</h4>
  <p>
    Étude et implémentation d’un modèle inspiré de <strong>Salifou Tera</strong> pour le stockage thermique 
    (équation d’énergie, Euler implicite, résolution itérative type Jacobi). 
    Adaptation du modèle à l’air comme fluide caloporteur (au lieu de l’eau dans les modèles de référence).
  </p>

  <h4>4. Instrumentation et campagne expérimentale</h4>
  <p>
    Instrumentation du prototype : thermocouples (TC 20, 21, 22, 32), anémomètres, pyranomètres. 
    Tests réalisés sur banc d’ensoleillement artificiel (11 lampes), ventilateurs (V1, V2, V3) 
    et cycles charge/décharge (ex. 08:00 → 16:00 → 08:00). 
    Mesures de poids sur échantillons pour évaluer le séchage.
  </p>

  <h4>5. Comparaison modèle / expérimentation et ajustements</h4>
  <p>
    Comparaison systématique des profils de température simulés et mesurés, identification des écarts 
    et propositions d’amélioration (régime transitoire, recalibration des coefficients d’échange, 
    vérification des propriétés matériaux).
  </p>

  <h3>Résultats clés (synthèse)</h3>
  <ul>
    <li>Le modèle Excel/VBA reproduit la tendance générale des profils de température le long du capteur.</li>
    <li>Étude de l’impact de l’irradiance et du débit d’air sur la température de sortie du capteur.</li>
    <li>
      Exemple : pour le 05/03/2024 (débit d’air 0,03 m³/s), la température mesurée ≈ 78 °C 
      contre ≈ 51 °C simulée — l’écart a permis d’identifier les limites du modèle.
    </li>
    <li>
      Simulations : augmentation de l’irradiance → hausse générale des températures ; 
      augmentation du débit d’air → diminution du gradient entrée/sortie.
    </li>
    <li>
      Campagnes expérimentales : séchage plus efficace à 12 V qu’à 10 V ; durée optimale ≈ 24 h.
    </li>
  </ul>

  <h3>Limites identifiées et recommandations</h3>
  <ul>
    <li>Intégrer un régime transitoire pour représenter la montée en température (essais ≈ 1 h).</li>
    <li>Recalibrer les coefficients d’échange convectifs/radiatifs (Nusselt, h) selon les mesures et la littérature.</li>
    <li>Fiabiliser la chaîne d’acquisition (RIGOL SIGMA / logiciel) – certains problèmes d’installation ont été signalés.</li>
    <li>Corriger le code VBA (bug sur la mise à jour de colonnes) et documenter les feuilles Excel pour la reproductibilité.</li>
  </ul>

  <h3>Compétences mobilisées</h3>
  <ul>
    <li>Modélisation thermique et bilans énergétiques.</li>
    <li>Transferts de chaleur : conduction, convection, rayonnement.</li>
    <li>Méthodes numériques : discrétisation, résolution de systèmes linéaires, Euler implicite, itérations.</li>
    <li>Programmation VBA et automatisation Excel.</li>
    <li>Instrumentation expérimentale et protocole d’essai.</li>
    <li>Analyse et validation modèle/mesures, interprétation des données expérimentales.</li>
  </ul>

  <h3>Languages and Utilities Used</h3>
  <ul>
    <li><strong>Langages / scripts :</strong> VBA (macros Excel), formules Excel avancées, scripts de post-traitement.</li>
    <li><strong>Utilitaires / instruments :</strong> Microsoft Excel (10 feuilles), RIGOL (acquisition), thermocouples, anémomètres, pyranomètre, banc d’éclairage (11 lampes halogènes).</li>
  </ul>

  <h3>Environments Used</h3>
  <p>
    Poste de travail avec Microsoft Excel (Windows / macOS compatible), environnement de tests en laboratoire 
    (banc d’ensoleillement artificiel, ventilateurs, instrumentation), logiciels d’acquisition RIGOL.
  </p>

  <h3>Fichiers & documentation</h3>
  <p>
    La description complète, les annexes techniques (thermocouples, protocole), le code VBA et les feuilles Excel 
    sont disponibles dans le rapport de projet fourni. 
    <br>
    <a href="#" target="_blank">📄 Consulter le rapport complet : Rapport PRD séchoir solaire</a>
  </p>
</section>

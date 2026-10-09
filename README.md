# MBE Bihorel — concept de refonte

Maquette de refonte du site du Centre MBE 3481 (Bihorel, Rouen Nord), proposée par Kréalabs.
**Concept non contractuel** : ce n'est pas le site officiel du réseau Mail Boxes Etc.

## Contenu

Une seule page, `index.html` : HTML, CSS et JS inline, sans build. Three.js r128 est chargé depuis cdnjs et les polices depuis Google Fonts.

| Section | Technique |
|---|---|
| Écran de chargement | Cube CSS 3D |
| Fond fixe sur toute la page | Three.js : la caméra suit une route 3D (tube, portiques, ~400 cartons instanciés) au fil du scroll global, et un colis guide l'accompagne |
| Hero | Three.js épinglé sur 360vh : le carton s'ouvre et les objets en sortent |
| Le voyage d'un colis | Three.js épinglé sur 640vh, entièrement piloté par le scroll : montage du carton à plat, calage (bouteille, cadeau, papier bulle), fermeture et scotch, étiquette, tampon et scan, enlèvement par avion |
| Destinations | Globe Three.js épinglé : la zone (Tout / France / Europe / International) change avec le scroll, avec routes animées et étiquettes projetées |
| Envois spéciaux | Carrousel CSS 3D épinglé, rotation pilotée par le scroll |
| Simulateur | Carton CSS 3D redimensionnable, calcul du poids volumétrique et mail de devis pré-rempli |
| Impression / domiciliation | Éventail CSS 3D et carte qui se retourne |
| Avis, FAQ, contact | Avis Google (extraits verbatim), horaires avec statut ouvert/fermé à l'heure de Paris |
| Final | Three.js : pluie de cartons qui s'empilent |

Chaque scène WebGL ne s'affiche que lorsqu'elle est visible. Le fond fixe se coupe quand une section opaque (voyage, final) couvre l'écran.

## Lancer en local

```bash
npx serve .            # ou : python3 -m http.server
```

Ouvrir directement `index.html` dans le navigateur fonctionne aussi.

## Déploiement

Le site est statique : GitHub Pages (branche `main`, racine), Coolify (static site) ou n'importe quel hébergement de fichiers.

## À valider avec le centre avant diffusion

- Les phrases qui ne viennent pas de leur page actuelle : « 5 grands transporteurs », les réponses de la FAQ (assurance, douanes, domiciliation) et le diviseur 5000 du simulateur.
- Les 22 villes du globe, qui sont des exemples d'illustration.
- L'usage de la marque MBE sur un site local, soumis à la charte du franchiseur.
- Les performances sur mobile d'entrée de gamme, à tester sur un vrai appareil.

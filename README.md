# Contexte — Veille BIM & Construction Numérique Québec

## À coller en début de nouvelle conversation

> "Je suis gestionnaire BIM pour un entrepreneur général au Québec. J'ai une page HTML de veille BIM partagée sur Google Drive avec mon équipe. Peux-tu faire une mise à jour mensuelle du fichier ? Le fichier s'appelle `veille_bim_quebec.html`. Voici le contexte complet ci-dessous."

---

## Ce qu'est le fichier

Une page HTML autonome (aucun serveur, aucune dépendance externe) déposée sur un Google Drive partagé avec l'équipe. Elle s'ouvre directement dans un navigateur.

**Fonctionnalités :**
- Vue liste et vue calendrier (bascule en haut à droite)
- Filtres : type d'événement, format (virtuel / présentiel / hybride), coût (gratuit / payant)
- Barre de recherche par mot-clé
- Bouton "+ Calendrier" sur chaque événement → ouvre Google Calendar
- Fiche détaillée au clic sur un événement
- Statistiques en en-tête (total, prochains 30 jours, en ligne, gratuits)
- Bannière dorée automatique si les données ont plus de 30 jours
- **Les événements passés disparaissent automatiquement** à chaque ouverture (filtrage par `dateFin < aujourd'hui`)

---

## Ce que fait Claude à chaque mise à jour

1. Faire une recherche web sur les événements BIM et construction numérique au Québec/Canada pour les prochains mois
2. Remplacer le bloc `const EVENTS = [...]` dans le fichier HTML
3. Mettre à jour `const DATA_DATE` à la date du jour
4. **Ne garder que les événements dont la date est dans le futur** (le filtrage est automatique, mais les données passées n'ont pas à être incluses)
5. Fournir le fichier `.html` mis à jour à télécharger et redéposer sur le Drive

---

## Organisations à surveiller en priorité

- Groupe BIM du Québec → bimquebec.org/evenements
- Bâtiment numérique Québec → batimentnumerique.ca
- BuildingSMART Canada → buildingsmartcanada.ca
- Building Transformations Canada → buildingtransformations.ca
- Revizto → revizto.com/fr/events/
- Autodesk University → autodesk.com/events
- Grands Bâtisseurs → grandsbatisseurs.com
- AEQ (Association des entrepreneurs en construction du Québec) → aeq.ca

---

## Types d'événements à inclure

| Valeur dans le code | Libellé affiché |
|---|---|
| `conference` | Conférence / colloque |
| `webinaire` | Webinaire |
| `formation` | Formation |
| `norme` | Appel de commentaires / Norme |
| `outil` | Outil / Logiciel |
| `autre` | Autre |

---

## Format de chaque événement dans le code

```js
{
  id: "evt01",                          // identifiant unique, incrémenter
  titre: "Nom de l'événement",
  organisateur: "Nom de l'organisme",
  type: "conference",                   // voir tableau ci-dessus
  format: "hybride",                    // virtuel | presentiel | hybride
  cout: "gratuit",                      // gratuit | payant
  dateDebut: "2026-06-18",             // format YYYY-MM-DD
  dateFin: "2026-06-18",               // même date si 1 jour
  heure: "17h30 – 19h30",             // string ou null
  lieu: "Montréal (ÉTS) + En ligne",
  description: "2-3 phrases max.",
  lienInscription: "https://...",      // ou null
  lienInfo: "https://..."              // ou null
}
```

---

## État actuel des données

- **Dernière mise à jour :** 5 mai 2026
- **Année couverte :** 2026
- **Nombre d'événements :** 17

### Événements confirmés dans le fichier actuel

| Date | Événement | Organisateur | Type | Format |
|---|---|---|---|---|
| 18 mars 2026 | Salon de l'emploi SETC 2026 | Groupe BIM du Québec | Conférence | Présentiel |
| 30 mars–3 avr. 2026 | Mission BIM World Paris 2026 | Groupe BIM QC / CCMM | Conférence | Présentiel |
| 7–9 avr. 2026 | buildingSMART International Summit — Printemps | buildingSMART Intl | Conférence | Hybride |
| 21 avr. 2026 | AGA 2026 — Groupe BIM du Québec | Groupe BIM du Québec | Autre | Hybride |
| 21 avr. 2026 | Soirée-conférence : IA appliquée à la gestion de projet | Groupe BIM du Québec | Conférence | Hybride |
| 21 mai 2026 | Conférence : Le scan 3D — technologies et usages | Groupe BIM du Québec | Conférence | Hybride |
| 28 mai 2026 | Webinaire Revizto : coordination BIM et suivi de chantier | Revizto | Webinaire | Virtuel |
| 15 juin 2026 | Feuille de route BIM Québec — Bilan post-2026 | SQI | Norme | Virtuel |
| 18 juin 2026 | Conférence Groupe BIM du Québec — Juin | Groupe BIM du Québec | Conférence | Hybride |
| 20 août 2026 | Webinaire Revizto : introduction pour entrepreneurs | Revizto | Webinaire | Virtuel |
| 17 sept. 2026 | Conférence Groupe BIM du Québec — Septembre | Groupe BIM du Québec | Conférence | Hybride |
| 24 sept. 2026 | AEQ — Journée de l'innovation en construction | AEQ | Conférence | Présentiel |
| 28–30 sept. 2026 | buildingSMART International Summit — Automne | buildingSMART Intl | Conférence | Hybride |
| 5–8 oct. 2026 | Autodesk University 2026 | Autodesk | Conférence | Présentiel |
| 21–22 oct. 2026 | Building Transformations Canada 2026 | BTC | Conférence | Hybride |
| 4–5 nov. 2026 | Grands Bâtisseurs — Forum annuel | Grands Bâtisseurs | Conférence | Présentiel |
| 18 nov. 2026 | Conférence Groupe BIM du Québec — Novembre | Groupe BIM du Québec | Conférence | Hybride |

---

## Instruction rapide pour Claude lors d'une mise à jour

```
Mets à jour le fichier veille_bim_quebec.html avec les événements BIM 
et construction numérique au Québec/Canada à venir. 
Fais une recherche web sur les organisations listées dans le contexte, 
remplace le bloc EVENTS avec les événements futurs trouvés, 
mets DATA_DATE à aujourd'hui, et fournis le fichier HTML complet.
```

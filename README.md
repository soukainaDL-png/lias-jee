# LIAS – Gestion du laboratoire (Spring Boot 3 / JPA / JWT)

Lancer : ouvrir le dossier `lias` dans IntelliJ, lancer `LiasApplication`, puis http://localhost:8080/
Console H2 : /h2-console (JDBC URL jdbc:h2:file:./data/lias, user sa, mot de passe vide)

Comptes de test (mot de passe : password123) :
- karim.bennani@lias.ma   (directeur)
- nadia.elfassi@lias.ma   (vice-directrice)
- youssef.idrissi@lias.ma (chef d'équipe)
- sara.alaoui@lias.ma     (doctorante — accès limité, voir plus bas)
- ahmed.tazi@lias.ma      (retraité : connexion refusée, compte gelé)

## Répartition des accès (§2 du cahier des charges)
- Visiteurs (non connectés) : présentation, événements, publications, formulaire d'adhésion.
- Tout membre connecté et actif (y compris associés et doctorants) : son profil (modifiable),
  l'annuaire, le calendrier, ses notifications, la consultation/ajout de publications.
- Membres permanents + gouvernance + administrateur système uniquement : les modules internes
  (documents & archives, matériel, conventions & partenaires, réunions & PV, discussions) —
  un doctorant ou un associé ne les voit pas dans le menu et ne peut pas y accéder par l'API.
- Direction (directeur/vice-directeur) : demandes d'adhésion, mandats & rôles, gestion du matériel,
  validation du rapport annuel.
- Administrateur système : gestion technique des comptes (activation/désactivation, réinitialisation
  de mot de passe), en plus de tout ce que peut faire un membre permanent.

## Modules réalisés
Profils et statuts, historique des affiliations, mandats et rôles historisés, demandes d'adhésion
avec activation de compte par jeton, retraite/ancien membre, événements, publications, rapport annuel
(avec validation et export PDF), archivage documentaire (upload/téléchargement, suppression réversible),
matériel et besoins (avec répartition équitable automatique), conventions & partenaires, réunions & PV,
communication interne (par équipe et par événement), notifications, recherche globale, calendrier,
authentification JWT, gestion technique des comptes.

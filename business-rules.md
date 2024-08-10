# RÈGLES DE GESTION

## Lexique

**Formation** : Un ensemble de Modules avec un objectif pédagogique défini. L'ordre des Modules est défini par un système de Semantic Versioning.

**Module** : Un ensemble de Leçons avec un objectif pédagogique défini. Un Module concerne un sujet précis.

**Leçon** : Une plus petite unité qui compose un Module (semblable à un chapitre).

**Tag** : Une catégorie ou un sujet abordé dans la Formation ou le Module. Permet de filtrer plus facilement.

**Auteur** : Formateur qui a écrit une Leçon.

**Utilisateur** : Groupe général dont découlent tous les autres acteurs.

- **Apprenant** : Utilisateur qui veut suivre une Formation.

- **Formateur** : Utilisateur qui peut suivre ou créer des Formations, Modules et Leçons.

- **Formateur référent** : Rôle attribué à certains Formateurs, leur permettant de publier et modifier des Formations attribuées.

- **Super Administrateur** : Utilisateur en charge des Administrateurs.

- **Administrateur** : Utilisateur en charge des Transactions, des Formateurs Référents et des divers aspects administratifs.

**Inscription** : Processus liant un Apprenant à une Formation.

**Transaction** : Informations concernant le paiement d'une Formation.

## 1. Formations

- Une Formation doit avoir un intitulé unique.
- Une Formation doit avoir une langue, choisie parmi une liste prédéfinie.
- Une Formation doit avoir un prix. Cela peut être un montant ou `gratuit`.
- Une Formation doit avoir une description.
  - La description d'une Formation doit comporter les objectifs / compétences à atteindre.
  - La description peut suggérer des Formations pré-requises.
- Une Formation doit avoir une date de création ou de mise à jour.
- Une Formation doit avoir une durée estimée, correspondant à l'addition des durées de tous ses Modules.
- Une Formation est composée d'un ou plusieurs Modules.
- Une Formation appartient à un ou plusieurs Formateurs.
- Une Formation peut avoir 0 ou plusieurs Apprenants.
- Une Formation peut avoir 3 états : `Brouillon`, `Publiée` ou `Archivée`.
- Une Formation est considérée comme terminée lorsque tous ses Modules sont validés par l'Apprenant.
- Une Formation ne peut pas être supprimée.
- Une Formation peut avoir un ou plusieurs Tags.
- Une Formation peut offrir une preuve de complétion à l'Apprenant une fois validée.
- Une Formation est composée de Modules
  - Les Modules ont un ordre spécifique défini pour cette Formation.

## 2. Modules

- Un Module doit avoir un intitulé unique.
- Un Module doit avoir une langue, choisie parmi une liste prédéfinie.
- Un Module ne peut appartenir qu'à une Formation dans la même langue.
- Un Module doit avoir une description.
  - La description d'un Module doit mentionner une durée estimée.
  - La description d'un Module doit mentionner un ou plusieurs objectifs d'apprentissage.
- Un Module doit avoir une date de création ou de mise à jour.
- Un Module a pour Auteur(s) un ou plusieurs Formateurs.
- Un Module peut faire partie d'une ou plusieurs Formations.
- Un Module peut avoir 3 états : `Brouillon`, `Publié` ou `Archivé`.
- L'état du Module est changé automatiquement pour refléter celui de la Formation dont il fait partie.
- Un Module est considéré comme validé lorsque toutes ses leçons ont été terminées par l'Apprenant.
- Un Module peut avoir un ou plusieurs Tags.
- Un Module est composé d'une ou plusieurs Leçons.
  - Les Leçons ont un ordre spécifique défini pour ce Module.

## 3. Leçons

- Une Leçon doit avoir un intitulé unique.
- Une Leçon doit avoir une langue, choisie parmi une liste prédéfinie.
- Une Leçon ne peut appartenir qu'à un Module dans la même langue.
- Une Leçon doit avoir une description.
- Une Leçon a pour Auteur un Formateur unique.
- Une Leçon doit avoir au moins un contenu textuel (paragraphe).
- Une Leçon doit avoir au moins une image.
- Une Leçon doit avoir au moins une vidéo.
- Une Leçon doit avoir une date de création ou de mise à jour.
- Une Leçon peut faire partie d'un ou plusieurs Modules.
- Une Leçon peut être suivie par 0 ou plusieurs Apprenants.
- Une Leçon peut être validée directement par un Apprenant.
- Une Leçon validée dans un Module doit être à nouveau validée si elle est rencontrée dans un autre Module.

## 4. Tags

- Un Tag doit avoir un nom unique.
- Un Tag peut être associé à une ou plusieurs Formations ou Modules.
- Les Tags peuvent être ajoutés à partir d'une liste prédéfinie.
- Un Tag peut être créé par un Administrateur ou un Formateur référent.
- Un Tag peut être modifié ou supprimé par un Administrateur.
- Un Tag ne doit pas être supprimé s'il est associé à une Formation, un Module ou une Leçon ayant l'état `Publié`.
- Un Tag peut être utilisé pour faciliter la recherche et le filtrage des contenus sur la plateforme.

## 5. Utilisateurs

- Un Utilisateur doit avoir un UUID.
- Un Utilisateur doit avoir une adresse mail.
- Un Utilisateur doit avoir un nom.
- Un Utilisateur doit avoir un prénom.
- Un Utilisateur doit avoir une adresse postale.
- Un Utilisateur doit avoir une date de naissance.

## 6. Apprenants

- Un Apprenant a un Code Apprenant unique, attribué automatiquement.
- Un Apprenant peut s'inscrire à une ou plusieurs Formations.
- Un Apprenant peut valider 0 ou plusieurs Leçons.
  - Un Module est complété en validant toutes les Leçons de celui-ci.
  - Une Formation est terminée en complétant tous les Modules de celle-ci.
- Un Apprenant peut consulter son historique de Formation et les certificats de complétion obtenus.
- Un Apprenant peut demander la suppression de son compte, ce qui entraîne la suppression de ses données personnelles conformément au RGPD.

## 7. Formateurs

- Un Formateur a un Code Formateur unique, attribué automatiquement.
- Un Formateur peut créer des Leçons.
  - Un Formateur peut modifier les Leçons qu'il a créées.
- Un Formateur peut créer des Modules en assemblant plusieurs Leçons, qu’il a créées ou qui ont été créées par d'autres Formateurs.
  - Un Formateur peut modifier les Modules qu'il a créés en ajoutant, supprimant (archivage) ou réorganisant des Leçons.
- Un Formateur peut créer des Formations en assemblant plusieurs Modules.
  - Un Formateur peut modifier les Formations qu'il a créées en ajoutant, supprimant (archivage) ou réorganisant des Modules.
- Un Formateur peut associer des Tags à une Formation, un Module, ou une Leçon, à partir d'une liste prédéfinie.
- Un Formateur peut demander la suppression de son compte, ce qui entraîne la suppression de ses données personnelles et l'archivage des Formations, Modules, et Leçons qu'il a créés, conformément au RGPD.
- Un Formateur peut consulter l’historique des Formations, Modules, et Leçons qu'il a créés, ainsi que les statistiques d’utilisation par les Apprenants.

### Rôle de Formateur Référent

- Un Formateur peut être promu au rôle de Formateur Référent par un Administrateur.
- Un Formateur Référent peut se voir attribuer des Formations à l'état `Brouillon` ou `Publiée`
- Un Formateur Référent peut :
  - publier,
  - archiver,
  - modifier
une Formation qui lui est attribuée.
- Un Formateur Référent peut modifier des Modules dont il n'est pas l'auteur, à condition qu'ils fassent partie d'une Formation qui lui est attribuée.
- Un Formateur Référent peut créer de nouveaux Tags.

## 8. Super Administrateurs

- Un Super Administrateur peut :
  - créer,
  - modifier,
  - suspendre,
  - supprimer
des comptes Administrateurs.

## 9. Administrateurs

- Un Administrateur peut créer et modifier des comptes Utilisateurs.
- Un Administrateur peut promouvoir un Formateur au rôle de Formateur Référent.
- Un Administrateur peut désactiver temporairement un compte Utilisateur pour des raisons de sécurité ou de non-respect des conditions d’utilisation.
- Un Administrateur peut consulter et gérer les Transactions.
  - Un Administrateur est notifié lorsqu'un paiement est reçu, afin de confirmer manuellement l'inscription de l'Apprenant concerné.
- Un Administrateur peut superviser les Inscriptions des Apprenants.
- Un Administrateur peut accéder à des statistiques globales sur l’utilisation de la plateforme (taux d’inscription, taux de complétion, etc.).
- Un Administrateur peut générer des rapports personnalisés sur les activités de la plateforme.

## 10. Inscriptions

- Une Inscription lie un Apprenant à une Formation spécifique.
- Une Inscription doit inclure une date d’inscription.
- Une Inscription peut avoir 4 états : `En attente de paiement`, `Paiement effectué`, `Inscription confirmée` et `Annulée`.
  - Si la Formation est gratuite, le statut de l'Inscription passe automatiquement à `Inscription confirmée`.
  - Si la Formation est payante, le statut de l'Inscription passe automatiquement à `En attente de paiement`.
  - Lorsqu'un paiement est effectué, le statut de l'Inscription passe automatiquement à `Paiement effectué`.
  - Lorsqu'un paiement est reçu, l'Administrateur peut changer manuellement le statut l'Inscription à `Inscription confirmée`.
  - Une `Inscription confirmée` débloque le contenu d'une Formation pour l'Apprenant.
  - Une Inscription peut être `Annulée` avant le paiement par l'Apprenant ou l'Administrateur.
  - Une Inscription ne peut pas être `Annulée` une fois que la Formation a commencé.

## 11. Transactions

- Une Transaction est liée à une Inscription spécifique.
- Une Transaction doit avoir un montant correspondant au prix de la formation (ou 0 si la formation est gratuite).
- Une Transaction doit inclure une date de transaction.
- Une Transaction doit inclure le moyen de paiement utilisé (carte de crédit, PayPal, etc.).
- Une Transaction peut avoir 4 statuts : `Complétée`, `En attente`, `En cours`, `Échouée`.
  - Une Transaction est automatiquement créée lors du processus de paiement dans une inscription spécifique. Elle a alors le statut `En attente` par défaut.
  - Lorsque le paiement est effectué, le statut de la Transaction passe à `En cours`.
  - Si le paiement échoue (fonds insuffisant, interruption du processus de paiement), la Transaction passe au statut `Échouée` et ne peut plus être modifiée. Une nouvelle Transaction doit être créée pour effectuer un autre paiement.
  - Lorsque le paiement est reçu, la Transaction passe au statut `Complétée` et une notification est envoyée automatiquement à l'Administrateur.
- Une Inscription peut être liée à une ou plusieurs Transactions si des paiements échelonnés sont autorisés.

### Détail du processus d'inscription et de paiement

**1.** Lorsqu'un Apprenant s'inscrit à une Formation, une Inscription est créée :

- **1a.** Si la Formation est payante, l'Inscription a le statut `En attente de paiement`

- **1b.** Si la Formation est gratuite, l'Inscription est automatiquement `confirmée` (pas besoin de l'intervention de l'Administrateur)

**2.** Lorsque l'apprenant commence le processus de paiement, une transaction est créée, avec le statut `En attente` :

- **2a.** Si le paiement aboutit, la Transaction passe au statut `En cours` -> l'Inscription passe automatiquement au statut `Paiement effectué`

- **2b.** Si le paiement échoue (fonds insuffisants, processus interrompu avant la fin), la Transaction passe au statut "Échouée" -> l'Inscription ne change pas de statut -> une Transaction échouée ne peut plus être modifiée. Il faudra ouvrir une autre Transaction pour effectuer un autre paiement.  

**3.** Une fois le paiement reçu, la Transaction passe automatiquement au statut `Complétée` -> L'Administrateur est notifié et peut alors confirmer manuellement l'Inscription.  

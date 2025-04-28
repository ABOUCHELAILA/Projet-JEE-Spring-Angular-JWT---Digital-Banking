**Digital Banking Backend**

Description
Ce projet est une application backend de gestion bancaire numérique, développée avec Spring Boot et Spring Data JPA.
Elle offre des fonctionnalités pour gérer les clients, les comptes bancaires (courants et d'épargne) ainsi que les opérations financières (crédits, débits, virements).

Structure du projet
Entities :

Customer : Représente les clients de la banque.

BankAccount : Compte bancaire abstrait (hérité par CurrentAccount et SavingAccount).

CurrentAccount : Compte courant avec facilité de découvert.

SavingAccount : Compte d'épargne avec taux d'intérêt.

AccountOperation : Historique des opérations bancaires (crédit/débit).

Enums :

AccountStatus : Statuts possibles d'un compte (CREATED, ACTIVATED, SUSPENDED).

OperationType : Types d'opérations (DEBIT, CREDIT).

Repositories :

CustomerRepository : Gestion des données des clients avec recherche par mot-clé.

BankAccountRepository : Gestion des comptes bancaires.

AccountOperationRepository : Gestion des opérations sur comptes avec pagination.

Web Layer :

CustomerRestController : Expose des endpoints pour la gestion des clients.

BankAccountRestAPI : Expose des endpoints pour la gestion des comptes et des opérations.

Fonctionnalités principales
Gestion des clients :

Créer, mettre à jour, supprimer et rechercher des clients.

Gestion des comptes bancaires :

Consultation des comptes bancaires.

Consultation des opérations associées à un compte (avec pagination).

Effectuer des débits, crédits, et transferts entre comptes.

API Endpoints
Clients
Méthode	Endpoint	Description
GET	/customers	Liste de tous les clients
GET	/customers/search?keyword={keyword}	Recherche de clients par nom
GET	/customers/{id}	Détails d'un client
POST	/customers	Ajouter un nouveau client
PUT	/customers/{id}	Modifier un client existant
DELETE	/customers/{id}	Supprimer un client
Comptes
Méthode	Endpoint	Description
GET	/accounts	Liste de tous les comptes
GET	/accounts/{accountId}	Détails d'un compte
GET	/accounts/{accountId}/operations	Historique des opérations d'un compte
GET	/accounts/{accountId}/pageOperations?page=x&size=y	Historique paginé des opérations
POST	/accounts/debit	Effectuer un débit
POST	/accounts/credit	Effectuer un crédit
POST	/accounts/transfer	Transférer de l'argent entre deux comptes
Technologies utilisées
Java 17+

Spring Boot

Spring Data JPA

Hibernate

Lombok

H2 Database (par défaut pour développement/test)

Maven

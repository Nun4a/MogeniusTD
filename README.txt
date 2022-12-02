Baptiste Porcu 32024624

Version avec image dans TD Mise en production image.pdf

Pour mettre en place des services sur Mogenius :
- Créer un cloudspace

- Rentrer deux Key Vault :
-- POSTGRES_USERNAME : <username souhaité>
-- POSTGRES_PASSWORD : <mot de passe souhaité>

- Ajouter un service basé sur le template PostgreSQL
-- Mettre le champ POSTGRES_USER en Key Vault avec la variable POSTGREs_USERNAME en secret
-- Mettre le champ POSTGRES_PASSWORD en Key Vault avec la variable POSTGRES_PASSWORD en secret
-- Bien mettre le nom de la base de donnée dans le champ PPOSTGRES_DB
-- Récupérer le lien de la base et le rajouter dans votre application pour accéder à la BDD

- Ajouter un service personnalisé qui ira clone votre repo Git à chaque MaJ.
-- Rajouter des variables d'environnements :
--- SPRING_PROFILES_INCLUDE -> no-liqubase
--- SPRING_DATASOURCE_USERNAME -> POSTGRES_USERNAME
--- SPRING_DATASOURCE_PASSWORD -< POSTGRES_PASSWORD
-- Bien changer adresse de la BDD dans application-prod.yml

- Lancer le service PostgreSQL puis le service Spring

Lien du déploiement : https://api-prod-test-5vbdml.mo5.mogenius.io/api/{options}
Options dispo : 
 - showadmin
 - showcenter
 - showdoctor
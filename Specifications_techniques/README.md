# Spécifications techniques

### Découpage de l'application en couche N-tier.
L'architecture de l'application sera conçue en couche N-tier, ce qui signifie qu'elle sera divisée en plusieurs couches distinctes pour une gestion efficace des données et des interactions utilisateur.  
- La couche backend sera responsable de la logique métier, de la gestion des données et des opérations complexes.
- la couche frontend se concentrera sur l'interface utilisateur et l'expérience utilisateur globale.

Les avantages d'une architecture N-tier sont nombreux.  
- Elle permet une meilleure séparation des préoccupations, ce qui rend le code plus modulaire, facile à maintenir et évolutif.
- Chaque couche peut être développée, testée et déployée de manière indépendante, facilitant ainsi les mises à jour et les modifications sans perturber l'ensemble du système.
- Cette architecture favorise une meilleure sécurité en limitant l'accès direct aux données sensibles et en contrôlant les permissions à travers différentes couches, renforçant ainsi la protection des informations critiques.

### Caractéristiques clés de conception de l'application

Ce tableau résume les principales décisions de conception prises pour notre application, en mettant en lumière divers aspects techniques et stratégiques.  

Chaque question posée explore un domaine crucial de l'architecture et du développement, de la gestion des données à l'optimisation pour les moteurs de recherche, en passant par les choix de langage et l'orientation vers l'avenir du projet.  

Chaque réponse fournit un aperçu succinct mais informatif des choix faits, guidant ainsi la mise en œuvre de l'application pour répondre aux besoins spécifiques des utilisateurs et assurer une performance optimale.

| Question  | Réponse  |
|---|---|
| Machine Learning  | Non |
| Asynchrone  | Oui |
| Architecture | API |
| SEO | Oui |
| Rendu | Client (CSR) |
| Hébergement | Serveur Perso |
| Langage |  |
| • Front-End | Typescript  |
| • Back-End | C#  |
|Futur du projet| embauche |
| BDD | SQL Relationnelle|
  
## Back-end

### Base de donnée
- [RGPD](./rgpd.md)
- [Stratégie de sécurisation BDD](./securisation-bdd.md)
- [Choix de base de données](choix-bdd.md)
- [MCD](./mcd.md)
- [MLD](./mld.md)
- [MPD](./mpd.md)
- [Dictionnaire de données](./dictionnaire-donnees.md)

### API
- [Stratégie de sécurisation API](./securisation-api.md)
- [Choix stack API](choix-stack-api.md)
- [Diagramme de cas d'utilisation](./cas-utilisation.md)
- [Diagramme d'activité](./diagramme-activite.md)
- [Diagramme de séquence](./diagramme-sequence.md)
- [Diagramme de classe](./diagramme-classe.md)


## Clients

### Front-end

- [Stratégie de sécurisation front](./securisation-front.md)
- [Choix stack front](choix-stack-front.md)
- [Wireframes](./wireframes.md)
- [Mockups](./mockups.md)

### mobile

- [Stratégie de sécurisation mobile](./securisation-mobile.md)
- [Choix stack mobile](choix-stack-mobile.md)
- [Wireframes](./wireframes-mobile.md)
- [Mockups](./mockups-mobile.md)







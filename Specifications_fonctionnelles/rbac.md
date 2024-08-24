# RBAC - Role-Based Access Control

Le Contrôle d'Accès Basé sur les Rôles (RBAC) est un modèle de gestion des autorisations qui attribue des privilèges aux utilisateurs en fonction de leur rôle au sein d'une organisation.  
Dans ce modèle, chaque utilisateur se voit assigner un ou plusieurs rôles qui déterminent les actions auxquelles il peut accéder et les opérations qu'il peut effectuer dans le système.

En attribuant des rôles spécifiques aux utilisateurs, tels que administrateur, utilisateur régulier, ou invité,  
le RBAC permet de définir clairement qui peut effectuer quelles actions sur les notes, les carnets et autres fonctionnalités de l'application.  
Cette approche simplifie la gestion des autorisations en réduisant la complexité des configurations individuelles d'autorisations pour chaque utilisateur.

Nous avons besoin d'un RBAC dans notre application pour plusieurs raisons essentielles:
- Cela garantit une sécurité renforcée en limitant l'accès aux fonctionnalités sensibles uniquement aux utilisateurs autorisés.
- cela facilite la gestion des utilisateurs à grande échelle en permettant une administration centralisée des permissions basées sur les rôles plutôt que sur des autorisations individuelles.
- le RBAC favorise la conformité réglementaire en assurant un contrôle précis et auditable des accès aux données et aux fonctionnalités critiques de l'application.



# RBAC - Role-Based Access Control

| Role/Permission                           | Visitor | User | Admin  |
|-------------------------------------------|---------|------|--------|
| **Account Management**                    |         |      |        |
| Create account                            | ✅      | ❌   | ✅    |
| Authenticate                              | ❌      | ✅   | ✅    |
| Update username                           | ❌      | ✅   | ✅    |
| Update password                           | ❌      | ✅   | ✅    |
| Change email (if validated)               | ❌      | ✅   | ✅    |
| Validate email (with code)                | ❌      | ✅   | ✅    |
| Suspend account                           | ❌      | ❌   | ✅    |
| Delete account                            | ❌      | ❌   | ✅    |
| **Note Management**                       |         |      |        |
| Create note                               | ❌      | ✅   | ✅    |
| Edit note                                 | ❌      | ✅   | ✅    |
| Edit shared note (with write permissions) | ❌      | ✅   | ✅    |
| View/restore previous note versions       | ❌      | ✅   | ✅    |
| Archive note                              | ❌      | ✅   | ✅    |
| Retrieve archived note                    | ❌      | ✅   | ✅    |
| Share note with friends (read-only/edit)  | ❌      | ✅   | ✅    |
| Sort notes alphabetically                 | ❌      | ✅   | ✅    |
| Sort notes by date                        | ❌      | ✅   | ✅    |
| Filter shared notes                       | ❌      | ✅   | ✅    |
| Filter archived notes                     | ❌      | ✅   | ✅    |
| **Notebook Management**                   |         |      |        |
| Create notebook                           | ❌      | ✅   | ✅    |
| Add notes to notebook                     | ❌      | ✅   | ✅    |
| Delete notebook (archive contained notes) | ❌      | ✅   | ✅    |
| **Friend Management**                     |         |      |        |
| Send friend request                       | ❌      | ✅   | ✅    |
| Accept/decline friend request             | ❌      | ✅   | ✅    |
| Remove friend                             | ❌      | ✅   | ✅    |
| **Admin Management**                      |         |      |        |
| Create admin account                      | ❌      | ❌   | ✅    |
| View activity logs                        | ❌      | ❌   | ✅    |

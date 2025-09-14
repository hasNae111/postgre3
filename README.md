Exercice : Gestion d'une Bibliothèque Numérique
La liste des tables:
Utilisateurs(id_utilisateur, nom, email, role['lecteur', 'bibliothecaire', 'admin'])
Livre(id_livre, titre, auteur, categorie, disponible)
Emprunts(id_Emprunts, id_utilisateur, id_livre, date_emprunt, date_retour_prevue,date_retour_reelle)
Commentaires(id_commentaire, id_utilisateur, id_livre, texte, note)

Partie 1 : Requêtes SQL basiques
Lister tous les livres disponibles.
Afficher les utilisateurs ayant le rôle ‘bibliothecaire’.
Trouver tous les emprunts en retard (date_retour_reelle est NULL et date_retour_prevue < aujourd'hui).
Donner le nombre total d’emprunts effectués.
Afficher les 5 derniers commentaires publiés avec le nom de l'utilisateur et le titre du livre.

Partie 2 : Requêtes SQL avancées
Pour chaque utilisateur, afficher le nombre de livres qu’il a empruntés.
Afficher les livres jamais empruntés.
Calculer la durée moyenne de prêt par livre (en jours).
Lister les 3 livres les mieux notés (moyenne des notes).
Afficher les utilisateurs qui ont emprunté au moins un livre de la catégorie "Science-fiction".

Partie 3 : Mises à jour & transactions
Mettre à jour le champ disponible à FALSE pour tous les livres actuellement empruntés.
Écrire une transaction SQL pour : Emprunter un livre (insérer dans Emprunts)
Mettre à jour le statut disponible du livre: Vérifier que le livre n’est pas déjà emprunté (disponible = FALSE)
Supprimer tous les commentaires des utilisateurs inactifs (ceux qui n’ont jamais emprunté de livre).

Partie 4 : Vues et fonctions SQL
Créer une vue appelée Vue_Emprunts_Actifs qui affiche tous les emprunts en cours (sans retour).
Créer une fonction SQL nb_emprunts_utilisateur(id_utilisateur INT) qui retourne le nombre d’emprunts effectués par un utilisateur donné.
Table : Utilisateurs


id_utilisateur	nom	email	role
1	Alice Martin	alice.martin@mail.com	lecteur
2	John Doe	john.doe@mail.com	bibliothecaire
3	Sarah Lopez	sarah.lopez@mail.com	lecteur
4	Marc Dupont	marc.dupont@mail.com	admin
5	Emma Bernard	emma.bernard@mail.com	bibliothecaire
6	Thomas Durand	thomas.durand@mail.com	lecteur

Table : Livre
id_livre	titre	auteur	categorie	disponible
1	L'Étranger	Albert Camus	Roman	TRUE
2	1984	George Orwell	Science-fiction	FALSE
3	Le Petit Prince	Antoine de Saint-Ex.	Conte	TRUE
4	Dune	Frank Herbert	Science-fiction	FALSE
5	Les Misérables	Victor Hugo	Classique	TRUE
6	Sapiens	Yuval Noah Harari	Histoire	TRUE

Table : Emprunts

id_emprunts	id_utilisateur	id_livre	date_emprunt	date_retour_prevue	date_retour_reelle
1	1	2	2024-06-01	2024-06-15	NULL
2	3	4	2024-06-20	2024-07-05	2024-07-03
3	6	2	2024-05-10	2024-05-25	2024-05-24
4	1	4	2024-07-01	2024-07-15	NULL

Table : Commentaires

id_commentaire	id_utilisateur	id_livre	texte	note
1	1	2	Un classique à lire absolument	5
2	3	4	Très dense, mais fascinant	4
3	6	2	Excellent, mais un peu long	4
4	1	4	Très bon roman de SF	5
5	3	1	Lecture facile et intéressante	3

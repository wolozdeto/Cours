#Windows Active Directory

---

##Notions fondamentales de l'AD

>### Les besoins
Centralisation de l'administration
Personnalisation des postes
Déploiement d'applications
Sécurités

>### Etats d'un serveur
Serveur autonome, responsable de lui-même
Serveur membre, membre d'un domaine AD
Contrôleur de domaine

>### Définitions
Domaine AD : Représentation logique d'une organisation, limite administrative de sécurité
Contrôleur de domaine : Ensemble des machines qui vont détenir la sécurité

>### Bonnes pratiques
Nom de machine pratique
Adresse IP fixe
Installation des prérequis

>### Workgroups
Réaliser un partage, créer des utilisateurs

>### Forêt et domaine
Domaine AD et Contrôleur de domaine
Créer domaine enfant avec relation d'approbation
Arborescence de domaine lorqu'il y a aucune relations entre les arbres, il faut le faire manuellement
On peut avoir plusieurs versions de DC pour une même version de forêt
Windows server 2008 --> ajout de Kerberos

>### Classes et attributs
NDTS est l'emplacement de la base AD
Schéma AD, contient la définition de toutes les classes et des attributs d'un AD
La description c'est l'ensemble des objets configurables
Classes : ordinateurs, contact, groupe, unité d'organisation, imprimante, utilisateur

>### Le Distinguished Name (DN)
DN représente le chemin LDAP
CN (common name)
OU (organizational unit)
DC (domain conponent)

---

>### Installation d'un DC d'un AD
Rôle : C'est un service qu'il va rendre aux autres serveur
Fonctionnalité : Pas de notion de service
Nom de domaine racine (ESN.dom, SKY.com)
Mot de passe de restauration des services AD
SYSVOL, contient l'intégralité des configurations de l'AD (en prod il est recommandé de séparer les dossiers NTDS et SYSVOL sur 3 volumes)

>### Jonction d'un poste à un AD
Modifier nom ordinateur (SRV1)
Mettre une IP fixe
--> restart
Modifier groupe de travail (ESN.dom, SKY.com) !!!Penser au DNS!!!
 \SKY, domaine  \SRV1, local

>### Fonctionnement des groupes
|Types de groupe|Les membres|Utlisation|
|---|---|---|
|Groupes de domaine locaux|Comptes, Groupes globaux, universels, locaux **De tout domaine**|Autorisation sur des ressources
|Groupes Globaux|Comptes, groupes globaux et universels **Du même domaine**|rassembler des utilisateurs|
|Groupe universel|comptes, groupes globaux, groupes universels **De la même forêt**|cas particulier|
Structure U-G-DL-a
Autorisation de partage : En passant par le réseau
Autorisation NTFS : En passant directement par la machine

>### Création de groupes


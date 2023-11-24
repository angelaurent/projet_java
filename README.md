# PROJET_JAVA : APPLICATION DE  SIMULATION DE TRAITEMENT D'UNE ELECTION LEGISLATIVE

##CONTEXT ET OBJECTIF DU PROJET

 dans une ville ou les elections respectent certaines normes comme : Chaque parti politique présente un candidat dans chaque 
département, et le scrutin se déroule selon des règles spécifiques. Par exemple, contrairement aux élections habituelles, les bulletins de vote blancs ou nuls ne 
sont pas autorisés dans notre simulation. De plus, chaque département ne peut avoir deux candidats obtenant le même nombre de voix, et le scrutin est 
majoritaire à un tour.Notre application a pour objectif de fournir des fonctionnalités essentielles pour répondre à une série de questions pertinentes liées à cette élection législative 
simulée. Parmi ces fonctionnalités, Nous souhaitons pouvoir calculer le taux de participation par département ainsi que le taux de participation global, 
déterminer le parti politique gagnant dans chaque département, identifier le parti politique ayant obtenu le plus mauvais score dans chaque département, obtenir 
les numéros et noms des département où au moins 50% des électeurs inscrits ont voté et enfin identifier la liste des départements où tous les électeurs inscrits ont 
voté et ont choisi le même parti politique.Pour atteindre ces objectifs, notre application sera conçue avec une structure 
orientée objet, en utilisant des classes. Les données relatives aux départements et aux partis politiques ainsi que les résultats du vote seront stockées dans des fichiers textes.

##EXPLICATION DETAILLEE DE NOS CLASSES UTILISEES POUR L'APPLICATION
Notre application de simulation d'élection législative est composée de cinq classes concrètes. Chacune de ces classes joue un rôle essentiel dans la réalisation du projet.

#Classe Departement

• Attributs : ils sont tous private
➢ Int numero
➢ String nom
➢ String situationGeographique
➢ Int nombreElecteurs (qui représente le nombre d’inscrits pour un 
département donné).
➢ Int nombreVotants (c'est le nombre de personnes qui ont vraiment voté sur la liste des inscrits, il est initialisé ainsi nombreVotants = (int) (Math.random() * this.nombreElecteurs) ).
➢ Candidat [] candidats (tableau de candidats qui se sont présentés dans le departement)
➢ Int nombreCandidats (nombre de personnes s’étant présentés comme candidat dans un département).
➢ private Int[] votes (est un tableau d'entiers représentant le nombre de voix obtenues par chaque candidat. Par exemple, l'élément à l'index zéro du 
tableau correspond au nombre de votes du candidat à l'index zéro dans le tableau des candidats).

• Méthodes :
➢ boolean existeCandidatDuMemeParti : Vérifie si un parti politique a déjà un représentant dans le département donné. Retourne True si c'est le cas, sinon retourne false.
➢ ajouterCandidat : Ajoute un nouveau candidat dans le département à condition qu'il n’existe pas déjà de candidat du même parti.
➢ Void simulerVote () : Simule le vote aléatoire pour chaque électeur, en choisissant un candidat au hasard.
➢ PartiPolitique getPartiGagnant () : Retourne le parti politique gagnant dans le département donné, en se basant sur les votes simulés.
➢ PartiPolitique getPartiPlusMauvaisScore() : retourne le parti politique ayant obtenu le plus mauvais score aux élections dans le département donné.
➢ boolean ontVoteMemeCandidat() : Vérifie si tous les votants ont choisi le même candidat, c'est-à-dire si un candidat a obtenu 100% des voix.

#Classe PartiPolitique

• Attributs : 
➢ private String nom;
➢ private String president;
➢ private Candidat[] candidats;
➢ private int nombreCandidats;

• Méthodes :
➢ Void ajouterCandidat (Candidat candidat) : Intègre un candidat dans un parti.

#Classe Candidat
• Attributs :
➢ private String nom;
➢ private Departement departement;
➢ private PartiPolitique partiPolitique;

#Classe Election

• Attributs : 
➢ private Departement[] departements;

• Méthodes : 
➢ Void simulerElections(): Effectue la simulation des élections.
➢ String [] afficherTauxParticipation() : Retourne un tableau contenant le taux de participation dans chaque département donné ainsi que le taux de participation global sur l'ensemble du pays.
➢ String [] afficherPartiGagnant() : Retourne un tableau affichant le nom du parti gagnant dans un département donné.
➢ String [] afficherPartiPlusMauvaisScore() : Retourne un tableau affichant le nom du parti politique ayant obtenu le plus mauvais score dans chaque departement.
➢ Departement [] getDepartements50Pourcent () : Retourne une liste des départements où au moins 50% des électeurs inscrits ont voté.
➢ Departement [] getDepartementsElecteursUniques () : Retourne une liste des départements où tous les électeurs ont voté et pour le même parti politique.

#Classe principale appelée App
➢ Les objets candidats, départements et partis politiques sont créés à partir des flux d'entrée des fichiers tels que candidats.txt, dept.txt et part_po.txt. De plus, les résultats des élections sont enregistrés dans le fichier resultats.txt.En plus des méthodes spécifiques mentionnées dans les différentes classes, chaque classe comprend également des méthodes de type getter et setter pour 
accéder et modifier les attributs des objets.

##GUIDE D'UTILISATION
➢ Pour exécuter le programme, assurez-vous de copier tous les fichiers nécessaires en plus du projet jar que sont "resultat.txt", "log.txt", "part_po.txt", "dept.txt" et "cand.txt", sur un support de stockage. 
➢ Ensuite, ouvrez l'invite de commande ou un terminal et naviguez vers le répertoire où vous avez enregistré l'application. 
➢ Enfin, exécutez le programme en entrant la commande java --enablepreview -jar javaProject.jar et appuyez sur Entrée. 

On pourra avoir un bref resumé du fonctionnement du programme dans le 
fichier "log.txt".
À partir de nos jeux de données, les objets Candidat, Departement et Parti 
politique sont créés, suivis d'une simulation des élections. Vous êtes libre de 
simuler les élections autant de fois que vous le souhaitez grâce à notre 
application.

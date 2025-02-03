# Framework Betula
Le projet open-source Betula est un framework bilingue (FR/EN) orienté objet pour les produits PC SOFT (WinDev, WebDev et WinDev Mobile) en Unicode.


## Objectif
Le framework est d’abord là pour faciliter la vie du programmeur en ne réinventant pas, à chaque projet, la même roue.  L’objectif est de diviser le temps de développement par 2 et d’augmenter la fiabilité du même facteur.

Dès son démarrage, en janvier 2018, il a été pensé pour devenir open-source.

Gardez à l'esprit que la release présente ici est en WD2024. La version originale, compatible WD23, est disponible avec son historique, le composant et un exemple sur [le site wlplus.org](https://wlplus.org/betula/get/)
## Structure
En bref, le framework se compose de plus de <ins>**150 classes**</ins>. Il est accompagné de <ins>**16 collections de procédures**</ins> rassemblant prés de <ins>**600 fonctions**</ins>, plus de <ins>**1000 nouvelles constantes**</ins>, des dizaines de structures nécessaires au LDAP et aux API Windows. Affichez facilement, dans vos applications, les listes complètes et à jour des pays, devises, langues, la météo, les taux de change et accédez, en quelques lignes de code, aux API, notamment Amazon AWS et OpenAI (ChatGPT).

Afin d’avoir une compatibilité multi-plateforme, des contraintes liées au WLangage ont imposé au framework quelques tours de passe-passe dans le code. Entre-autres exemples : une classe ne peut hériter que d’une seule autre classe, des syntaxes de déclaration d’objets dynamiques sont possibles pour certaines plateformes et pas d’autres, des constantes ne sont pas reconnues dans tous les produits, …

![Structure générale de Betula](https://i0.wp.com/wlplus.org/wp-content/uploads/2024/01/Betula20240122.png?w=703&ssl=1)
## Contenu
- classe cApplication pour initialiser le composant Betula (1 ligne dans le code init du projet suffit), qui initialise :<br/>
  -la gestion de fichier de log (classe cLog avec suppression des fichiers trop anciens, interception des boites de dialogue et des réponses utilisateur, copies d'écran en temps réel, envoi d'un zip crypté au dev en cas de plantage)<br/>
  -la gestion de fichier de trace (classe cTrace avec suppression des fichiers trop anciens, trace tous les appels dans le framework)<br/>
  -la gestion des erreurs (classe cErreur via cGénérique), détections globales (login/utilisateur en cours via la classe cUtilisateur, #process, chemin des données, nom du projet, version, adresse IP, ...)<br/>
  -la gestion des paramètres de l'application et/ou de l'utilisateur en cours (classe cAppParamètre : cryptage, gestion par environnement dev, test, prod,...) et sécurité<br/>

> Portion POO :
- 19 classes d'accès aux bases de données avec liste des colonnes et des indexes, objet enregistrement et tableau d'enregistrements. Gestion des jauges de chargement. Accès à Excel comme une BD.
- 87 classes LDAP sur serveur 2000 à 2012.
- 6 classes de gestion des communications (courriel, ftp, http, ...) avec serveur HTTP et web scrapping (cHTML)
- 1 classe de gestion des fichiers texte (détection automatique du format, optimisation du temps de parcours, écriture en boucle)
- 1 classe de lecture des tags mp3 (par l'utilisation de AudioGenie ou MediaInfo joint à l'exécutable), peut être étendu à d'autres types de fichiers
- 12 classes "géographiques" : continents, pays, régions, devises, langues et dialectes. Le tout en français et anglais soit par appel API, soit depuis des fichiers Excel fournis
- 1 classe pour gérer les champs obligatoires dans un formulaire

> Portion non POO :
- 100 fonctions de conversions (unités de mesure, chiffres romains, extraction d'un chiffre dans un nombre, date, UTF16, nombre en lettre en 6 langues...)
- collection de procédures pour gérer les communications DDE (ex : pour ouvrir un fichier selon son extension sans lancer plusieurs fois l'application)
- gestion des jours spéciaux par pays ou par région avec indicateur de jour férié (avec exemple (données pour la France, la Belgique, la Suisse et le Canada), fonction de DateRelative (ex : second dimanche après le 1er septembre)
- 34 fonctions de gestion d'interface utilisateur (déplacement d'un groupe de champs, nom complet, position exacte, # de cellule d'un champ disposition ou # d'onglet dans lequel se trouve un champ, nombre de plans...)
- traitement phonétique en français (celle de PCS est en anglais)
- impression d'une table WYSIWYG (fenêtre de paramétrage contenant une 50aine de paramètres)
- gestion des sources ODBC
- gestion des fichiers temporaires (choix de l'extension, suppression automatique des fichiers temp à la fermeture de l'application)
- 31 fonctions PCS surchargées
- information sur Windows, le réseau et le matériel (nom de domaine, nom du groupe local, IP publique, 15 fonctions pour le matériel, 25 fonctions pour Windows et 108 fonctions WMI)
- 14 fonctions de vérification (RIB, année bisextile, nombre hexa, comparaison "floue" de chaine ...)
- 12 fonctions de formatage de # de téléphone (France, Belgique, Canada, Dom-Tom)

## Références
[Page principale du projet sur le blog de wlplus.org](https://wlplus.org/betula/start/)

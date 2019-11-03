# Sonde Nagios Alerte Anti-spam Wordpress

Nous allons utiliser l’API REST de Wordpress en l’interrogeant à distance via la fonction curl,
par exemple en demandant combien de commentaires ont été postés après le 20 octobre 2019
07 Heures du matin au format iso-8601 :

curl -X GET http://sitewordpress/wp-json/wp/v2/comments?after=2019-09-20T07:00:00

si nous rajoutons dans le pipe : | jq nous aurons alors le retour dans un format json « lisible » 

et si nous complétons par ceci : | jq '. | length' nous aurons alors le nombre de « paragraphe commentaire » :



il suffit de tester ce nombre avec les critères WARNING=4 et SPAM=10 pour obtenir un code de sortie :
Exit Code Status :

0	OK
1	WARNING
2	CRITICAL
3	UNKNOWN 

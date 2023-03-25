Pour la création d'une architecture de datalake, nous avons différents types de données à notre disposition, notamment :

CO2 : Marque / Modèle, Bonus / Malus, Rejets CO2 g/km, Coût en énergie

`CO2.csv` peut être stocké dans HDFS, car il s'agit d'un format de stockage distribué et scalable conçu pour gérer des données volumineuses. HDFS peut gérer des fichiers de grande taille et est particulièrement bien adapté aux données non structurées.

Catalogue : Marque, Nom, Puissance, Longueur, NbPlaces, NbPortes, Couleur, Occasion, Prix

`Catalogue` peut également être stocké dans HDFS, car elles sont volumineuses et semi-structurées. HDFS peut traiter des fichiers CSV ou JSON, ce qui est idéal pour stocker des données semi-structurées comme celles-ci.

Clients : Age, Sexe, Taux, SituationFamiliale, NbEnfantsAcharge, 2ème voiture, Immatriculation

`Clients_0.csv` peut être stocké dans une base de données NoSQL, ici nous choisissons MongoDB, car il a une structure flexible et peut être stocké sous forme de documents. Les bases de données NoSQL sont également adaptées pour gérer des données en temps réel, ce qui peut être utile pour les données clients.

Immatriculation : Immatriculation, Marque, Nom, Puissance, Longueur, NbPlaces, NbPortes, Couleur, Occasion, Prix

`Immatriculations.csv` peut être stocké dans une base de données NoSQL, ici nous choisissons Oracle NoSql, car il est semi-structuré et peut être stocké sous forme de documents. 

Marketing : Age, Sexe, Taux, SituationFamiliale, NbEnfantsAcharge, 2ème voiture

`Marketing.csv` peut être stockées dans une base de données NoSQL, ici nous choisissons Oracle NoSql, car il a une structure flexible et peut être stocké sous forme de documents. Les bases de données NoSQL sont également adaptées pour gérer des données en temps réel, ce qui peut être utile pour les données marketing.

En résumé, les données `CO2` et `Catalogue` vont être stockées dans `HDFS`, tandis que les données `clients`, `immatriculation` et `marketing` vont être stockées dans `une base de données NoSQL` telle que MongoDB et oracle nosql
Aussi les fichiers `CO2` et `Catalogue` seront aussi déposés dans un repertoire windows qui sera utilisé en cas de défaillance du HDFS


Nous allons utiliser Kafka pour faire la mise à jour en temps réel de la table clients dans MongoDB lorsque le fichier sur HDFS est modifié.
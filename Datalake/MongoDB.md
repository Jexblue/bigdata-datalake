Demarrage du serveur MongoDB: "sudo systemctl start mongod"
Connexion sur MongoDB: "mongo"

Choisir un environnement avec "use"
	- use TP

Creer les collections avec db.createCollection("collection")
	- db.createCollection("Immatriculaions")
	-db.createCollection("Clients")


Importation des fichiers csv
	- mongoimport --db TP --collection Immatriculations --type csv --headerline --drop --file /home/vagrant/donnees/Immatriculations.csv
	- mongoimport --db TP --collection Clients --type csv --headerline --drop --file /home/vagrant/donnees/Clients_0.csv
	- mongoimport --db TP --collection Clients --type csv --headerline --file /home/vagrant/donnees/Clients_19.csv
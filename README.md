# ElasticSearch-Indexation

## INSTALL

`
ES => https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html
`


`
kibana => https://www.elastic.co/guide/en/kibana/current/deb.html
`

## START

`
sudo systemctl start elasticsearch.service #start lesaticserach
`

`
sudo systemctl start kibana.service #start kibana
`

## LOGSTASH CONFIG FILE

_See .conf file_

## RUN 

`
sudo /usr/share/logstash/bin/logstash -f 'path_to_conf_file' #index data in elastic using logstash
`

## CREATE AND DELETE INDEX

`
sudo curl -X PUT or DELETE "localhost:9200/nom_index?pretty" #to add or delete an index
`

## BE CAREFUL

1) Préparer les données d'entrées, le fichier à specifier dans le input du .conf de logstash

3) Préparer le fichier de conf logstash. 

	=> Specifier la condition de prise en charge du template defini avec la condition if, sinon le template par defaut sera considéré lors de l'ingestion des données.
	
	=> commenter après le if {...}, et créer un index avec le nom spécifié et dans le template, et dans le fichier .conf pour la sortie de ES.
	
	=> !Toujours ingérer le template (avec l condition if{} ) avant de créer l'index et ingérer les données par la suite en supprimant tout simplement le if dans le output qui specifie le nom de l'index
	
	=> le nom de l'index doit être identique à celui du template, dans le output de ES, le nom du template doit être spécifié


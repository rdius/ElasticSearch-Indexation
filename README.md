# ElasticSearch-Indexation

## INSTALL

ElasticSearch

```
https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html
```


kibana

```
https://www.elastic.co/guide/en/kibana/current/deb.html
```

## START

```
sudo systemctl start elasticsearch.service #start lesaticserach
```

```
sudo systemctl start kibana.service #start kibana
```

## LOGSTASH CONFIG FILE

_See .conf file_

## RUN 

```
sudo /usr/share/logstash/bin/logstash -f 'path_to_conf_file' #index data in elastic using logstash
```

## CREATE AND DELETE INDEX (In this example, you do not need to create an index, as it automatically done in the config file)

`
sudo curl -X PUT or DELETE "localhost:9200/nom_index?pretty" #to add or delete an index
`

## STEPS

1) Préparer les données d'entrées (ou à indexer), le fichier sera à specifier dans le Input du .conf de logstash

2) Préparer le fichier de config logstash. Indiquer le nom du template à la sortie du Logstash dans la section Output de ES
3) Spécifier le nom du template doit être spécifié
4) Le nom de l'Index doit être identique à celui du template, dans le Output de ES


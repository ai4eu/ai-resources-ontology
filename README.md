## WP3 Ontology SPARQL Endpoint and Web Server

Contact: olivier.corby@inria.fr



We have set up a Web server and a SPARQL endpoint to query and browse the OWL ontology, the SKOS thesaurus (ai categories) and the Knowledge Graph (from Thales, thanks to E. Blaudez) :

http://corese.inria.fr/srv/service/ai4eu

There is a set of predefined SPARQL queries. Click on submit to execute a query.


For example, the query below enables us to select a type in the KG and obtain instances of this type :

http://corese.inria.fr/srv/service/ai4eu?uri=st:kg1

The URL in the result are browsable as hypertex links, hence we can browse the KG.


This query searches the skos thesaurus of ai categories :

http://corese.inria.fr/srv/service/ai4eu?uri=st:skos1


This one searches the ontology classes :

http://corese.inria.fr/srv/service/ai4eu?uri=st:owl1

This service displays the ontology class hierarchy :

http://corese.inria.fr/srv/service/class?param=%2Fdata%2Fdemo%2Fai4eu%2Fai4eu.ttl

![](images/class-hierarchy.png)

This one displays the property signatures :

http://corese.inria.fr/srv/service/signature?param=%2Fdata%2Fdemo%2Fai4eu%2Fai4eu.ttl

![](images/property-signatures.png)


There is a SPARQL endpoint at this URL :

http://corese.inria.fr/ai4eu/sparql


You can send a query via HTTP this way :

    wget "http://corese.inria.fr/ai4eu/sparql?query=prefix rel: <http://ai4eu.org/onto/> select * where {?s rel:instanceof ?o} limit 10" -O tmp.txt

or :

    curl -o tmp.txt --data-urlencode "query=select * where {?s ?p ?o} limit 10" http://corese.inria.fr/ai4eu/sparql
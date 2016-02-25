# neo4j-recommendation-engine
POC for Neo4j Recommendation Engine based on https://github.com/graphaware/neo4j-reco

######Installation of Neo4J
1. su
2. Enter password
3. wget -O - http://debian.neo4j.org/neotechnology.gpg.key | apt-key add -
4. echo 'deb http://debian.neo4j.org/repo stable/' > /etc/apt/sources.list.d/neo4j.list
5. exit
5. sudo apt-get update
6. sudo apt-get install neo4j
7. Check the Neo4j is running service neo4j-service status

######Installation of GraphAware libraries
1. <a href="http://products.graphaware.com/download/reco/latest">GraphAware Neo4j Recommendation Engine</a>
2. <a href="http://products.graphaware.com/download/framework-server-community/latest">GraphAware Neo4j Framework</a>
3. Dropped the downloaded jar files into the plugins directory (/var/lib/neo4j/plugins) of your Neo4j installation
4. sudo mv ~/Downloads/graphaware-reco-2.3.2.37.10.jar /var/lib/neo4j/plugins
5. sudo mv ~/Downloads/graphaware-server-community-all-2.3.2.37.jar /var/lib/neo4j/plugins

######Installation of Neo4j Recommendation Engine (Maven)
1. Download a copy of the project from https://github.com/graphaware/neo4j-reco
2. Unzip the project to ~/Downloads
3. cd ~/Downloads/neo4j-recommendation-engine
4. mvn clean install 

######Load Neo4J with data
1. Access http://localhost:7474
2. Cut and paste the following to the Neo4J console -->$
```
CREATE
    (m:Person:Male {name:'Michal', age:30}),
    (d:Person:Female {name:'Daniela', age:20}),
    (v:Person:Male {name:'Vince', age:40}),
    (a:Person:Male {name:'Adam', age:30}),
    (b:Person:Female {name:'Britney', age:12}),
    (l:Person:Female {name:'Luanne', age:25}),
    (c:Person:Male {name:'Christophe', age:60}),
    (j:Person:Male {name:'Jim', age:40}),

    (lon:City {name:'London'}),
    (mum:City {name:'Mumbai'}),
    (br:City {name:'Bruges'}),

    (m)-[:FRIEND_OF]->(d),
    (m)-[:FRIEND_OF]->(l),
    (m)-[:FRIEND_OF]->(a),
    (m)-[:FRIEND_OF]->(b),
    (m)-[:FRIEND_OF]->(v),
    (d)-[:FRIEND_OF]->(v),
    (b)-[:FRIEND_OF]->(v),
    (j)-[:FRIEND_OF]->(v),
    (j)-[:FRIEND_OF]->(m),
    (j)-[:FRIEND_OF]->(a),
    (a)-[:LIVES_IN]->(lon),
    (d)-[:LIVES_IN]->(lon),
    (v)-[:LIVES_IN]->(lon),
    (m)-[:LIVES_IN]->(lon),
    (j)-[:LIVES_IN]->(lon),
    (c)-[:LIVES_IN]->(br),
    (b)-[:LIVES_IN]->(br),
    (l)-[:LIVES_IN]->(mum);
```






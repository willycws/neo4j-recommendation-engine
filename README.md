# neo4j-recommendation-engine
POC for Neo4j Recommendation Engine

######Installation of Neo4J
1. su
2. Enter password
3. wget -O - http://debian.neo4j.org/neotechnology.gpg.key | apt-key add -
4. echo 'deb http://debian.neo4j.org/repo stable/' > /etc/apt/sources.list.d/neo4j.list
5. exit
5. sudo apt-get update
6. sudo apt-get install neo4j
7. Check the Neo4j is running service neo4j-service status

######Installation of GraphAware
1. <a href="http://products.graphaware.com/download/reco/latest">GraphAware Neo4j Recommendation Engine</a>
2. <a href="http://products.graphaware.com/download/framework-server-community/latest">GraphAware Neo4j Framework</a>
3. Dropped the downloaded jar files into the plugins directory (/var/lib/neo4j/plugins) of your Neo4j installation
4. sudo mv ~/Downloads/graphaware-reco-2.3.2.37.10.jar /var/lib/neo4j/plugins
5. sudo mv ~/Downloads/graphaware-server-community-all-2.3.2.37.jar /var/lib/neo4j/plugins




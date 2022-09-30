# Neo4j-apoc.export.cypher.all / Export to Cypher Script

 * Backup with cypher Neo4j browser



        CALL apoc.export.cypher.all("arli-export.cypher", {
            format: "plain",
            useOptimizations: {type: "UNWIND_BATCH", unwindBatchSize: 20}
        })
        YIELD file, batches, source, format, nodes, relationships, properties, time, rows, batchSize
        RETURN file, batches, source, format, nodes, relationships, properties, time, rows, batchSize;

* Create new database in Neo4j browser
* Restore with cypher Neo4j browser

       CALL apoc.cypher.runFile("arli-export.cypher", {statistics: false});


#### Noted:

* saved in path directory /home/arliputraa/neo4j-enterprise-4.4.11/import/arli-export.cypher
* By default exporting to the file system is disabled. We can enable it by setting the following property in /neo4j/conf/apoc.conf :

      apoc.export.file.enabled=true

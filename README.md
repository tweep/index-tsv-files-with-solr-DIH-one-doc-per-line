# index-csv-files-with-solr-DIH-one-doc-per-line

Here's a quick examle how to index a bunch of CSV files from the file system
with SOLR; for each line in the CSV, we're creating a SOLR document.

- the DataImportHandler ( so indexing can be started by http post )
- FileListEntityProcessor ( identify all files to index from file system )
- LineEntityProcessor ( process each line of the CSV )
- scriptTransformer : create one solr document per (parsed) tab-separated line

## Todo
- add request handler to solrconfig.xml

```
       <requestHandler name="/import_pheno_data" class="org.apache.solr.handler.dataimport.DataImportHandler">
            <lst name="defaults">
          <str name="config">pheno-data-config.xml</str>
         <str name="update.chain">dedupe</str>
        </lst>
     </requestHandler>
```

## Create file pheno-data-config.xml
Example in conf/pheno-data-config.xml

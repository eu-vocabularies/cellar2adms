# Production of ADMS packages for EU vocabularies assets

The process was imagined as a future component of a larger process that will facilitate the automated publication of EU Vocabularies to various portals supporting the ADMS standard.
The implementation is based on the a process invoving the extraction of assets from Publications Office SPARQL endpoint and automated production of the ADMS metadata files for each of them.
The current implementation of the transformation pipelines uses Linked Pipes ETL (https://etl.linkedpipes.com/).


#### **Folders:** 
* pipeline: Contains the JSONLD source of the pipeline
* input: Contains the list of assets to be processed as CSV file and the bsh file used to call the REST API
* output: Contains sample of resulted ADMS files in RDF and TTL formats


#### **Input:** 
* CELLAR SPARQL endpoint
  
#### **Output goals:**
* To generate ADMS packages in RDF and TTL formats
* Resulted packages to be fully compliant with JoinUP requirements for publication

### ETL pipelines description
* Phase-0 : ETL REST service receives orders
* Phase-1 : Asset profile is extracted from CELLAR (http://publications.europa.eu/webapi/rdf/sparql)
* Phase-2 : Metadata is generated in acordance with ADMS requirements
* Phase-3 : File names are generated from the public ID of the asset
* Phase-4 : ADMS files are saved on local FTP


### Technical notes for the current implementation
* input data: Currently provided as bash process pointing to REST API
* output data: ftp://localhost:22/data/out/adms
 

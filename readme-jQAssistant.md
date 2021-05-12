# jQAssistant

This repository provides an example setup for the integration of jQAssistant into the Spring PetClinic to demonstrate:

* Exploration & Analysis
* Architecture Validation & Documentation

## Requirements

* Java Development Kit 8
* [Maven 3.6](https://maven.apache.org/)

## Preparation

* Clone this repository to your local machine
* Build the project using `mvn verify -DskipTests`

## Exploration using the Neo4j Browser

* Run `mvn jqassistant:server`
* Open your browser with the URL `http://localhost:7474`
* If asked for Neo4j credentials switch to "No authentication" and confirm
* Enter your first query (e.g. `MATCH (artifact:Artifact)-[:CONTAINS]->(type:Type) RETURN artifact.fqn as Artifact, count(type) as Types ORDER BY Types desc`) and hit Ctrl-Enter

## jQAssistant Dashboard (Experimental)
* The jQAssistant Dashboard illustrates visualization of structures and metrics. Note: It is currently a prototype for demonstration purposes.
* Run `mvn jqassistant:server`
* Open your browser with the URL `http://localhost:7474/jqassistant/dashboard`
* If asked for Neo4j connection settings just click "Save"
* Explore the dashboard!

## Analysis using Jupyter Notebooks

* Run `docker-compose -f jqassistant-docker-compose.yml up` (Note: the Neo4j server must be stopped before running this command)
* Open the Juypter URL shown in the startup log including the token (e.g. `http://127.0.0.1:8888/?token=<the token>`) with your browser, this will open the Jupyter file browser
* The folder `examples` contains a notebook `vis.ipynb` illustrating differents visualizations of code structures.

## Architecture Validation and Documentation

* The example rules are contained in the folder `/jqassistant`
* After a successful build (see above) the created jQAssistant reports are available in the folder `/target/jqassistant/report/`, the rendered HTML output is located in the sub-folder `asciidoc/`

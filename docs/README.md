# jQAssistant demo output for Spring PetClinic #
jQAssistant ([https://www.jqassistant.org](https://www.jqassistant.org "https://www.jqassistant.org")) is a great tool for scanning  and validating software structures (like Maven projects or Java bytecode). It also brings the fantastic feature of defining all the rules that should be validated within AsciiDoc files. With this approach you'll get a **self-validating living architecture documentation**!

The creators of jQAssistant built up a showcase with the [Spring PetClinic project](https://github.com/buschmais/spring-petclinic/) for getting you started very quickly. On this page, you'll find the generated outputs of jQAssistant (also available directly on [GitHub](https://github.com/buschmais/spring-petclinic/tree/master/docs)) for that project. It's meant for people who don't have the time or setup to build the entire project with Java / Maven / GraphViz. 

The files will give you a quick impression of what jQAssistant is capable of.

## Documentation

In the following, you can see the files that will be generated with a <tt>mvn clean install</tt> and be placed in <tt>/target/generated-docs</tt>. It's the final documentation of the software architecture including design concepts and programming conventions. It contains the description of the software system in words along with "concepts" (aka the "things" your software system is made of) and "constraints" (aka "rules" that need to be behelt) written in the graph query language [Cypher](https://neo4j.com/developer/cypher-query-language/). The concepts and constraints will be applied and validated against your artifacts during the build by jQAssistant.

### [index.html](documentation/index.html)
The generated documentation as HTML files based on the AsciiDoc files in <tt>/jqassistant</tt>:

![HTML-Documentation_1](screenshots/html-documentation-1.png)

**Figure 1: Beginning of the documentation including a table of contents on the left side**

    
![HTML-Documentation_2](screenshots/html-documentation-2.png)

**Figure 2: UML diagram produced with PlantUML/GraphViz directly out of the real code**


![HTML-Documentation_3](screenshots/html-documentation-3.png)

**Figure 3: Inline defined concepts that jQAssistant will find in your code and show in your documentation**

  
## Reports
Within a build, jQAssistant will not only produce the documentation files, but also apply and validate your software structure. Here you can see some examples of the produced results:

### [jqassistant-report.xml](reports/jqassistant-report.xml)
The XML report with the result of the architecture validation  that will be produced with <tt>mvn clean install</tt>
  

![XML-File](screenshots/xml-report.png)

**Figure 4: The raw XML report**


### .graphml files
You can also define some special queries in your documentation that generate diagrams. Here are some of the diagramms generated in GraphML:

* [layer_LayerDependencyDefinition.graphml](reports/graphml/layer_LayerDependencyDefinition.graphml)
  
You'll need yEd to open them. In yEd, you have to select all elements and layout them e. g. via "Layout" -> "hierarchical". But for your convenience, here you can see an example:  


![yEd-Editor](screenshots/yed-graphml.png)

**Figure 5: A diagram of some components of the software system, viewed in yEd**


For more information, check out the [documentation](https://jqassistant.github.io/jqassistant/doc/) or the [project's website](https://jqassistant.org/).

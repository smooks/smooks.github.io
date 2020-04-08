<br/>
All Smooks components are available from the Maven Central Repository.

If your building Smooks from source using Maven, please use:

1. Java 1.5 or 1.6
2. [Maven v3](https://maven.apache.org/download.cgi) 


## Artifact IDs
The **groupId** for all Smooks components is "**org.milyn**".

The **artifactId** for each of the Smooks components are as follows:

* Smooks Core: "milyn-smooks-core"
* [Smooks Cartridges](documentation/#smooks-cartridges):
    * Calc:"milyn-smooks-calc"
    * CSV: "milyn-smooks-csv"
    * Fixed length reader: "milyn-smooks-fixed-length"
    * EDI: "milyn-smooks-edi"
    * Javabean: "milyn-smooks-javabean"
    * JSON: "milyn-smooks-json"
    * Routing: "milyn-smooks-routing"
    * Templating: "milyn-smooks-templating"
    * Persistence: "milyn-smooks-persistence"
    * Validation: "milyn-smooks-validation" 
* Commons: "milyn-commons" (all components depend on Commons, so no need to specify a dependency on this module if you are already dependent on one of the others)
* EdiSax: "milyn-edisax"

**Note**: All cartridges depend on Smooks Core (i.e. "milyn-smooks-core"). Therefore, if your project depends on one of the cartridges, there's no need to specify the dependency on Smooks Core.

```xml
<dependency>
    <groupId>org.milyn</groupId>
    <artifactId>milyn-smooks-javabean</artifactId>
    <version>1.7.1</version>
</dependency>
```

See the POMs in the Examples as examples of Maven based applications that depend on different Smooks Cartridges.


## SNAPSHOTs

Smooks SNAPSHOTs are available from [Sonatype OSSRH](https://oss.sonatype.org/content/repositories/snapshots). You need to list this Maven repo in your project POM e.g.

```xml
<repositories>
    ....
    <repository>
        <id>oss.sonatype.org-snapshot</id>
         <url>http://oss.sonatype.org/content/repositories/snapshots</url>
         <releases>
            <enabled>false</enabled>
         </releases>
         <snapshots>
            <enabled>true</enabled>
         </snapshots>
    </repository>
</repositories>
```
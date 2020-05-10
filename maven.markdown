<br/>
All Smooks components are available from the Maven Central Repository.

If your building Smooks from source using Maven, please use:

1. Java 8
2. [Maven v3](https://maven.apache.org/download.cgi) 

## Artefact IDs
The Maven group ID for Smooks cartridges, excluding the EDI and EDIFACT cartridges, is "**org.smooks.cartridges**". For the EDI and EDIFACT cartridges,
the group ID is "**org.smooks.cartridges.edi**". All remaining Smooks artefacts have the groupId "**org.smooks**".

The **artifactId** for each of the Smooks components are as follows:

* Smooks Core: "smooks-core"
* [Smooks Cartridges](documentation/#smooks-cartridges):
    * Calc: "smooks-calc-cartridge"
    * CSV: "smooks-csv-cartridge"
    * Fixed length reader: "smooks-fixed-length-cartridge"
    * EDI: "smooks-edi-cartridge"
    * EDIFACT: "smooks-edifact-cartridge"
    * Javabean: "smooks-javabean-cartridge"
    * JSON: "smooks-json-cartridge"
    * Routing: "smooks-routing-cartridge"
    * Templating: "smooks-templating-cartridge"
    * Persistence: "smooks-persistence-cartridge"
    * Validation: "smooks-validation-cartridge" 
    * DFDL: "smooks-dfdl-cartridge"
* Commons: "smooks-commons" (all components depend on Commons, so no need to specify a dependency on this module if you are already dependent on one of the others)

**Note**: All cartridges depend on Smooks Core (i.e., "smooks-core"). Therefore, if your project depends on one of the cartridges, there's no need to specify the dependency on Smooks Core.

```xml
<dependency>
    <groupId>org.smooks.cartridges</groupId>
    <artifactId>smooks-javabean-cartridge</artifactId>
    <version>2.0.0</version>
</dependency>
```

See the POMs in the [examples](https://github.com/smooks/smooks-examples) as examples of Maven based applications that depend on different Smooks Cartridges.


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
<br/>
If you're using Ant in your project, you can pull the Smooks binaries from the Maven repository using the "**getsmooks-build.xml**" Ant script:

1. Make sure [Ant](https://ant.apache.org/) is installed, and your environment properly configured.
2. [Download getsmooks-build.xml](https://github.com/smooks/smooks-distro/blob/master/utils/getsmooks-build.xml) to a local directory.
3. Check the "**smooks.version**" script property and make sure it is set to the appropriate version (e.g. "1.7.1").
4. In the download directory, run "**ant -f getsmooks-build.xml**".


The jar files will be dropped in the "**./smooks-<timestamp>**" folder, from where you can easily copy them to the appropriate location. 
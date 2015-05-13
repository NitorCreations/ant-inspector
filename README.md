Tool I developed to perform archaeology on Apache Ant build scripts.

Say you have a project with a complex set of ant build scripts and you need to get an overview of what some specific target does. Using this tool you can execute

    ./ant2fm -b release.xml -D release.version=1.0 make-release > make-release.fm

This produces a file `make-release.fm` which can be opened for browsing by the venerable Freemind mindmapping tool (and also other tools supporting the same file format).

Notable shortcomings:

* Poor error reporting
* Unsupported tasks:
    * <include> 
* Unsupported task features
    * <ant inheritAll="true"> (default behaviour)
    * <ant dir="...">
    * <ant useNativeBasedir="...">
    * <ant><property>
    * <antcall inheritAll="true"> (default behaviour)
    * <antcall><param>

# Example

For this randomly selected Ant build file on github:

  https://github.com/jheizmann/HaloACL/blob/3de9ac606c9ccab1acfeb3f75c2b9ae070412a8c/tests1/webtests/tests/allTests.xml

we get the following partially expanded freemind graph:

  [images/example1.png]

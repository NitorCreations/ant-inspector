# Ant Inspector

Tool I developed to inspect [Apache Ant](https://ant.apache.org) build scripts visually.

Say you have a project with a complex set of ant build scripts and you need to get an overview of what some specific target does. Example execution:

    ./ant2fm -b release.xml -D release.version=1.0 make-release > make-release.fm

This visualizes the tasks that would be executed when running:

    ant -f release.xml -Drelease.version=1.0 make-release

This produces a file `make-release.fm` which can be opened for browsing by the venerable [Freemind mindmapping tool](http://freemind.sourceforge.net/wiki/index.php/Main_Page) (and also other tools supporting the same file format).

# TODO

A subset of notable shortcomings:

* Poor error reporting
* Unsupported tasks:
    * &lt;include&gt;
* Unsupported task features
    * &lt;ant inheritAll="true"&gt; (default behaviour)
    * &lt;ant dir="..."&gt;
    * &lt;ant useNativeBasedir="..."&gt;
    * &lt;ant&gt;&lt;property&gt;
    * &lt;antcall inheritAll="true"&gt; (default behaviour)
    * &lt;antcall&gt;&lt;param&gt;

# Example

For this randomly selected Ant build file on github:

  https://github.com/jheizmann/HaloACL/blob/3de9ac606c9ccab1acfeb3f75c2b9ae070412a8c/tests1/webtests/tests/allTests.xml

we get the following partially expanded Freemind graph (cropped screenshot):

  <a href="https://raw.githubusercontent.com/NitorCreations/ant-inspector/master/images/example1.png"><img src="images/example1.png"></a>

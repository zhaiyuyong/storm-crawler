storm-crawler
=============

A collection of resources for building low-latency, large scale web crawlers on [Storm](http://storm.apache.org/) available under Apache License.

## How to use
### As a Maven dependency
Available from Maven Central with : 

```
<dependency>
    <groupId>com.digitalpebble</groupId>
    <artifactId>storm-crawler-core</artifactId>
    <version>0.4</version>
</dependency>
```
### Running in local mode
To get started with storm-crawler, it's recommended that you run the CrawlTopology in local mode.
 
NOTE: These instructions assume that you have Maven installed.

First, clone the project from github:
 
 ``` sh
 git clone https://github.com/DigitalPebble/storm-crawler
 ```
 
Then :
``` sh
cd core
mvn clean compile exec:java -Dstorm.topology=com.digitalpebble.storm.crawler.CrawlTopology -Dexec.args="-conf crawler-conf.yaml -local"
```
to run the demo CrawlTopology.

### On a Storm cluster
Alternatively, generate an uberjar:
``` sh
mvn clean package
```

and then submit the topology with `storm jar`:

``` sh
storm jar target/storm-crawler-core-0.5-SNAPSHOT-jar-with-dependencies.jar  com.digitalpebble.storm.crawler.CrawlTopology -conf crawler-conf.yaml
```

to run it in distributed mode.

## Getting help

Mailing list : http://groups.google.com/group/digitalpebble

Or use the tag [storm-crawler](http://stackoverflow.com/questions/tagged/storm-crawler) on stackoverflow. 



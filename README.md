[![Build Status](https://travis-ci.org/yakworks/gorm-tools.svg?branch=master)](https://travis-ci.org/yakworks/gorm-tools)



Documentation 
-----

Guide: https://yakworks.github.io/gorm-tools/  
API: https://yakworks.github.io/gorm-tools/api/

**Running mkdocs locally**  
Docs are built with https://yakworks.github.io/mkdocs-material-components/
Run 
> ```pip install -r pip-requirements.txt```
And then ```mkdocs serve``` see the docs if you have troubles

**Publishing**  
Build are automatically published by travis. 
Snapshots are published from master branch, and releases are published from tags to BinTray.

If you want to publish artifacts from your local system.
 
Define following properties in ~/.gradle/gradle.properties

- bintrayUser
- bintrayKey
- artifactoryUsername
- artifactoryPassword

bintray credentials are used for **bintrayUpload** task. Artifactory credentials are used for publishing snapshots to 9ci artifactory.

**Using latests SNAPSHOT**  
Configure 9ci repo in build.gradle

```groovy
repositories {
  maven { url "http://repo.9ci.com/artifactory/grails-plugins" }
 }
```

Add dependency for snapshot  

```groovy
dependencies {
 compile("org.grails.plugins:gorm-tools:3.0.7-SNAPSHOT") { changing = true } //see gradle.properties for latest snapshot version.
}
```
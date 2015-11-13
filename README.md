# gradle-applyscript-plugin
Gradle plugin that applies Gradle build scripts in jars.
So that you can package multi Gradle build scripts into a jar, and distribute it to any repo as a standard artifact.

## Install
All Gradle versions:
```
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.orctom.gradle:gradle-apply-script-plugin:1.0'
    }
}

apply plugin: 'com.orctom.apply'
```

Gradle 2.1 or newer:
```
plugins {
	id "com.orctom.apply" version "1.0"
}
```

# Usage
Option 1:
```
dependencies {
	scripts '{{scriptjar.group}}:{{scriptjar.name}}:{{scriptjar.version}}'
}

applyScript '{{scriptjar.name}}-{{scriptjar.version}}/{{gradle-script-filename}}.gradle'
```

Option 2:
```
applyScript '{{scriptjar.group}}:{{scriptjar.name}}:{{scriptjar.version}}/{{gradle-script-filename}}.gradle'
```
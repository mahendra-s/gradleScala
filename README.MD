# Scala Project under Gradle

## Create
```$xslt
mkdir -p gradleScala
cd gradleScala
gradle init --type scala-library --package me.example
```

## Build
`gradle build`

## Create and Run Application
Add application plugin in `build.gradle`

```$xslt
plugins {
id 'application'
}

application {
mainClassName = me.example.Application
}
```

Add Application Main Object as 
```$xslt
package me.example

object Application extends App {
println("Hello Mahendra!")
}
```

Run Application

`gradle run`

## Publishing

To publish built artifact in maven repository

Step 1) Add Plugin 
`plugins.id 'maven-publish'`
Step 2) Define publication artifact
```$xslt
publishing {
    publications {
        maven(MavenPublication) {
            // built artifact details
            groupId = 'me.example'
            artifactId = 'gradleScala'
            version = '1.0.1'
            from componets.java
        }
    }
}
```

Step 3) (Optional) Publish docs and sources 
```$xslt
java {
    withJavadocJar()
    withSourcesJar()
}
```

Step 4) Publish and PublishLocal
`gradle publish`
`gradle publishToMavenLocal`
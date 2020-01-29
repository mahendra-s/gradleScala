# Scala Project under Gradle

## Create
```$xslt
mkdir -p gradleScala
cd gradleScala
gradle init --type scala-library --package com.example
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
mainClassName = com.example.Application
}
```

Add Application Main Object as 
```$xslt
package com.example

object Application extends App {
println("Hello Mahendra!")
}
```

Run Application

`gradle run`
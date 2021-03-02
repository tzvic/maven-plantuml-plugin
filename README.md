A [maven](http://maven.apache.org/) plugin to generate UML diagrams using [PlantUML](http://plantuml.sourceforge.net/) syntax.

# Usage

To generate images from PlantUML description add following dependency to your pom.xml:

```xml
...
<build>
  <plugins>
    <plugin>
      <groupId>net.sourceforge.plantuml</groupId>
      <artifactId>plantuml-maven-plugin</artifactId>
      <version>1.2021.1</version>
      <configuration>
        <sourceFiles>
          <directory>${basedir}</directory>
          <includes>
            <include>src/main/plantuml/**/*.wsd</include>
          </includes>
        </sourceFiles>
      </configuration>
      <dependencies>
        <dependency>
          <groupId>net.sourceforge.plantuml</groupId>
          <artifactId>plantuml</artifactId>
          <version>1.2021.1</version>
        </dependency>
      </dependencies>
    </plugin>
  </plugins>
</build>
```

Note that you must explicitly define the PlantUML version you want to use.

Then execute command:

```
mvn clean net.sourceforge.plantuml:plantuml-maven-plugin:generate
```

# Extra configuration options

`outputDirectory` Directory where generated images are generated. Defaults to `${basedir}/target/plantuml`

`outputInSourceDirectory` Whether or not to generate images in same directory as the source file. Defaults to `false`.

`format` Output format. Defaults to `png`.

`verbose` Wether or not to output details during generation. Defaults to `false`.

`preproc` Generate the preprocessed files .


Released under [Apache 2 license](http://www.apache.org/licenses/LICENSE-2.0.html).

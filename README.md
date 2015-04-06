# About OS X Application Bundle Plugin #

This plugin creates an Application Bundle for OS X containing all your project dependencies and the necessary metadata.

The application bundle will be packaged in a zip-file, allowing you to build it on Linux or Windows and then unpack it as an application on OS X.

If this plugin is run on a Mac OS X platform it will also create a DMG disk image containing the Application Bundle.

For more details, see [the official documentation](http://mojo.codehaus.org/osxappbundle-maven-plugin/).

# Usage #

This is a [Maven](http://maven.apache.org/) [plugin](http://maven.apache.org/plugins/index.html). As such, it can be enabled in any Maven project. See [the examples provided](http://mojo.codehaus.org/osxappbundle-maven-plugin/) and [the full documentation of the osxappbundle:bundle mojo](http://mojo.codehaus.org/osxappbundle-maven-plugin/bundle-mojo.html).

You can clone this repository and build a new snapshot, which you can then use in your project's build:

```
<project>
  ...
  <build>
    <plugins>
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>osxappbundle-maven-plugin</artifactId>
        <version>1.0-SNAPSHOT</version>
        <configuration>
          ...
        </configuration>
        <executions>
          <execution>
            <phase>package</phase>
            <goals>
              <goal>bundle</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
</project>
```

This is not recommended though, since the resulting build is not reproducible.

Alternatively, you can use the unofficial releases available in the [PhenoTips Nexus repository](https://nexus.phenotips.org/nexus/#nexus-search;quick~osxappbundle-maven-plugin):

```
<project>
  ...

  <pluginRepositories>
    <pluginRepository>
      <id>nexus.phenotips.org</id>
      <name>PhenoTips Releases</name>
      <url>https://nexus.phenotips.org/nexus/content/repositories/externals</url>
      <layout>default</layout>
      <snapshots>
        <enabled>false</enabled>
      </snapshots>
      <releases>
        <updatePolicy>never</updatePolicy>
      </releases>
    </pluginRepository>
  </pluginRepositories>
  ...
  <build>
    <plugins>
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>osxappbundle-maven-plugin</artifactId>
        <version>1.0-alpha-5-sdumitriu</version>
        <configuration>
          ...
        </configuration>
        <executions>
          <execution>
            <phase>package</phase>
            <goals>
              <goal>bundle</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
</project>
```

# LICENSE #

Licensed under the Apache License, Version 2.0. For more details, see [LICENSE.txt](LICENSE.txt).
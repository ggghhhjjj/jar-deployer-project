# jar-deployer-project
 Maven skeleton pom project for 3-th party jar installation

Use this project as an example configuration when you need to deploy jar-s without sources for your Maven project.

The project shows how to use maven-install-plugin to install 3-th party jars and use them afterwards in you Maven project

## Configuration steps
1. Put the jar to be deployed into the project root folder.
2. Appned execution id bellow with the jar file name and artifact's GAV.

        <plugin>
              <artifactId>maven-install-plugin</artifactId>
              <version>2.5.2</version>
              <executions>
                  <execution>
                      <id>test.jar</id>
                      <goals>
                          <goal>install-file</goal>
                      </goals>
                      <phase>generate-resources</phase>
                      <configuration>
                          <file>${project.basedir}/test.jar</file>
                          <groupId>jar.deployer</groupId>
                          <artifactId>test.jar</artifactId>
                          <version>1.0</version>
                          <createChecksum>true</createChecksum>
                          <generatePom>true</generatePom>
                      </configuration>
                  </execution>
              </executions>
          </plugin>
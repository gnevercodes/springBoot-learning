# Maven

## Project based learning:

`install Maven`.

> macos : brew install maven

### properties:

`maven validate` looks at pom.xml and checks is a valid xml maven project and reports it.
`mvn clean` : deletes the target folder.

### Pom xml file :

1. compiler files , junit files.
2. build section
   1. specify plugins: for testing etc purposes.
3. Dependencies:
   1. specify dependency by groupid , artifactID , version to tell maven to downlaod the dependency. which is nice.
   2. we can add dependency by
   ```xml
   <dependency>
      <groupId>
      <artifactId>
      <version>
      <scope> // for testing , main , compile time
   </dependency>
   ```
4. properties can be set using junit version , properties can be used.

   > <junit.version></junit.version> in the properties file
   > <version>${junit.version}</version>

5. Scope : compile , test(only when test cases) , `mostly these are being used`.

6. dependencies are being added from internet.
7. `search.maven.org`.

### important things in xml file:

1. group id : should be in reverse of dommain name.
2. artifact : should be the goal
3. snapshot version mean's its a work in progress.
4. change version in dependency and it changes it
5. use intellJ builin dependency search.

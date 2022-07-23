# maven-quickstart
Exemple pour démontrer comment fonctionne les cycles de vies maven


Le plugin [echo-maven-plugin](https://github.com/Ekryd/echo-maven-plugin/wiki/Cookbook) est utilisé pour écrire à l'écran l'étape du cycle de vie exécutée.

## Vérifier quelles sont les étapes auxquelles font appel `mvn clean install`

`mvn clean install` 

Le résultat à l'écran sera:

```
In pre clean
...
In clean
...
In validate
...
In compile
...
In test
...
In package
...
In Install

```


## Vous pouvez rattacher le plugin aux phases additionnelles que vous souhaitez observer.

Pour observer la phase `deploy`

```
<plugins>
  <plugin>
      <groupId>com.github.ekryd.echo-maven-plugin</groupId>
      <artifactId>echo-maven-plugin</artifactId>
      <executions>
          <execution>
              <id>deploy</id>
              <phase>deploy</phase>
              <goals>
                  <goal>echo</goal>
              </goals>
              <configuration>
                  <message>In 'deploy'</message>
              </configuration>
          </execution>
      </executions>
    </plugin>
</plugins>
```

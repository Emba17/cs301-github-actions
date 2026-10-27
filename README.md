# CS301 — GitHub Actions and Gradle

This project continues the previous JFiglet assignment. The Java application
prints a greeting as ASCII art using `com.github.lalyos:jfiglet:0.0.9`.

## Build and run

Install Java 21, then use the checked-in Gradle wrapper:

```sh
./gradlew build
./gradlew run
```

On Windows, use `gradlew.bat build` and `gradlew.bat run`.

The build creates `build/libs/jfiglet-gradle.jar`. This is the application JAR;
its JFiglet dependency is provided by Gradle when running with `./gradlew run`.
The application distribution under `build/distributions/` includes dependencies.

## Pull request automation

The workflow in `.github/workflows/gradle.yml` builds every pull request using
Java 21 and `./gradlew build --no-daemon`.

The `test-build` branch changes the original `Hello CS301` greeting. A later
commit adds JAR upload so the workflow's run summary offers a downloadable
`java-jar` artifact.

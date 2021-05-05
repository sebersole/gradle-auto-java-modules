# gradle-auto-java-modules

Illustrates the problem trying to mix auto and explicit Java 9 modules onces Gradle's `java-library` plugin is added to the mix

`project-a` is intended for Java 8+ and so cannot define a `module-info.java` file.  So it uses the standard `Automatic-Module-Name` JAR manifest entry to supply the module name.  This module name is only available when using the JAR.

`project-b` is a consumer of `project-a`.  However, it targets Java 11 so defines an explicit `module-info.java` requiring the `project-a` module by name.


# Java 9 simple multi-module project
Sample created to understand the module support introduced by Java 9.
Basically is possible define modules inside the application that can:
- import modules
- export specific packages

Each module declare what need to include or what want to share with other modules defining the ```module-info.java```.
Below an example:

```java
//bootstrap module require to import a specific package to use
module bootstrap {
  requires andzac.greetings;
}

//greetings module export a single package externally
  module andzac.greetings {
      exports it.andzac.j9;
  }
```
> The module-info should be defined at src folder level.
## Example
The demo application is defined with two module:
- ```greetings``` that export the package that contains the ```Greetings``` class
- ```bootstrap``` that require the ```Greetings``` class to use its method.
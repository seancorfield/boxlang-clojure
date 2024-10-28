# BoxLang / Clojure interop example

You need the following installed:
* Java 21 (JDK): https://adoptium.net/temurin/releases/
* Clojure CLI: https://clojure.org/guides/install_clojure
* BoxLang runtime (Beta 20 or later): https: https://boxlang.io/download#runtimes

To check your Clojure CLI/Java installation, run:

```bash
clojure -M -e '((requiring-resolve (quote example.greet/welcome)) "CLI")'
```
That should print:
```
"Hello, CLI!"
```

Then run the `index.bxs` script with BoxLang:

```bash
boxlang index.bxs
```
(assuming `boxlang` is in your PATH)

Your should see output like this:
```
file:/home/sean/boxlang/src/
file:/home/sean/.m2/repository/org/clojure/clojure/1.12.0/clojure-1.12.0.jar
file:/home/sean/.m2/repository/org/clojure/core.specs.alpha/0.4.74/core.specs.alpha-0.4.74.jar
file:/home/sean/.m2/repository/org/clojure/spec.alpha/0.5.238/spec.alpha-0.5.238.jar
1
2
3
(+ 1 2) = 3
require failed: Could not locate example/no_such_namespace__init.class, example/no_such_namespace.clj or example/no_such_namespace.cljc on classpath. Please check that namespaces with dashes use underscores in the Clojure file name.
Hello,World!
Hello, Clojure!
6
```
(the paths of those `file:` URLs will be different on your system)

The `require failed` message is expected: that is a test of catching
exceptions in BoxLang that are thrown from Clojure code.

Happy Clojuring!

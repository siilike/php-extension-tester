# PHP extension tester

This is a simple Gradle script to automatically test a PHP extension with different PHP versions.

It downloads the versions defined in the `php` array, compiles them, compiles the extension with each version and runs the tests. To add a version not published in php.net add, for example, version "local" to the versions array and put the relevant source to `php-src/local`.

Next, run `./gradlew compilePHP` do download and/or compile all relevant PHP versions.

Next, symlink or copy the extension source to `src/`. The source must be clean (run `make clean`).

Finally, run `./gradlew test`. This copies the extension source to `build/$php_version`, runs `phpize`, `./configure`, `make` and `make test`.

To clean up run `./gradlew clean`.
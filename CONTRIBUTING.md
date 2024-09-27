# Contributing to Presto

    1. User friendliness
        1. Config options have names and descriptions that can be understood by someone configuring Presto
        1. All new language features, new functions, and major features have documentation added
        1. When adding a new method to [plugin.java](https://github.com/prestodb/presto/blob/master/presto-spi/src/main/java/com/facebook/presto/spi/Plugin.java), include documentation for the new method. 
        1. Release notes following the [Release Note Guidelines](https://github.com/prestodb/presto/wiki/Release-Notes-Guidelines) are added for user visible changes
* For large features, discuss your design with relevant code owners before you start implementing it.

Spring Cloud Config provides server and client-side support for externalized configuration in a distributed system.

With the Config Server you have a central place to manage external properties for applications across all environments. The concepts on both client and server map identically to the Spring Environment and PropertySource abstractions, so they fit very well with Spring applications, but can be used with any application running in any language. As an application moves through the deployment pipeline from dev to test and into production you can manage the configuration between those environments and be certain that applications have everything they need to run when they migrate. The default implementation of the server storage backend uses git so it easily supports labelled versions of configuration environments, as well as being accessible to a wide range of tooling for managing the content. It is easy to add alternative implementations and plug them in with Spring configuration.

CloudConfigService uses properties files from the CloudConfigProperties repository. Due to the need of passing the properties files' location, they must be either stored in $HOME/git/symbiote/coreConfig-properties folder (default location), or the proper location needs to be set in the CloudConfigService's application.properties file. In the latter case please be careful when committing your changes so that the default location is not overwritten.

Due to the nature of Spring Cloud Config, the properties folder needs to be a git repository and any changes in properties files will not be picked up by the config server until they are committed to local repository.

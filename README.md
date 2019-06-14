# Example Liferay OAuth2 Provider scope translation conventions override

JAX-RS applications deployed to Liferay Portal are inspected by the runtime, causing ResourceBundleLoader OSGi services to be automatically registered.
These will read from the application module's ```ResourceBundle```. i.e. ```/src/main/properties/content/Language.properties```

However, when this ```ResourceBundle``` is missing language keys of the form oauth2.scope.X corresponding to scopes published by the application,
then the ```oauth2-provider-scope-impl``` module of Liferay Portal provides a default scope description through its ```ResourceBundle```. 

This example module uses the Liferay Language Extender feature to override the ResourceBundleLoader that is used to load it, 
so that a custom default ```ResourceBundle``` can be used.

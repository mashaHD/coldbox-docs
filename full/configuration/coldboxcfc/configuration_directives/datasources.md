# Datasources

This element is used to define metadata about datasources used in your application. ColdBox does not register the datasources with the under-lying CFML engine.  This setting is for documentation and easy usage of datasource information in your application.

```js
//Datasources
datasources = {
	alias1 = { name="", dbType="", username="", password=""},
	alias2 = { name="", dbType="", username="", password=""}
};
```

You can add any key to the datasource configuration structure.  You will then be able to retrieve it in your handlers/interceptors/models.

```js
// Retrieve
getDatasource( "alias1" );

// Inject
property name="dsn1" inject="coldbox:datasource:alias1";
```

> **Info** : Please note that the `getDatasource()` method is not available in your models.  Models are isolated so you will need to inject them with the appropriate datasource structure using the `coldbox:datasource:{alias}` injection DSL.

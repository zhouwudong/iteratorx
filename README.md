# IteratorX: simplest iterator for IO

## 1. JdbcReader: read jdbc table rows into json objects

Read each jdbc Table Row into JSONObject iterably.

```	
	// create jdbc reader
	final JdbcReader jdbcReader = new JdbcReader(
			new JdbcDataSourceBuilder().setUrl("jdbc:postgresql://10.23.112.2:3333/dbname")
					.setUser("username").setPassword("password").build());
	
	// fetch by iterable
	for (final JSONObject item : jdbcReader.read("select * from tablename")) {
		System.err.println(item);
	}
	
	// fetch all into one collection
	final Collection<JSONObject> items = jdbcReader.readAll("select * from tablename where id = ?", "param");
	for (final JSONObject item : items) {
		System.err.println(item);
	}
```
## 2. FileReader: read file content lines into json objects
todo

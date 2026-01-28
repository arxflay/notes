SQL database is general purpose database and this comes at cost when we need specific operation to be fast. It's possible to use SQL for every operation but it will consume more time. It doesn't mean that SQL is bad and in it

 Alternatives:
1. *Memory only databases*
	* Very fast
	* Data are not persistent
	* Usually key-pair structure
	* Example: *Redis*
2. *Logging databases*
	* Fast text search (regex) and great compression
	* No schema required
	* Example: *Loki*
3. Metric (Vector) databases
	* Made for time series metrics, for example data flow per second
	* 1000 lines of SQL code will be equal to few lines of metric databases
	* Used for monitoring
	* Example: *Prometheus, Mimir (enterprise prometheus)*
4. Hybrids
	* General purpose SQL databases, that can be used for metric data
	* They may lack typical SQL operations but have metric specific operations
	* Example: *Clickhouse*


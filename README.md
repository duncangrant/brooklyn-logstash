# brooklyn-logstash

Pure Brooklyn YAML blueprint to deploy a [Logstash](https://www.elastic.co/products/logstash) instance from the sources. This can be deployed as a `standalone` server or as a `child` of another software process.

When started as `standalone`, you can currently customize the following configuration:

- **logstash.config.input**: The `input` for the logstash configuration file
- **logstash.config.filter**: The `filter` for the logstash configuration file
- **logstash.config.output**: The `output` for the logstash configuration file
- **logstash.config.dir**: The folder that contains the configuration files

When started as `child`, Logstash server will be embedded as a child of a SoftwareProcess who
publishes his 'log.location' as a sensor. Callers should configure 'logstash.elasticsearch.ip' (if using ES)
or 'logstash.config.output'.

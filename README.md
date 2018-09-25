# logstash

logstash is the central component of the elasticsearch/logstash/kibana (ELK) stack. It is a jruby middleware application whose purpose is to aggregate, parse, and emit streams of application logs. It lets you define inputs, filters, and outputs for your log streams. The actual log streams themselves are handled by a separate application in the ecosystem. Common applications for this include filebeat and rsyslog.

## logstash inputs

The inputs folder provides examples of logstash configurations to handle incoming log streams.  Typically we will tag an input log stream to identify it and route it to the proper filter.

## logstash grok filters

logstash filters are extremely powerful and let us parse and transform log streams. They define complex regexes which match customized application log formats, allowing incoming log streams to be parsed into json. They also perform other operations such as transforming or adding additional custom fields, and performing geoip lookups. Once the streams are transformed into json, they are ready to be sent to our defined outputs.

## logstash outputs

The outputs folder provides examples of logstash configurations to handle the final processing of log streams. Typically these is elasticsearch, but it's common to use a message queue such as SQS or kinesis as an intermediate message store. A single stream can be emitted to several different outputs.
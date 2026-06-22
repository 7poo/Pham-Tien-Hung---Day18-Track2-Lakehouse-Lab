# Delta Log Sample

Source:
`_lakehouse/bronze/llm_calls_raw/_delta_log/00000000000000000000.json`

```json
{"protocol":{"minReaderVersion":1,"minWriterVersion":2}}
{"metaData":{"format":{"provider":"parquet","options":{}},"schemaString":"{\"type\":\"struct\",\"fields\":[{\"name\":\"request_id\",\"type\":\"string\",\"nullable\":true,\"metadata\":{}},{\"name\":\"ts\",\"type\":\"timestamp\",\"nullable\":true,\"metadata\":{}},{\"name\":\"raw_json\",\"type\":\"string\",\"nullable\":true,\"metadata\":{}}]}","partitionColumns":[]}}
{"add":{"path":"part-00001-8ac282f9-1089-4909-bf61-5c7fb8e8a123-c000.snappy.parquet","partitionValues":{},"size":13994842,"dataChange":true,"stats":"{\"numRecords\":200000,...}"}}
{"commitInfo":{"operation":"WRITE","operationParameters":{"mode":"Overwrite"},"operationMetrics":{"num_added_files":1,"num_added_rows":200000,"num_removed_files":0},"clientVersion":"delta-rs.py-0.25.5"}}
```

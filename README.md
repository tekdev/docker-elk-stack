You might need to edit your host file and map elasticsearch and logstash to your localhost `127.0.0.1` .
Shell scripts to trigger jenkins job via the CLI are under `jenkins/shell_scripts`.
Jenkins test job is a parametirised job which has a boolean to make the job either failed or succeed. Both script accept that flag and will trigger the job with that parameter. if you don't pass anything the build will always succeed.  

once kiban is connected to elasticsearch you can create index patterns via the Gui or via this curl command
` curl -XPOST -D- 'http://localhost:5601/api/saved_objects/index-pattern' \
    -H 'Content-Type: application/json' \
    -H 'kbn-version: 6.3.2' \
    -d '{"attributes":{"title":"logstash-*","timeFieldName":"@timestamp"}}' `

## Running
To run the stack, simply run it with ``docker-compose up ``.
services endpoints are:
- Jenkins from http://localhost:8080
- Cerebro from http://localhost:9000
- Elasticsearch from http://elasticsearch:9200
- Kibana from http://localhost:5601
- logstash from http://localhost:5000

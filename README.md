# docker-logstash-postgres-elasticsearch

A modified Logstash Docker image with plugins (JDBC) capable of synchronizing our Elasticsearch index with data in a Postgres database

## Usage

```bash

# Pull the image from dockerhub
docker pull studysnap/logstash-pg-es:<version_tag>

# Run the image
docker run -d -e DB_NAME=studysnap_notedb \
  -e DB_USER=studysnap \ 
  -e DB_PASS=password \ 
  -v logstash.yml:/usr/share/logstash/config/logstash.yml \
  -v pipelines.yml:/usr/share/logstash/config/pipelines.yml \
  -v /pipelines/:/usr/share/logstash/pipeline \
  studysnap/logstash-pg-es:<version_tag>

```

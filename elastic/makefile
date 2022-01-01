ELAS=7.13.2

simple:
	docker-compose -f docker-compose.yml up 

clean:
	docker container prune --force
	docker ps -a --filter status=exited --format {{.ID}} | xargs docker rm

pull:
	docker pull docker.elastic.co/elasticsearch/elasticsearch:${ELAS}

run:
	docker run -d -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:${ELAS}

bash:
	docker run -it docker.elastic.co/elasticsearch/elasticsearch:${ELAS} bash


info:
	CORRECT:

	1. docker pull docker.elastic.co/elasticsearch/elasticsearch:${ELAS}
	
	2. docker volume create elastic-data
	
	3. docker run -v elastic-data:/usr/share/elasticsearch/data  -it docker.elastic.co/elasticsearch/elasticsearch:${ELAS}  bash
	# check to make sure /usr/share/elasticsearch/data is externalized
	
	chown elasticsearch:elasticsearch /usr/share/elasticsearch/data
	
	#make sure the following runs your elastic search 
	/tini -- /usr/local/bin/docker-entrypoint.sh eswrapper
	
	finally run
	4. docker run -v elastic-data:/usr/share/elasticsearch/data -d -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:${ELAS} 

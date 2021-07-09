NAME=sada1
ITAG=sada001/myrepos:sada-centdjango

run:
	docker run   -p 4000:4000 -v /tmp/:/tmp1 --rm --name ${NAME} -it ${ITAG}

run1:
	docker run -it --rm -p 4000:4000 -v /tmp/:/tmp1 --rm --name ${NAME} ${ITAG}

build:
	docker pull python:3.8.3
	docker build --tag=${ITAG} .

show:
	docker image ls

rm:
	docker stop ${NAME}
	docker rm ${NAME}


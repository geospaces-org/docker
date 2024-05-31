#
# docker image ls
# > geo-echo   latest      9ffdf79538a3   7 days ago      1.56GB
# 
TAGNAME=geo-echo
DOCKERHUB=sada001/geo

k8stest:
	#docker network create demonet 
	docker  build --tag=${TAGNAME} -f Dockerfile-rhel9-cpu-kube-echo  .

push:
	docker login --username sada001 #As.....$
	docker tag  $(TAGNAME) $(DOCKERHUB):$(TAGNAME)
	docker push $(DOCKERHUB):$(TAGNAME)
	docker tag  $(DOCKERHUB):$(TAGNAME) $(TAGNAME)
	echo "You can use " $(DOCKERHUB):$(TAGNAME)

k8stest-run1:
	docker run --name k8stest1 -p 8000:8000 --rm -e PORT=8000 -v /tmp/:/opt/apps/tmp/ $(TAGNAME)

k8stest-run2:
	docker run --name k8stest2 -p 8001:8001 --rm -e PORT=8001 -v /tmp/:/opt/apps/tmp/ $(TAGNAME)

mk:
	echo "*** Running minikube: "  $(DOCKERHUB):$(TAGNAME)


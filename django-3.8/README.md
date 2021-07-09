### STEP 1 : To Build the Docker image and push it to Dockerhub

In this step, we will download and create django python 3.8.3 image.

[#1] docker pull python:3.8.3
[#2] docker build --tag=sada-centdjango
[#3] docker tag sada-centdjango sada001/myrepos:sada-centdjango

Now login to docker using "docker login" sada001 and password
or on Mac goto docker Dashboard and push

[#4] docker push sada001/myrepos:sada-centdjango

### To USE the docker

docker pull sada001/myrepos:sada-centdjango
docker run --rm -it --name sada1 sada001/myrepos:sada-centdjango 
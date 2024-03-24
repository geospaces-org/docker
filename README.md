** Docker commands

START PODMAN PROPERLY:

[ ] podman machine init -v $HOME:$HOME

---------------------------------------------------------------------------------------------
1. docker pull hello-world          # if problem check proxy - pulls the image

2. docker image ls                  # Show images

3. RUN - various options

    HOST_FOLDER="~/notebooks"
    DOCK_FOLDER="/notebooks"
    VOLUMES= "-v HOST_FOLDER:DOCK_FOLDER"

    HOST_PORT="8000"
    DOCK_PORT="8888"
    PORTS= "-p HOST_PORT:DOCK_PORT"

    docker run $VOLUMES $PORTS -it --rm --name note1  -d 


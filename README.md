# Introduction to Docker, K8s & Openshift

## The steps to build a container image

Container images act like the blueprint of a container. You need to build an image first, then from that image, you can start up as many containers as you want.

1. Clone this repo

2. Using the command line, navigate to the root folder of the project

3. Type the following command: 

        docker build -t division-service .

    This command will take the instructions from the dockerfile and use it to build our container image. The `-t` flag is used to tag the image or name it.

4. To ensure the image is created, you can use the following command

        docker images

    This command shows a list of docker images that you currently have on your machine.

## Steps to start a container from image

Now that we have created our docker image, we can start a new container from that image.

1. Type the following command:

            docker run -d -P --name my-container division-service

    The `docker run` command is used to start up new containers from a docker image.

    The `-d` flag runs the container in the background (detached mode)

    The `-P` flag will bind the exposed port to your Docker host on a random port

    The `--name` flag will set the name of the container

    Finally, the name of the image is the last parameter which was `division-service` in this example.

2. To check for the randomly assiged port, use the following command

        docker ps

    This lists all the running containers along with some of their information like port mappings

3. You can access your application through localhost and concatenating the port number you got from the previous step. *(Example: http://localhost:32771/)*

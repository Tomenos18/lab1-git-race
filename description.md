## How to deploy with Dockerfile

It's very simple, just follow the following steps:

1. Run the script called "create_image.sh" from the "scripts" folder. This if going to create the image that we need:

```console
$ scripts/create_image.sh
```

2. If all went correctly, a image has been created (Image ID and Size may be different):

```console
$ docker images
REPOSITORY      TAG       IMAGE ID       CREATED          SIZE
lab1-git-race   latest    6de6b5e29bda   1 minutes ago   709MB
```

3. Finally, the following command run the container and is going to link the port 8080 of the container with the port 8080 of the host. This can be changed for example `5000:8080` to link the port 8080 of the container with the port 5000 of the host.
```console
$ docker run -p 8080:8080 lab1-git-race
```
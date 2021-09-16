# Web Engineering 2021-2022 / Lab1 Git Race

Please, go to the [Wiki](https://github.com/UNIZAR-30246-WebEngineering/lab1-git-race/wiki) in order to get the instructions for this assignment.

Some ideas for obtaining a :gift: if you are the first that:

- **Moby Dick**: Use Docker to run the app
- **Moby Dick II**: Use Docker Compose to run the app
- **Moby Dick III**: Use Kubernetes (minikube) to run the app
- **Home improvement**: Use a markup template language different from Thymeleaf (server side)
- **Home improvement II**: Use an endpoint that returns the message and update the HTML in client side (no MVC server side)
- **Home improvement III**: Use moder JS framework (React) and a Restful web service (no MVC server side)

User name | NIA | Travis-CI|Score
----------|-----|----------|-----
[UNIZAR-30246-WebEngineering](https://github.com/UNIZAR-30246-WebEngineering/lab1-git-race) |30246 | [![Build Status](https://github.com/UNIZAR-30246-WebEngineering/lab1-git-race/actions/workflows/ci.yml/badge.svg)](https://github.com/UNIZAR-30246-WebEngineering/lab1-git-race/actions/workflows/ci.yml)
[Tomás Pelayo Benedet](https://github.com/Tomenos18/lab1-git-race) |779691 | [![Build Status](https://github.com/Tomenos18/lab1-git-race/actions/workflows/ci.yml/badge.svg)](https://github.com/Tomenos18/lab1-git-race/actions/workflows/ci.yml)
your name | your nia | your Travis-ci status

## How to deploy with Dockerfile

It's very simple, just follow the following steps:

1. Run the script called "create_image.sh" from the "scripts" folder. This if going to create the image that we need:

```
$ scripts/create_image.sh
```

2. If all went correctly, a image has been created (Image ID and Size may be different):

```
$ docker images
REPOSITORY      TAG       IMAGE ID       CREATED          SIZE
lab1-git-race   latest    6de6b5e29bda   1 minutes ago   709MB
```

3. Finally, the following command run the container and is going to link the port 8080 of the container with the port 8080 of the host. This can be changed for example `8080:5000` to link the port 8080 of the container with the port 5000 of the host.
```
$ docker run -p 8080:8080 lab1-git-race
```
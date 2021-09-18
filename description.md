# Documentation

## Integration Tests

There's 3 tests, stored at `src/test/kotlin`, that have been made for this Kotlin Webpage

---

### HTML/CSS Tests

The file `src/test/kotlin/IntegrationTest.kt` contains two tests that checks the main behaivour of the HTML page itself:

- `testHome()` checks if making a request at `http://localhost:$port` (With `$port` in this case being 0 for the shake of the test), yields both:

  - A `OK` HTTP Status Code.
  - A HTML body with `<title>hello`.

    If this happens, we can assume the webpage's HTML is the one intended.
- `testCss()` checks if the CSS of the webpage has basic functionality. For this, it request `http://localhost:$port/webjars/bootstrap/5.1.0/css/bootstrap.min.css` from the Web Server, and checks if it has a response with:

  - A `OK` HTML Status.
  - A body with `"body"`.
  - A file with a header equal to that of `"text/css"`.

This ensures the webpage has a valid CSS file.

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

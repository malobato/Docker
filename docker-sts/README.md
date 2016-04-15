#malobato/sts
Dockerfile to build a development environment with the Spring Tool Suite IDE and Git.

You can build it with

```bash
docker build .
```

and run it with this command and the _\<image id\>_ you got at the end of the built
```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY -v /home/malobato/test:/home/sts/test --name sts <IMAGE ID>
```


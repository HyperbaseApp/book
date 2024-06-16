# Build From Source

This section will cover how to build Docker image from source. Before doing so, you can visit [the Docker website](https://www.docker.com/) for instructions on how to install and use Docker. You will also need git to clone the source repository. Visit [the git website](https://git-scm.com/) to install git and learn how to use it.

To build the source code, you need to follow these steps:

- Clone the Hyperbase source code hosted from [this GitHub repository](https://github.com/HyperbaseApp/hyperbase). You can also clone the Hyperbase UI source code form [this GitHub repository](https://github.com/HyperbaseApp/hyperbase-ui) and follow similar next steps.

```console
$ git clone git@github.com:HyperbaseApp/hyperbase.git
$ # git clone git@github.com:HyperbaseApp/hyperbase-ui.git
```

- Open the local directory of the repository.

- Build the source code using Docker.

```console
$ docker build . -t mnaufalhilmym/hyperbase
$ # docker build . -t mnaufalhilmym/hyperbase-ui
```

After successfully build the image(s), you can proceed to [setup](04_setup/01_chapter.md).

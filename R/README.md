# R Image Creation
Docker uses a Dockerfile to create an image that will be used for containers. In this case the Dockerfile in this project is used to create the image.

There are a few steps to get this Dockerfile working on a computer the way Docker intends.

1. Install Docker
    - https://docs.docker.com/install/
    - Make sure Docker is installed correctly
        - ```docker --version```
1. Build the image
    - ```docker build --tag=NameYouWant .```
    - this needs to be done in the same folder as the Dockerfile
    - ```docker image ls```
    - this checks what images are on the PC
1. Run the image to create a container
    - Some example runs
    ```
    docker run -v /c/Users/justi/Documents/Test_env:/home/rstudio/data -d -p 8787:8787 -e PASSWORD=work -e USER=me --name rstudio test_build
    docker run -v /c/Users/justi/PychramProjects/repo/docker_build:/home/rstudio/data -d -p 8787:8787 -e PASSWORD=work -e USER=me --name rstudio r_test
    docker run -v /c/Users/justi/PycharmProjects/repo/docker_builds:/home/rstudio/data -w /home/rstudio/data -p 8787:8787 -i -t r_test bash
    ```

### Some Notes on the Dockerfile
- The current version of R is tidyverses 
- Uses a non-R solution for installation 

## Useful Links
- https://docs.docker.com/get-started/part1/
- https://hub.docker.com/r/rocker/tidyverse/
- https://www.rocker-project.org/
- https://towardsdatascience.com/creating-sandbox-environments-for-r-with-docker-def54e3491a3
- https://www.r-bloggers.com/an-introduction-to-docker-for-r-users/
- https://github.com/rocker-org/rocker/wiki/Using-the-RStudio-image
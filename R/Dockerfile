# Basic Documentation
# https://hub.docker.com/r/rocker/tidyverse/
# https://www.rocker-project.org/
# Guides
# https://towardsdatascience.com/creating-sandbox-environments-for-r-with-docker-def54e3491a3
# https://github.com/rocker-org/rocker/wiki/Using-the-RStudio-image
# https://www.r-bloggers.com/an-introduction-to-docker-for-r-users/
# Problems with gitbash (use powershell)
# https://github.com/docker/toolbox/issues/673
# run command for my pc
# docker run -v /c/Users/justi/Documents/Test_env:/home/rstudio/data -d -p 8787:8787 -e PASSWORD=work -e USER=me --name rstudio test_build
# docker run -v /c/Users/justi/PychramProjects/repo/docker_build:/home/rstudio/data -d -p 8787:8787 -e PASSWORD=work -e USER=me --name rstudio r_test
# docker run -v /c/Users/justi/PycharmProjects/repo/docker_builds:/home/rstudio/data -w /home/rstudio/data -p 8787:8787 -i -t r_test bash
FROM rocker/tidyverse:latest

RUN mkdir -p $HOME/.R

RUN apt-get update -qq && apt-get -y --no-install-recommends install \
  libxml2-dev \
  libcairo2-dev \
  libsqlite3-dev \
  libmariadbd-dev \
  libmariadb-client-lgpl-dev \
  libpq-dev \
  libssh2-1-dev \
  unixodbc-dev \
  && install2.r --error \
    --deps TRUE \
    tidyverse \
    dplyr \
    devtools \
    formatR \
    remotes \
    selectr \
    caTools \
    BiocManager

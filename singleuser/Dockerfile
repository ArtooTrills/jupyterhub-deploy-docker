ARG DOCKER_NOTEBOOK_IMAGE
FROM $DOCKER_NOTEBOOK_IMAGE
ARG JUPYTERHUB_VERSION
USER root
RUN apt-get update
RUN apt-get install -yq --no-install-recommends libmysqlclient-dev
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
USER $NB_UID
RUN python3 -m pip install --no-cache jupyterhub==$JUPYTERHUB_VERSION
RUN python3 -m pip install --no-cache pymongo
RUN python3 -m pip install --no-cache textblob
RUN python3 -m textblob.download_corpora lite
RUN python3 -m pip install --no-cache mysqlclient
RUN python3 -m pip install --no-cache MySQL-python
# RUN python3 -m pip install --no-cache python-mysqldb

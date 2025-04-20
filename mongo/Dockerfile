ARG MONGODB_VERSION=8.0

FROM mongo:${MONGODB_VERSION}

ADD ./initdb.d /docker-entrypoint-initdb.d/

ARG MONGO_INITDB_DATABASE
RUN echo "db = db.getSiblingDB('${MONGO_INITDB_DATABASE}');" >> /docker-entrypoint-initdb.d/init.js \
    echo "db.createCollection('${MONGO_INITDB_DATABASE}');" >> /docker-entrypoint-initdb.d/init.js

EXPOSE 27017

CMD [ "mongod" ]
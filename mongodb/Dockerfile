# MongoDB Dockerfile
FROM dockerfile/ubuntu

# Install MongoDB.
RUN \
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10 && \
  echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' > /etc/apt/sources.list.d/mongodb.list && \
  apt-get update && \
  apt-get install -y mongodb-org && \
  rm -rf /var/lib/apt/lists/*

RUN apt-get update -y && apt-get upgrade -y && apt-get install git 
# Define mountable directories.
#VOLUME ["/data/db"]

# Define working directory.
WORKDIR /data

# Define default command.
CMD ["mongod --httpinterface"]
#ENTRYPOINT ["/usr/bin/mongod"]

# Expose ports.
EXPOSE 27017
EXPOSE 28017

#RUN git clone https://github.com/inab/openVRE.git
#RUN for f in openVRE/install/database/*.json; do mongoimport --host my-mongodb --db open-vre -u ${MONGO_ADMIN} -p ${MONGO_ADMIN_PASS} --authenticationDatabase admin $f; done


~                       

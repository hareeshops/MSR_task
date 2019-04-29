FROM ubuntu:latest

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
RUN echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /sbin/initctl /bin/true 

RUN apt-get update
RUN apt-get install mongodb

RUN mkdir -p /data/db

EXPOSE 27017
CMD ["usr/bin/mongod", "--smallfiles"]
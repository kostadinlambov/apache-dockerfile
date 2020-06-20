# apache-dockerfile

This is a Dockerfile based on Ubuntu 20.04. The Image from this Dockerfile will install Apache Server. The index.html in the current repo will be copied into the Image und set as default page for the Apache Server.

Build an Image with docker from this Dockerfile:

`docker image build -t apache-img .`

Create a container from this Image:

`docker container run -d -p 80:80 --name apache-container apache-img`

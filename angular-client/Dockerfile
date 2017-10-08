# Create image based off of the REHL node image
FROM registry.access.redhat.com/rhscl/nodejs-4-rhel7

MAINTAINER zeatful zeatful@github.com

# Set the labels that are used for OpenShift to describe the builder image.
LABEL io.k8s.description="Running an angular client on Openshift v3" \
    io.k8s.display-name="Angular 2 on OC" \
    io.openshift.expose-services="4200:http" \
    io.openshift.tags="builder,webserver,html,angular" \
    io.openshift.s2i.scripts-url="image:///usr/libexec/s2i"
# This last label tells s2i where to find its mandatory scripts (run, assemble, save-artifacts)

# Create a directory where our app will be placed
RUN mkdir -p /usr/src/app

# Change directory so that our commands run inside this new dir
WORKDIR /usr/src/app

# Copy dependency definitions
COPY package.json /usr/src/app

# Install dependecies
RUN npm install

# Get all the code needed to run the app
COPY . /usr/src/app

# Expose the port the app runs in
EXPOSE 4200
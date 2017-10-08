# angular2-s2i
This guide was made by following https://github.com/openshift/source-to-image/tree/master/examples/nginx-centos7

## Getting started
### Prerequisites
#### Docker
Install the version for your OS:
https://store.docker.com/search?type=edition&offering=community

#### s2i
`brew install source-to-image`

### Create the builder image
`docker build -t angular-oc .`

### Testing the builder image
`docker build -t angular-oc-candidate . IMAGE_NAME=angular-oc-candidate test/run`

### Creating the application image
`s2i build test/test-app angular-oc angular-oc-app`
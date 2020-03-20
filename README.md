# tssc-pipelines
Sample Pipelines for the Trusted Software Supply Chain

## Overview
This repo contains reference pipelines for the Trusted Software Supply Chain. 

The reference pipeline included is based on a Java web application and performs the following steps:
* SCM Checkout of Source Code
* Builds the artifacts using mvn package
* Unit test the code base using JUnit
* Scans the source code using Sonar Qube Scanning
* Builds the image using Openshfit Binary Build
* Scans the image using Anchore Scanning
* Deploys the application using Helm to the Dev namespace

## Installation

* Create projects for Dev deployment
````
$oc new-project example-dev
````

### Openshift Appy Install
````
helm template v1 ./helm/pipelines/ -set global.namespace=tssc-tools --set global.cluster_url=mikes.sandbox389.opentlc.com --set application.app_dev_namespace="example-dev" | oc apply -f-
````
### Using Helm Install
````
helm install v1-pipes ./helm/pipelines/ --set global.namespace=tssc-tools --set global.cluster_url=mikes.sandbox389.opentlc.com --set application.app_dev_namespace="example-dev"
````



# tssc-pipelines
Sample Pipelines for the Trusted Software Supply Chain

## Overview
This repo contains reference pipelines for the Trusted Software Supply Chain. 

## Installation

Modify the settings in the file helm/pipelines/values.yaml

helm template v1 helm/pipelines | oc apply -f-

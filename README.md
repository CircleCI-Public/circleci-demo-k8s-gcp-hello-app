circleci-k8s-gcp-hello-app
==========================

This project demonstrates continuous delivery with [CircleCI](https://circleci.com) and [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine/) using [Docker](https://www.docker.com/) and [Kubernetes](https://github.com/GoogleCloudPlatform/kubernetes).

This project is based on the demo tutorial here:
https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app

The code for the hello-app application was extracted from this repository: https://github.com/GoogleCloudPlatform/kubernetes-engine-samples/tree/master/hello-app

## Required Environment Variables
Note that the following environment variables must be set on CircleCI via the
project settings page:
* GCLOUD_SERVICE_KEY: e.g. `<base64-encoded GCP service account key value>`
* GOOGLE_PROJECT_ID: e.g. hello-app-12345
* GOOGLE_CLUSTER_NAME: e.g. cluster-1
* GOOGLE_COMPUTE_ZONE: e.g. us-central1-a
* DOCKER_IMAGE_NAME: e.g. gcr.io/hello-app-12345/hello-app

## Useful References
- https://circleci.com/docs/2.0/google-auth/#creating-and-storing-a-service-account

circleci-demo-k8s-gcp-hello-app
===============================

[![CircleCI](https://circleci.com/gh/CircleCI-Public/circleci-demo-k8s-gcp-hello-app.svg?style=svg)](https://circleci.com/gh/CircleCI-Public/circleci-demo-k8s-gcp-hello-app)

This project demonstrates continuous delivery with [CircleCI](https://circleci.com) and [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine/) using [Docker](https://www.docker.com/) and [Kubernetes](https://github.com/GoogleCloudPlatform/kubernetes).

This project is based on the demo tutorial here:
https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app

The code for the hello-app application was based on this repository: https://github.com/GoogleCloudPlatform/kubernetes-engine-samples/tree/master/hello-app


## Prerequisites
* GCP project: A GCP project created from the Kubernetes Engine page in the Google Cloud Platform Console (or one with Kubernetes Engine API and related services enabled)
* GCP service account: A GCP service account must already exist before running the build, and it needs to have sufficient privileges to manage the project's resources

## Required Environment Variables
Note that the following [environment variables](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project) must be set for the project on CircleCI via the
project settings page:
* GCLOUD_SERVICE_KEY: `<base64-encoded GCP service account key value>`
* GOOGLE_PROJECT_ID: e.g. hello-app-12345
* GOOGLE_CLUSTER_NAME: e.g. cluster-1 (the cluster will be created if it doesn't yet exist)
* GOOGLE_COMPUTE_ZONE: e.g. us-central1-a
* DOCKER_IMAGE_NAME: e.g. gcr.io/hello-app-12345/hello-app (should match project id)
* DELETE_CLUSTER_AT_END_OF_TEST: true|false (If set to `true`, the deployment's resources including the cluster named by GOOGLE_CLUSTER_NAME will be *deleted* after the test. This will prevent unwanted charges incurring on your GCP account)

## Useful References
- https://circleci.com/docs/2.0/google-auth/#creating-and-storing-a-service-account

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![Active](https://img.shields.io/badge/Status-Active-green)](https://guide.unitvectorylabs.com/bestpractices/status/#active)

# crossfiresyncrun

Provides real-time synchronization between GCP Firestore instances across regions using Pub/Sub, packaged as a Docker image for deployment on Cloud Run.

## References

- [crossfiresync](https://github.com/UnitVectorY-Labs/crossfiresync) - A Java library enabling real-time synchronization between GCP Firestore instances across regions using Pub/Sub.
- [crossfiresyncrun](https://github.com/UnitVectorY-Labs/crossfiresyncrun) - Provides real-time synchronization between GCP Firestore instances across regions using Pub/Sub, packaged as a Docker image for deployment on Cloud Run.
- [crossfiresyncrun-tofu](https://github.com/UnitVectorY-Labs/crossfiresyncrun-tofu) - A module for OpenTofu that deploys crossfiresyncrun to GCP Cloud Run, along with configuring essential services including Firestore and Pub/Sub.
- [crossfiresync-firestore](https://github.com/UnitVectorY-Labs/crossfiresync-firestore) - Reference implementation of a crossfiresync Firestore publisher, featuring Java code and deployment scripts for Cloud Functions.
- [crossfiresync-pubsub](https://github.com/UnitVectorY-Labs/crossfiresync-pubsub) - Reference implementation of a crossfiresync Pub/Sub consumer, featuring Java code and deployment scripts for Cloud Functions.

## Overview

This application is a variant of [crossfiresync](https://github.com/UnitVectorY-Labs/crossfiresync) that implements the application in Cloud Run instead of a Cloud Function. This is accomplished by utilizing the exact same logic and implementation and simply wrapping that with Spring Boot 3 and allowing that to be built as a Docker container.

## Getting Started

This Container for the most recent development version is available on GitHub Packages:

```
docker pull ghcr.io/unitvectory-labs/crossfiresyncrun:dev
```

## APIs

The implementation for crossfiresyncrun has one endpoint for receiving the events from Firestore and another for receiving events from Pub/Sub via Eventarc.

The `/firestore` endpoint receives the `google.cloud.firestore.document.v1.written` events from Eventarc.

The `/pubsub` endpoint receives the `google.cloud.pubsub.topic.v1.messagePublished` events from Eventarc.

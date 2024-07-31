# crossfiresyncrun

Real-time synchronization between GCP Firestore instances across regions using PubSub running on Cloud Run.

This application is a variant of [crossfiresync](https://github.com/UnitVectorY-Labs/crossfiresync) that implements the application in Cloud Run instead of a Cloud Function. This is accomplished by utilizing the exact same logic and implementation and simply wrapping that with Spring Boot 3 and allowing that to be built as a Docker container.


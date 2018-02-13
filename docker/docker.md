## Glossary
* Container: Running image.
* Image: Stopped container (template).
* Top-level repo: Certain images like `alpine` are official docker containers. Anything else could be security risk.
* Daemon: Server process that hosts containers.
* Client: Thin client runs commands against daemon.
* Layered file system: each image has stack of read-only file systems.
    * Layer: One level of layered file system. Is immutable. Has unique id/version. Shared between containers.
    * Container Read-Write layer: Thin top layer on stack, specific to container instance.
    * Volume: External folder mounted in container.
* Dockerfile: Docker code used to create an image.
## Instructions
* `FROM`: Derive new image from base image.
* `MAINTAINER`: Specifies author of image.
* `RUN`: Runs a command inside container. Maybe `dotnet`, `wget`, etc.
* `COPY`: Copy files into image.
* `ENTRYPOINT`: Specify base command and args. Usually main process inside image.
* `WORKDIR`: Specify a container directory context.
* `EXPOSE`: Specify a port for external networking.
* `ENV`: Declare an environment variable.
* `VOLUME`: Specify an external volume.

## Example (Production Image)
```
FROM node # Base layer is "node" image.
MAINTAINER Daniel Lillja # I am the author.

ENV NODE_ENV=production
ENV PORT=3000

COPY . /var/www # Copy build context directory to container folder.
WORKDIR /var/www # Set container working directory.
RUN npm install # Restore files needed to work.
EXPOSE 8080 # Allow connections on port.
ENTRYPOINT ["node", "server.js"] # Run server.
```
Introduction
============

This contains the Dockerfile to create the deployment image for `viewservice`. The resulting
image (`viewservice_w_proxy`) proxies `timeservice` using the **nginx** used to serve `viewservice`.  It does this by using the `location` directive to check if the URI is prefixed by `/api`. If it is, it will route the request to `timeservice` container.

Building The `viewservice` Deployment Image
-------------------------------------------
This step is required to update the config for nginx.

`docker build -t viewservice_w_proxy .`

Deploying the Images
--------------------
This will start the required containers and bind to the host's port 80.

`docker-compose up -a`
# eLabFTW Javascript demo

## Description

This example web page shows how to interact with an eLabFTW server through javascript. It requires configuring correctly the eLabFTW service to allow CORS requests.

## Configuration
In the docker-compose file (`/etc/elabftw.yml` by default), add this:

~~~yaml
# here the value must the of the service doing the request
- ALLOW_ORIGIN=http://localhost:8087
# comma separated list of methods (use GET, POST, PATCH, DELETE for full api access)
- ALLOW_METHODS=GET
- ALLOW_HEADERS=Content-Type, Authorization
~~~

Restart the service (`elabctl restart`).

## Usage

Run a local server with:

~~~bash
git clone https://github.com/elabftw/elabapi-javascript-example
cd elabapi-javascript-example
docker run --rm -v ${PWD}:/usr/share/nginx/html -p 8087:80 -d nginx
~~~

Go to http://localhost:8087 to try it out!

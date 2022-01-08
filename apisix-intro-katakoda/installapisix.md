# Step 1: Install Apache APISIX#

Thanks to Docker, we can start Apache APISIX and enable it by enabling Admin API.

```bash
# Download the Docker image of Apache APISIX
git clone https://github.com/apache/apisix-docker.git
# Switch the current directory to the apisix-docker/example path
cd apisix-docker/example
# Run the docker-compose command to install Apache APISIX
docker-compose -p docker-apisix up -d
```

> Apache APISIX has already supported ARM64 architecture. For ARM64 users, please use `docker-compose -p docker-apisix -f docker-compose-arm64.yml up -d` instead in the last step.

It will take some time to download all required files, please be patient.

Once the download is complete, execute the `curl` command on the host running Docker to access the Admin API, and determine if Apache APISIX was successfully started based on the returned data.

```bash
# Note: Please execute the curl command on the host where you are running Docker.
curl "http://127.0.0.1:9080/apisix/admin/services/" -H 'X-API-KEY: edd1c9f034335f136f87ad84b625c8f1'
```

The following data is returned to indicate that Apache APISIX was successfully started:

```json
{
  "count": 1,
  "action": "get",
  "node": { "key": "/apisix/services", "nodes": {}, "dir": true }
}
```

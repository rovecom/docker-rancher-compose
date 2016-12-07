# docker-rancher-compose

Docker image with rancher-compose installed.

Rancher Compose is a docker-compose compatible client that deploys to Rancher.

More information on the official Rancher documentation: http://rancher.docs.rancher.com/docs/rancher-compose/ and on the Rancher Compose GitHub repository: https://github.com/rancher/rancher-compose

# Where to find the Rancher Compose Images
https://hub.docker.com/r/rovecom/rancher-compose/

# How do you use this image?

**Not interactive and basic mode:**

Just run it as a normal command, sharing the directory containing your docker-compose.yml file and your rancher-compose.yml file:

```bash
$ docker run -v /absolute/path/to/project/dir/:/app:ro \
             -e "RANCHER_URL=http://<rancher_server_ip>:<rancher_server_port>" \
             --rm \
             rovecom/rancher-compose:latest --help
```

**Not interactive with custom docker-compose file, rancher-compose file and project name:**

Add the -f, -r, -p options

```bash
$ docker run -v /absolute/path/to/project/dir/:/app:ro \
             -e "RANCHER_URL=http://<rancher_server_ip>:<rancher_server_port>/v1" \
             --rm \
             rovecom/rancher-compose:latest \
             -f "<docker_compose_file_name>.yml" \
             -r "<rancher_compose_file_name>.yml" \
             -p "<project_name>" \
             --help
```

**Not interactive with access control:**

Set the RANCHER_ACCESS_KEY and RANCHER_SECRET_KEY environment variables

```bash
$ docker run -v /absolute/path/to/project/dir/:/app:ro \
             -e "RANCHER_URL=http://<rancher_server_ip>:<rancher_server_port>/v1" \
             -e "RANCHER_ACCESS_KEY=<rancher_access_key>" \
             -e "RANCHER_SECRET_KEY=<rancher_secret_key>" \
             --rm \
             rovecom/rancher-compose:latest --help
```


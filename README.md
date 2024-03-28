# Using multiple databases with the official PostgreSQL Docker image

This is the implementation of the [official recommendation](https://hub.docker.com/_/postgres/) for creating multiple databases.

This repository contains a docker compose file with placeholders in mustache implementation with bash script to create multiple databases with minor improvement for granting privileges to related database user using that mechanism.

## Usage

### By mounting a volume

Clone the repository, replace the placeholder values in the `docker-compose.yml` file.

### By building a custom image

Clone the repository, replace the placeholder values with current, build and push the image to your Docker repository,
for example for Google Private Repository do the following:

    docker build --tag=eu.gcr.io/<project_name>/<image_name> .
    gcloud docker -- push eu.gcr.io/<project_name>/<image_name>

### Non-standard database names

If you need to use non-standard database names (hyphens, uppercase letters etc), quote them on this way in docker compose file:
`- POSTGRES_MULTIPLE_DATABASES: "non-standard-db-name-1","non-standard-db-name-2"`

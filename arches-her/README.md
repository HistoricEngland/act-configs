# arches-her configurations

This repository contains configurations for the Arches Container Tool to create development environments for Arches HER. These configurations are maintained by HE for use by this team, but are made available here for use by anyone in the Arches community who may find them useful. If you would like to contribute to these configurations, please see the Contributing section in the main README.

## Using these configurations

Refer to the main README for instructions on how to use these configurations with the Arches Container Tool. The main README also contains information on how to contribute to this repository if you would like to add new configurations or update existing ones.

## Additional information

> Where non-standard or additional information is useful for the developer, they will be nboted below.

1. The entrypoint script for arches-her has been modified to run the load_package command as part of the database setup process that runs when first using `act up`, leading to a longer than usual start time-to-first-use.
2. To avoid conflicts with other Arches Container Tool configurations, the following changes to the docker-compose files have been applied:
   - volumes have been suffixed with `-afher11`
   - image name has been suffixed with `_11` so it is now `he/arches_her:dev_build_1.1`.

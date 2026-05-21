# Arches Search Configuration

This repository contains configurations for the Arches Container Tool to create development environments for Arches Search. These configurations are maintained by HE for use by this team, but are made available here for use by anyone in the Arches community who may find them useful. If you would like to contribute to these configurations, please see the Contributing section in the main README.

## Using these configurations

Refer to the main README for instructions on how to use these configurations with the Arches Container Tool. The main README also contains information on how to contribute to this repository if you would like to add new configurations or update existing ones.

### Importing configurations into your workspace

The project name for the Arches Search configurations is `arches_search`. To import a configuration for a specific version of Arches Search, use the following command from your workspace root, replacing `<version number>` with the relevant version (e.g. `1.0`):

```sh
act import -p arches_search -r ./act-configs/arches-search/<version number>
``` 

## Additional setup steps

None noted.
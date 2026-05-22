# Arches Rascolls Configuration

This repository contains configurations for the Arches Container Tool to create development environments for Arches Rascolls. These configurations are maintained by HE for use by this team, but are made available here for use by anyone in the Arches community who may find them useful. If you would like to contribute to these configurations, please see the Contributing section in the main README.

## Using these configurations

Refer to the main README for instructions on how to use these configurations with the Arches Container Tool. The main README also contains information on how to contribute to this repository if you would like to add new configurations or update existing ones.

### Importing configurations into your workspace

The project name for the Arches Rascolls configurations is `arches_rascolls`. To import a configuration for a specific version of Arches Rascolls, use the following command from your workspace root, replacing `<version number>` with the relevant version (e.g. `1.0`):

```sh
act import -p arches_rascolls -r ./act-configs/arches-rascolls/<version number>
``` 

## Additional setup steps

It was noted that when ACT atarts, the service check is receiving a 302 response instead of a 200 response, which is causing the service check to fail. This is likely due to the fact that the service check is not following redirects, and the application is redirecting to a different URL. To resolve this issue, you can try updating the service check to follow redirects, or you can update the application to return a 200 response instead of a 302 response for the service check URL.

Check the logs using `act logs` to see that the service is responding with 302, and if so use Ctrl+C to exit the service availability check.  You should then be able to use `act view` to open the site.
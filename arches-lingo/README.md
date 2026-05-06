# arches-lingo configurations

This repository contains configurations for the Arches Container Tool to create development environments for Arches Lingo. These configurations are maintained by HE for use by this team, but are made available here for use by anyone in the Arches community who may find them useful. If you would like to contribute to these configurations, please see the Contributing section in the main README.

## Using these configurations

Refer to the main README for instructions on how to use these configurations with the Arches Container Tool. The main README also contains information on how to contribute to this repository if you would like to add new configurations or update existing ones.

### Importing configurations into your workspace

The project name for the Arches Lingo configurations is `arches_lingo`. To import a configuration for a specific version of Arches Lingo, use the following command from your workspace root, replacing `<version number>` with the relevant version (e.g. `1.1`):

```sh
act import -p arches_lingo -r ./act-configs/arches-lingo/<version number>
```

## Additional setup steps

You'll need to load the Arches Lingo package, and optionally the example FISH thesauri data, into your database after importing the configuration. You can do this with the following commands:

```sh
act shell --exec "python manage.py packages -o load_package -a arches_lingo --yes -db"
```

(Optional) To load the example FISH thesauri data, run:

```sh
act shell --exec "python manage.py loaddata tests/fixtures/data/FISH_Example_Thesauri.json.xz"
```

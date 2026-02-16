# act-configs
A collection of arches-container tool configurations that are unable to sit in the related Arches repo as they don't belong to Historic England

## arches container tool

To use these configurations, you will need to have the Arches Container Tool installed. You can find more information about the tool and how to install it in the [Arches Container Tool documentation](https://pypi.org/project/arches-containers/).

The Arches Container Tool is a CLI tool that provides a set of commands to create Arches development environments using Docker containers. It is designed to simplify the process of setting up and managing Arches development environments, allowing developers to focus on their work without worrying about the underlying infrastructure.

## Configurations

Configurations are organised in this repository by repo and version to allow for multiple versions to sit in the same branch. For example, the configuration for Arches HER version 1.1 is located in `act-configs/arches-her/1.1`.

## Usage

To use these configurations, clone this repository to your local workspace so that they are available to Arches Container Tool. Use the import and export commands to use, create and update configurations in this repository.  

### Importing configurations into your workspace

Once you have installed the Arches Container Tool, you can import the configurations from this repository into your workspace directory using the `act import` command. For example, to import the Arches HER 1.1 configuration, you would run the following command from your workspace root:

```sh
act import -p arches_her -r ./act-configs/arches-her/1.1
```

This will copy the configuration files from the `act-configs/arches-her/1.1` directory into the `.arches_containers/arches_her` directory in your workspace, allowing you to use the Arches Container Tool to create and manage your Arches HER development environment.

### Exporting configurations from your workspace

If you have made changes to the configurations in your workspace, or created a new one, and want to export them back to this repository to share with others, you can use the `act export` command. For example, to export the Arches HER configuration, you would run the following command from your workspace:

```sh
act export -p arches_her -r ./act-configs/arches-her/1.1
```

If you are creating a configuration for a new version of the target application, you need to create a new directory for that version in this repository before running the export command. For example, if you are creating a configuration for Arches HER version 1.2, you would create a new directory at `act-configs/arches-her/1.2` and then run the export command with that path:

```sh
act export -p arches_her -r ./act-configs/arches-her/1.2
```

### Example usage

Here is an example of setting up a work space with the Arches HER 1.1 configuration:

```sh
# Create a new workspace directory and navigate into it
mkdir my-arches-her-workspace
cd my-arches-her-workspace

# Create a virtual environment for your workspace
python -m venv venv
source ./venv/bin/activate

# Install the Arches Container Tool in your workspace
pip install arches-containers

# Clone this repository to your local workspace so that the configurations are available to Arches Container Tool
git clone https://github.com/HistoricEngland/act-configs.git

# Clone the Arches HER repository to your local workspace
git clone https://github.com/HistoricEngland/arches-her.git arches_her

# Import the Arches HER 1.1 configuration into your workspace
act import -p arches_her -r ./act-configs/arches-her/1.1

# Intialize the Arches Container Tool configuration and start the containers for the Arches HER development environment
act init
act up

```

## Contributing

If you would like to contribute to this repository, please fork the repository and create a pull request with your changes. We welcome contributions of all kinds, including new configurations, updates to existing configurations, and improvements to the documentation.

When contributing new or updated configurations, please ensure that they are well-documented and tested. This will help other developers understand how to use the configurations and ensure that they work as expected.

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

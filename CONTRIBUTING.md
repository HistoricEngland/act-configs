# Contributing to act-configs

Thank you for your interest in contributing to the act-configs repository! We welcome contributions of all kinds, including new configurations, updates to existing configurations, and improvements to the documentation.

## Table of Contents

- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
  - [Reporting Issues](#reporting-issues)
  - [Contributing New Configurations](#contributing-new-configurations)
  - [Updating Existing Configurations](#updating-existing-configurations)
  - [Improving Documentation](#improving-documentation)
- [Development Workflow](#development-workflow)
- [Testing Your Changes](#testing-your-changes)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Code of Conduct](#code-of-conduct)

## Getting Started

Before you begin contributing, please:

1. **Read the README**: Familiarize yourself with the [README.md](README.md) to understand the purpose of this repository and how to use the Arches Container Tool.

2. **Set up your environment**: Follow the example usage in the README to set up a workspace with the Arches Container Tool.

3. **Install the Arches Container Tool**: You'll need the Arches Container Tool installed to work with configurations. See the [Arches Container Tool documentation](https://pypi.org/project/arches-containers/) for installation instructions.

## How to Contribute

### Reporting Issues

If you encounter any issues with the configurations or have suggestions for improvements:

1. Check the [existing issues](https://github.com/HistoricEngland/act-configs/issues) to see if it has already been reported.
2. If not, create a new issue with a clear description of the problem or suggestion.
3. Include relevant details such as:
   - The configuration you're using (e.g., arches-her/1.1)
   - Steps to reproduce the issue
   - Expected vs. actual behavior
   - Your environment (OS, Docker version, Arches Container Tool version)

### Contributing New Configurations

If you want to add a configuration for a new version or application:

1. **Create the directory structure**: Create a new directory following the pattern `<application-name>/<version>`. For example: `arches-her/1.2`.

2. **Export your configuration**: Use the `act export` command to export your configuration from your workspace:
   ```sh
   act export -p <project_name> -r ./act-configs/<application-name>/<version>
   ```

3. **Document your configuration**: Add or update a README.md in the application directory (e.g., `arches-her/README.md`) with:
   - Instructions on how to use the configuration
   - Any non-standard setup steps
   - Compatibility information
   - Special considerations or known issues

4. **Test thoroughly**: Ensure your configuration works as expected (see [Testing Your Changes](#testing-your-changes)).

### Updating Existing Configurations

If you want to update an existing configuration:

1. **Import the configuration**: Import the existing configuration into your workspace:
   ```sh
   act import -p <project_name> -r ./act-configs/<application-name>/<version>
   ```

2. **Make your changes**: Modify the configuration in your workspace using the Arches Container Tool commands.

3. **Export the updated configuration**: Export your changes back to this repository:
   ```sh
   act export -p <project_name> -r ./act-configs/<application-name>/<version>
   ```

4. **Document your changes**: Update the relevant README files to reflect your changes.

5. **Test thoroughly**: Ensure your changes work as expected and don't break existing functionality.

### Improving Documentation

Documentation improvements are always welcome! This includes:

- Clarifying existing documentation
- Adding examples
- Fixing typos or grammar
- Adding missing information

When updating documentation, ensure that:
- Instructions are clear and easy to follow
- Examples are accurate and tested
- Links are working and point to the correct resources

## Development Workflow

1. **Fork the repository**: Click the "Fork" button on the [act-configs repository](https://github.com/HistoricEngland/act-configs).

2. **Clone your fork**:
   ```sh
   git clone https://github.com/YOUR-USERNAME/act-configs.git
   cd act-configs
   ```

3. **Create a branch**: Create a new branch for your changes:
   ```sh
   git checkout -b your-branch-name
   ```

4. **Make your changes**: Follow the guidelines above for the type of contribution you're making.

5. **Commit your changes**: Write clear, descriptive commit messages:
   ```sh
   git add .
   git commit -m "Add configuration for Arches HER 1.2"
   ```

6. **Push to your fork**:
   ```sh
   git push origin your-branch-name
   ```

## Testing Your Changes

Before submitting your contribution, please test your changes thoroughly:

### For New or Updated Configurations

1. **Start fresh**: Create a new workspace directory for testing.

2. **Import the configuration**: Import your configuration into the test workspace:
   ```sh
   act import -p <project_name> -r ./path/to/your/act-configs/<application>/<version>
   ```

3. **Initialize and start**: Initialize and start the containers:
   ```sh
   act init
   act up
   ```

4. **Verify functionality**: Ensure that:
   - Containers start without errors
   - The application is accessible and functional
   - All expected services are running
   - Any custom scripts or entrypoints work as expected

5. **Test clean-up**: Test that `act down` and `act clean` commands work properly.

### For Documentation Changes

1. **Review for accuracy**: Ensure all instructions and examples are accurate.
2. **Check links**: Verify that all links work and point to the correct resources.
3. **Test examples**: If possible, test any code examples or commands included in your documentation.

## Submitting a Pull Request

When you're ready to submit your contribution:

1. **Push your changes**: Ensure all your changes are pushed to your fork.

2. **Create a pull request**: Go to the [act-configs repository](https://github.com/HistoricEngland/act-configs) and click "New pull request".

3. **Select your branch**: Choose your fork and branch as the source.

4. **Provide a clear description**: In your pull request description, include:
   - What changes you've made
   - Why you've made them
   - How to test the changes
   - Any related issue numbers (e.g., "Fixes #123")

5. **Be responsive**: Be prepared to respond to feedback and make adjustments if requested.

6. **Be patient**: Maintainers will review your contribution as soon as possible.

## Code of Conduct

By contributing to this repository, you agree to:

- Be respectful and inclusive in all interactions
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards other community members

We are committed to providing a welcoming and inclusive environment for all contributors, regardless of their background or experience level.

---

Thank you for contributing to act-configs! Your contributions help make this resource better for everyone in the Arches community.

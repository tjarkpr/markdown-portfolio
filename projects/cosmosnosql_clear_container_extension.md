# CosmosNoSQL Clear Container Extension (CCE)

**Author:** [Tjark Prokoph](https://github.com/tjarkpr)  
**Repository:** [github.com/tjarkpr/cosmosnosql-clear-container-extension](https://github.com/tjarkpr/cosmosnosql-clear-container-extension)

## Overview

The CosmosNoSQL Clear Container Extension (CCE) is a Visual Studio Code (VS Code) extension designed to provide a straightforward and user-friendly method for clearing all documents from Azure Cosmos DB NoSQL (formerly known as Global DocumentDB) containers. This tool is particularly useful for developers who need to reset container contents during development or testing phases.

## Features

- **One-Click Clearing**: Quickly remove all documents from a selected Cosmos DB NoSQL container directly within VS Code.
- **User-Friendly Interface**: Intuitive UI elements integrated into VS Code for seamless operation.
- **Safe Operations**: Designed to prevent accidental data loss with confirmation prompts before clearing operations.
- **Lightweight Extension**: Minimal impact on system resources, ensuring smooth performance.

## Installation

To install the CosmosNoSQL CCE extension:

1. Open **Visual Studio Code**.
2. Navigate to the **Extensions** view by clicking on the Extensions icon in the Activity Bar on the side of the window.
3. Search for `CosmosNoSQL Clear Container Extension`.
4. Click **Install** to add the extension to your VS Code environment.

## Usage

After installation:

1. Open the Command Palette by pressing `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS).
2. Type `CosmosNoSQL: Clear Container` and select the command.
3. Choose the target Cosmos DB NoSQL container from the list.
4. Confirm the action when prompted to clear all documents from the selected container.

## Repository Structure

- **`src/`**: Contains the source code for the extension, including activation scripts and command implementations.
- **`resources/`**: Holds assets such as icons and images used in the extension's UI.
- **`.vscode/`**: Configuration files for VS Code development environment settings.
- **`package.json`**: Defines the extension's metadata, dependencies, and activation events.
- **`tsconfig.json`**: TypeScript configuration file specifying compiler options.
- **`README.md`**: Provides documentation and usage instructions for the extension.
- **`LICENSE.txt`**: Specifies the MIT License under which the extension is distributed.

## Contributing

Contributions are welcome! If you encounter issues or have suggestions for improvements, feel free to open an issue or submit a pull request on the [GitHub repository](https://github.com/tjarkpr/cosmosnosql-clear-container-extension).

## License

This project is licensed under the MIT License. For more details, refer to the [LICENSE.txt](https://github.com/tjarkpr/cosmosnosql-clear-container-extension/blob/main/LICENSE.txt) file in the repository.

---

By providing a simple and efficient way to clear documents from Cosmos DB NoSQL containers, the CosmosNoSQL Clear Container Extension enhances the development workflow for developers working with Azure's NoSQL offerings.
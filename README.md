# HuggingFace Workspace

Welcome to the Agents Course workspace. This repository is configured with a development container (devcontainer) that helps standardize the development environment and streamline onboarding.

## Devcontainer

The devcontainer is set up to provide:
- A consistent development environment regardless of the host OS.
- Pre-installed dependencies and tools to support development.
- Seamless integration with VSCode via the Dev Containers extension.

**How it Works:**
- The devcontainer configuration files (typically found in the `.devcontainer` folder) define the container environment.
- When you open this workspace in VSCode with the Dev Containers extension, you will be prompted to reopen the folder inside the container.
- This allows you to run and debug code in a predictable environment without manual setup.

**Note:** Make sure you have the VSCode Dev Containers plugin installed for a smooth setup:
- Open VSCode Extensions view (`Ctrl+Shift+X` or `Cmd+Shift+X`).
- Search for **Dev Containers** and install the extension provided by Microsoft.

**Note for Windows users:** Some of the file paths in the `devcontainer.json` file (for example, in the "mounts" configuration) may need to be adjusted to match Windows path formats.

## Getting Started

1. **Install VSCode and the Dev Containers Plugin:**
   - Download and install [Visual Studio Code](https://code.visualstudio.com/).
   - Install the **Dev Containers** plugin from the Extensions Marketplace.

2. **Setup Environment Variables:**
   - Locate the `.env.example` file in the root of the repository.
   - Copy or rename `.env.example` to `.env`.
   - Open the `.env` file and add the required key(s) as specified in the file comments.

3. **Open the Repository in the Devcontainer:**
   - Open the workspace in VSCode.
   - When prompted, choose to *Reopen in Container*. This will build the container based on the configuration provided in the `.devcontainer` folder.
   - Once the container is ready, you can start developing within the standardized environment.

## Additional Information

- **Repository Structure:**  
  Outline the major directories and files in this workspace.

- **Usage & Conventions:**  
  Brief notes on coding standards, commit message guidelines, and branch naming conventions.

- **Troubleshooting:**  
  Common issues with the devcontainer setup and links to relevant documentation/resources.

- **Dependency Management:**  
  This workspace uses `uv` to manage dependencies and install external packages. Commands such as `uv venv`, `uv sync --dev`, and `uv pip install -e .` in the devcontainer ensure that all necessary dependencies are installed.

- **VSCode Settings:**  
  The VSCode settings file is configured with Python type checking set to strict to catch potential issues early. Users can adjust this setting to a lower strictness level if desired.

- **Local Cache Mount for HuggingFace:**  
  The container mounts the local HuggingFace cache into the container to allow reuse of tokens or transformers already installed. If you do not want this behavior, remove or comment out the "mounts" array in the `devcontainer.json` file. For example:
  ```jsonc
  // "mounts": [
  //     "source=${localEnv:HOME}/.cache/huggingface,target=/opt/hf,type=bind,consistency=cached"
  // ],
  ```

Happy coding!
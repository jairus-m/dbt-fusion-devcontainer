# dbt Fusion DevContainer Template

A development container template for dbt projects that use the new fusion engine with additional tools and configurations.

## Features
- Official dbt VS Code Extension (also compatible with Cursor)
- Base Python development environment / tools
  - uv, ruff, ty
- Git
- Can configure other useful extensions
- Pre-configured settings for SQL, YAML, and Python

## Usage

### Option 1: Using the Template Directly

1. Clone this repository:
   ```bash
   git clone https://github.com/jairus-m/dbt-fusion-devcontainer.git
   ```

2. Copy the template files to your project:
   ```bash
   cp -r dbt-fusion-devcontainer/src/dbt-fusion/.devcontainer your-project/
   ```

3. Open your project in VS Code and use the Dev Containers extension to build and run the container.

### Option 2: Using the Container Image

1. Add the following to your project's `.devcontainer/devcontainer.json`:
   ```json
   {
     "image": "ghcr.io/jairus-m/dbt-fusion-devcontainer/dbt-fusion:latest",
     "customizations": {
       "vscode": {
         "extensions": [
           "ms-python.python",
           "charliermarsh.ruff",
           "ms-python.vscode-pylance",
           "tamasfe.even-better-toml",
           "EditorConfig.EditorConfig",
           "eamodio.gitlens",
           "github.vscode-pull-request-github",
           "visualstudioexptteam.vscodeintellicode",
           "dbtlabsinc.dbt",
           "redhat.vscode-yaml"
         ]
       }
     }
   }
   ```

   > **Note**: The extensions are not pre-installed in the container. They are installed by VS Code when the container starts. This is the recommended approach as it allows for better extension management and updates.

2. Open your project in VS Code and use the Dev Containers extension to build and run the container.

## Configuration Options

> **Note**: These options are only prompted when using Option 1 (Template Directly) through VS Code's "Add Development Container Configuration Files" command. When using Option 2 (Container Image), these settings are pre-configured in the image.

- `imageVariant`: Choose between Debian bullseye (recommended for Apple Silicon) or bookworm
- `pythonVersion`: Select Python version (3.12, 3.11, or 3.10)

## Requirements

- Docker
- VS Code with Dev Containers extension
- Git

## Development

To test the template locally:

```bash
# Run the test script
./test/dbt-fusion/test.sh
```

## Version History
- 1.0.2: Docs update
- 1.0.1: Added pre-configured VS Code extensions and settings
- 1.0.0: Initial release

## License

MIT License 

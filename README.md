# dbt Fusion DevContainer Template

A development container template for dbt projects that use the new fusion engine with additional tools and configurations.

## Requirements
- Docker Desktop
- VS Code with Dev Containers (or Remote Explorer) extension
- A `dbt-fusion` project that parses and compiles succesfully!

## Features
- Official dbt VS Code Extension (also compatible with Cursor)
- Base Python development environment / tools
  - uv, ruff, ty
- Git
- Can configure other useful extensions
- Pre-configured settings for SQL, YAML, and Python

## Usage

### Reccomended: Using the Container Image

1. Add the following to your project's `.devcontainer/devcontainer.json`:
   ```json
   {
     "image": "ghcr.io/jairus-m/dbt-fusion-devcontainer/dbt-fusion:latest",
     "remoteUser": "vscode",
     "mounts": [
       "source=${localEnv:HOME}/.dbt,target=/home/vscode/.dbt,type=bind",
       "source=${localEnv:HOME}/.ssh,target=/home/vscode/.ssh,type=bind"
     ],
     "workspaceMount": "source=${localWorkspaceFolder},target=/workspaces/${localWorkspaceFolderBasename},type=bind,consistency=cached",
     "workspaceFolder": "/workspaces/${localWorkspaceFolderBasename}",
     "customizations": {
       "vscode": {
         "settings": {
           "dbt.dbtPath": "/home/vscode/.local/bin/dbt",
           "files.associations": {
             "*.sql": "sql",
             "*.yml": "yaml"
           },
           "[sql]": {
             "editor.defaultFormatter": "dbtLabsInc.dbt",
             "editor.formatOnSave": true
           },
           "[yaml]": {
             "editor.defaultFormatter": "dbtLabsInc.dbt",
             "editor.formatOnSave": true
           },
           "[python]": {
             "editor.defaultFormatter": "charliermarsh.ruff",
             "editor.formatOnSave": true
           }
         },
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
     },
     "features": {
       "ghcr.io/devcontainers/features/common-utils:2": {
         "installZsh": true,
         "username": "vscode",
         "upgradePackages": true
       },
       "ghcr.io/devcontainers/features/python:1": {
         "version": "3.12",
         "installTools": true
       }
     }
   }
   ```

   > **Note**: The extensions are installed by VS Code when the container starts for ease of setup. To remove this configuration, remove the `"features"` key from the `devcontainer.json` file to manage the extension installation yourself.

2. Open your project in VS Code and use the Dev Containers (or Remote Explorer) extension to build and run the container.


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

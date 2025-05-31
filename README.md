# dbt Fusion DevContainer Template

A development container template for dbt projects that use the new fusion engine with additional tools and configurations.

## Features

- Python development environment
- dbt tools and extensions
- Git integration
- Code formatting and linting tools
- VS Code extensions for dbt development
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
     "image": "ghcr.io/jairus-m/dbt-fusion-devcontainer/dbt-fusion:latest"
   }
   ```

2. Open your project in VS Code and use the Dev Containers extension to build and run the container.

## Configuration Options

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

- 1.0.1: Added pre-configured VS Code extensions and settings
- 1.0.0: Initial release

## License

MIT License 

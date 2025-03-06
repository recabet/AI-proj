# Conda Environment Setup

This repository includes an environment file (`environment.yaml`) to set up a Conda environment with all necessary dependencies.

## Installation

### 1. Create the Conda Environment
Run the following command to create the environment:

```bash
    conda env create -f environment.yaml
```

### 2. Activate the Environment
After installation, activate the environment with:

```bash 
    conda activate <env_name>
    
```
Replace `<env_name>` with the actual name of the environment specified in `environment.yaml`.

### 3. Verify Installation
Check if the environment is correctly installed by listing the environments:

```bash 
    conda env list
```

To check installed packages inside the environment:

```bash
    conda list
```

## Updating the Environment
If changes are made to `environment.yaml`, update the existing environment with:

```bash
    conda env update --file environment.yaml --prune
```

## Removing the Environment
To remove the Conda environment completely, use:

```bash
    conda env remove --name <env_name>
    
```

For more details on Conda environments, visit the [Conda documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/ma
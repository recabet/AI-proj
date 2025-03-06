# Conda Environment Setup

This repository includes an environment file (`environment.yaml`) to set up a Conda environment with all necessary dependencies.

## Installation

### 1. Create the Conda Environment
Run the following command to create the environment:

```bash
  cd environments && conda env create -f <os>_environment.yaml
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

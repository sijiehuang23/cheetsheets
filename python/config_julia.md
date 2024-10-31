# Configuring Julia to Work with Python

To enable calling Julia from Python, follow these steps:

1. **Create Separate Environments**: Set up two separate conda environments—one for Julia (`env_julia`) and one for Python (`env_python`).
   ```bash
   conda create -n env_julia
   conda create -n env_python
   ```

2. **Install Julia**:
   - Activate the Julia environment:
     ```bash
     conda activate env_julia
     ```
   - Install Julia via conda:
     ```bash
     conda install -c conda-forge julia
     ```

3. **Install `PyCall` in Julia** 
   -  Activate Julia REPL by simply typing `julia` in command line
   -  

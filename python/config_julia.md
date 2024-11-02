# Configuring Julia to Work with Python

To enable calling Julia from Python, follow these steps:

1. **Create Separate Environments**: Set up two separate conda environments—one for Julia (`env_julia`) and one for Python (`env_python`):
   ```bash
   conda create -n env_julia
   conda create -n env_python
   ```

2. **Install Julia**:
   - Activate `env_julia` and install Julia:
     ```bash
     conda activate env_julia
     conda install -c conda-forge julia
     ```

3. **Install `PyCall` in Julia**:
   - Launch Julia by typing `julia` in the command line, then run:
     ```julia
     ENV["PYTHON"] = "/path/to/conda/envs/env_python/bin/python"
     import Pkg
     Pkg.add("PyCall")
     Pkg.build("PyCall")
     ```
     *Note*: Some warnings related to `@ Downloads.Curl` may appear but can be ignored.
   - Verify `PyCall` by running:
     ```julia
     using PyCall
     println(PyCall.python)  # Should print the path to `env_python`'s Python
     ```

4. **Install `PyJulia` in Python**:
   - Switch to `env_python`:
     ```bash
     conda deactivate
     conda activate env_python
     ```
   - Install `PyJulia`:
     ```bash
     pip install julia
     ```
   - Configure PyJulia in Python by entering the Python REPL:
     ```python
     import julia
     julia.install()
     ```
   - Test the setup by running:
     ```python
     from julia import Main
     print(Main.eval("2 + 2"))  # Should output "4"
     ```
      **Note**: If you see a message about a statically linked Python interpreter, use `compiled_modules=False` when initializing `Julia` as shown above, or alternatively, use `python-jl`:
      ```bash
      $ python-jl PATH/TO/YOUR/SCRIPT.py
      ```
   - Overall, one should always do
     ```python
     from julia.api import Julia
     jl = Julia(compiled_modules=False)  # Avoids issues with static linking
     from julia import Main
     print(Main.eval("2 + 2"))  # Should output "4"
     ```
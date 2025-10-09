---
layout: page
title: "Setting Up Python with Conda"
description: 
permalink: /teaching/course2/instructions/
---

Before starting the coding tasks in this course, it is important to have a proper Python environment. Conda is a popular tool for managing Python versions, packages, and environments. Using Conda ensures that your code works consistently, avoids conflicts between packages, and makes it easier to reproduce results on any computer.

<div style="border-left: 3px solid #0e69d0; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #0e69d0; font-weight: bold;">ℹ️ Note</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  You do not need to install Python separately if you are using Anaconda or Miniconda. Conda automatically manages Python installations inside each environment. Each environment can have its own Python version, completely isolated from the system Python.
  </span>
</div>

<div style="height: 20px;"></div>

### Step 1: Install Conda

You have two main options:

- **Anaconda:** Includes Python, Conda, Jupyter Notebook, and many scientific packages pre-installed.
  - Recommended if you want a ready-to-use setup for scientific computing. 
  - [Download Anaconda](https://www.anaconda.com/products/distribution)
- **Miniconda:** Minimal installation with Python and Conda only.
  - Recommended if you want a smaller installation and prefer to install only the packages you need. 
  - [Download Miniconda](https://docs.conda.io/en/latest/miniconda.html)

### Step 2: Open a Conda-enabled terminal

- **Windows:**  
  - Use **Anaconda Prompt** (installed with Anaconda/Miniconda).  
  - Alternatively, use **PowerShell** or **Command Prompt** if Conda was added to PATH.
- **macOS/Linux:**  
  - Open your regular **Terminal** app.  
  - If this is the first time using Conda, initialize it by running:  
    ```bash
    conda init
    ```  
    Then restart the terminal.

<div style="border-left: 3px solid #0e69d0; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #0e69d0; font-weight: bold;">ℹ️ Note</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  After opening the terminal, you should see <code>(base)</code> at the start of the prompt. This indicates the base Conda environment is active. Activating the correct environment ensures your code uses the right packages and versions.
  </span>
</div>

<div style="height: 20px;"></div>

### Step 3: Create a new environment

It is highly recommended to create a **separate environment** for this course to avoid conflicts with other projects:
```bash
conda create -n npde_env python=3.10
```
where
- `npde_env` is the name of the environment. You can choose any name you like.
- `python=3.10` ensures compatibility with the course exercises.

<div style="border-left: 3px solid #0e69d0; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #0e69d0; font-weight: bold;">ℹ️ Note</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  You may choose a different Python version (e.g., <code>python=3.11</code>) or omit the version entirely. Newer versions may work, but some packages or examples could potentially be incompatible. Omitting the version installs the latest Python from your Conda channels, which may cause minor issues. Specifying <code>python=3.10</code> ensures a consistent and reliable environment.
  </span>
</div>

<div style="height: 20px;"></div>

### Step 4: Activate the environment

After creating your environment, you need to **activate it** before using it. To activate the environment:
```bash
conda activate npde_env
```
After running this command, your terminal prompt will change to something like:
```scss
(npde_env) C:\Users\YourName>
```
or on macOS/Linux:
```ruby
(npde_env) your-computer:~$
```
The part in parentheses `(npde_env)` indicates that the `npde_env` environment is currently active.

<div style="border-left: 3px solid #FFC107; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #FFC107; font-weight: bold;">⚠️ Warning</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  Always make sure the correct environment is active before running Python code for this course. If you forget to activate it, your code may use packages from the <code>base</code> environment, which can lead to errors or inconsistent results.
  </span>
</div>

<div style="height: 20px;"></div>

When you are done working, you can deactivate the environment:
```bash
conda deactivate
```
The terminal prompt will return to `(base)` or your default system prompt. Deactivating an environment does **not** delete it; it simply stops using it until you activate it again.

### Step 5: Install required packages

Once your environment `npde_env` is active, you need to install the Python packages required for this course. These packages provide the tools to perform numerical computations, visualizations, and scientific calculations.

**Option 1: Default Conda channel**
```bash
conda install numpy matplotlib scipy
```
**Option 2: Conda-Forge (recommended for latest versions)**
```bash
conda install -c conda-forge numpy matplotlib scipy
```

<div style="border-left: 3px solid #FFC107; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #FFC107; font-weight: bold;">⚠️ Warning</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  Make sure your environment <code>npde_env</code> is active when installing packages. Installing in the wrong environment (or in <code>base</code>) can cause version conflicts or unexpected behavior.
  </span>
</div>

<div style="height: 20px;"></div>

### Step 6: Verify installation

After installing the required packages, verify that everything is working correctly. This helps catch any installation or configuration issues early.

With your `npde_env` environment active, open Python in the terminal:
```bash
python
```
On Windows (Anaconda/Miniconda Python), you may see:
```pgsql
Python 3.10.12 (tags/v3.10.12:aa12345, Jul  5 2025, 12:34:56) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
On Linux/macOS, you may see:
```csharp
Python 3.10.12 (default, Jul  5 2025, 12:34:56)
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
where
- `Python 3.10.12` indicates the Python version installed in your environment.
- `[MSC v.1934 64 bit (AMD64)]` or `[GCC ...]` shows the compiler used to build Python.
- `>>>` is the Python prompt, ready to accept commands.

<div style="border-left: 3px solid #0e69d0; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #0e69d0; font-weight: bold;">ℹ️ Note</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  The exact version and build may vary slightly depending on your Conda installation, but as long as the prompt shows <code>>>></code> and the correct Python version, your environment is ready.
  </span>
</div>

<div style="height: 20px;"></div>

At the Python prompt, type the following:

```python
import numpy as np
import matplotlib.pyplot as plt
import scipy

print("All packages installed correctly!")
```
If no errors appear, the packages are installed correctly, and you are ready to run Python code in this environment. If an error occurs, it typically indicates a missing package or a version conflict, and you will need to check your environment and installation before proceeding.

When you are done, you can exit Python using any of the following methods:
- Using a function:
```python
>>> exit()
```
or
```python
>>> quit()
```
- Using a keyboard shortcut:
    - Windows/Linux: `Ctrl + Z` then press `Enter`
    - macOS: `Ctrl + D`

After quitting, your terminal prompt will return to the Conda environment prompt, e.g.:
```scss
(npde_env) C:\Users\YourName>
```
or
```ruby
(npde_env) your-computer:~$
```

<div style="border-left: 3px solid #FFC107; background-color: transparent; padding-left: 15px; border-radius: 2px;">
  <span style="color: #FFC107; font-weight: bold;">⚠️ Warning</span><br>
  <span style="margin-top: 5px; display: inline-block;">
  Make sure your <code>npde_env</code> environment is active when running Python. If you accidentally run Python in another environment (like <code>base</code>), your packages may not be available or may be different versions, leading to errors or inconsistent results.
  </span>
</div>

<div style="height: 20px;"></div>

### Managing Conda Environments (Optional / Tips)

#### List all Conda environments

To see all Conda environments on your system and which one is active, run:
```bash
conda env list
```
or
```bash
conda info --envs
```
Example output:
```csharp
# conda environments:
#
base                  *  C:\Users\YourName\Anaconda3
npde_env                 C:\Users\YourName\Anaconda3\envs\npde_env
other_env                C:\Users\YourName\Anaconda3\envs\other_env
```
where
- `*` indicates the currently active environment.
- `base` is the default Conda environment; avoid installing course packages here to prevent conflicts.

If you want to see more details about each environment, including Python version and environment paths, you can run:
```bash
conda info
```
This shows:
- Active environment
- Conda version
- Python version in each environment
- List of installed packages (briefly)
- Environment locations on your system

#### Switch between environments

To switch from your current environment to another one, use:
```bash
conda activate <environment_name>
```
Example: Switch to the course environment:
```bash
conda activate npde_env
```
Your terminal prompt will change to indicate the active environment:
```scss
(npde_env) C:\Users\YourName>
```
or
```ruby
(npde_env) your-computer:~$
```
To stop using the current environment and return to the base environment:

```bash
conda deactivate
```
You can chain multiple `deactivate` commands if needed; the prompt will eventually return to `(base)` or your system default.

#### Delete an environment

To remove an environment completely:
```bash
conda remove -n <environment_name> --all
```
Example: Delete the course environment (if you no longer need it):
```bash
conda remove -n npde_env --all
```
where 
- `-n npde_env` specifies the environment to delete.
- `--all` removes all packages and the environment folder.

Conda will ask for confirmation before deleting. Type `y` to proceed. After deletion, the environment will no longer appear in:
```bash
conda env list
```

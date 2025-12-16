# The least painful way to access Python

<i>Adapted from the USGS’s [Python for Hydrology class instructions](https://github.com/DOI-USGS/python-for-hydrology/tree/main/installation). </i>

! If you run into an issue with this installation, use the [<b>Issues</b>](https://github.com/pycogss/pycogss-intro-to-python/issues) tab to open an issue - if you have a question or problem, someone else probably does, and we can track the progress of any issues or fixes!

# 0. Context
These are instructions to <b>install Python</b> on a <b>computer on which you have administrative privileges</b>. This is <b>not necessarily the route through which your students will access Python in a class setting</b>, especially if they are using lab computers or other setups that do not allow for software installation. If you are here because you want to introduce Python into your undergraduate classroom, you should do some <b>institution-specific research</b> through your IT department and/or Computer Science department to learn what resources might already be available to you, such as a [JupyterHub](https://jupyter.org/hub) deployed on either onsite computing resources or in the cloud. For example, William and Mary maintains both a [cloud-based](https://jupyterhub.wm.edu/) and [cluster-based](notebooks.sciclone.wm.edu) JupyterHub. 

For slightly more advanced users: this works best if you are working on your own computer (and not accessing a cluster or something like that) because you need a display. If you are interested in either conducting this workshop or your class in Jupyter notebooks via an institutional cluster, message me one-on-one and I can give you some tips.  

# 1. Install miniforge

If you have another Python distribution (Conda, Miniconda, Micromamba, Miniforge, *etc.*) installed on your laptop skip to Step 2. Otherwise,

Download the appropriate version of [Miniforge for your operating system](https://github.com/conda-forge/miniforge?tab=readme-ov-file#miniforge3).

- [Windows](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Windows-x86_64.exe)
- [MacOS x86_64](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-x86_64.sh)
- [MacOS Apple Silicon (arm64)](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh)
- [Linux x86_64](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh)
- [Linux aarch64 (arm64)](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-aarch64.sh)

For Windows operating systems, double-click on the downloaded executable installation file. Do not change the default for the `Add Miniforge3 to my PATH environment variable` so that Miniforge does not cause conflicts with existing installed software.

For MacOS and Linux operating systems, open a terminal in the directory that the installation script was downloaded to. Run

```
sh Miniforge-pypy3-OS-arch.sh
```

where `OS-arch` above is the operating system and architecture (MacOSX-x86_64, MacOSX-arm64, Linux-x86_64, or Linux-aarch64).

# 2. Create and activate the workshop environment

For Windows operating systems, open the "Miniforge Prompt" installed to the start menu. For MacOS and Linux operating systems, open a terminal. You will see that you are located in either your “User” folder (or *directory*) if using Windows or some equivalent in MacOS/Linux.

Now, you will need to navigate to the directory where you downloaded the `environment.yml` file that was included in the email with software installation instructions. This will be tricky because you must use the command line instead of clicking. You enter a directory by typing `cd`, and you back out of a directory by typing `cd ..` . In MacOS/Linux, you can list every file in the directory by typing `cd` . In Windows, the command is `dir` . A useful trick is that you can use the Tab button to autocomplete directories if they are present. For example, you can write `cd on` and then hit “Tab” to autocomplete to `cd "One Drive - William and Mary` if that directory is located in your current directory. Very useful! 

Once you have confirmed you are in the right directory by revealing the `environment.yml` file in your current directory using `ls` or `dir`, type the following command

```
mamba env create -f environment.yml
```

When prompted, enter `y` (for “yes”) and let the installation proceed. 

Once the installation has completed, type the following comand:

```jsx
conda activate basic
```

(*not* mamba activate). If successful, you should see a `(basic)` at the beginning of your line instead of the `(base)` environment

# 3. Activate JupyterLab

If you have successfully activated the `basic` environment, you can now type the command:

```jsx
jupyter lab
```

This will spin up an instance of JupyterLab that will be served through your browser and, like magic, your default browser should pop open, and you should find yourself looking at various directories and buttons in a workspace, and your browser will be at the address [`http://localhost:8888/lab`](http://localhost:8888/lab) or something similar. JupyterLab will run as long as that miniforge prompt is still open - it is serving this “app,” essentially, to you via your browser. 

At this point, you can create your own Jupyter notebook files by clicking the “Python 3” button under “Notebook,” or a Python file under “Other,” or any number of options. You can also upload any `.ipynb` files you may have come across online and try to run them here. 

From now on, anytime you want to bring up JupyterLab, follow these steps:

1. Open Miniforge Prompt
2. Activate your environment in which you have installed `jupyter lab` (like `basic`)
3. type `jupyter lab` 

# 4. Download the workshop repository

But most Jupyter Notebooks reside in public repositories on sites like GitHub, and many people directly import these repositories to their workspaces using `git`. 

You can either access the command line in a new Miniforge prompt or use the “Terminal” in JupyterLab to type the following command:

```bash
git clone https://github.com/pycogss/pycogss-intro-to-python.git
```

This will download the repo to your current directory, which you can then access like any other directory. 

If this doesn’t work, you can always download the repo as a zipped file from the webpage for the repo. 

# Optional upgrade: Use VS Code to access Python

<i>For those comfortable with the above steps and want to access their miniforge install in a sleek user interface popular with research and industry</i>

1. Install [VS Code](https://code.visualstudio.com/)
2. Install the Python and Jupyter extensions (Ctrl+Shift+X, Cmd+Shift+X. or the “Extensions” button on the left)
3. Select the Python Interpreter by opening the Command Palette (Ctrl+Shift+P or Cmd+Shift+P) and select your `basic` environment. 
4. Run existing notebooks or create your own new file in the Explorer tab.
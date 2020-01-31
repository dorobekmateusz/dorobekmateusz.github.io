---
title: "Machine Learning Workshop"
collection: teaching
type: "Machine Learning Workshops Materials."
permalink: /teaching/MLWorkshop
---

Workshop on Machine Learning at the Faculty of Mathematics, Warsaw University of Technology - 28 May 2019. Run the notebook from workshops here: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/SaxMan96/Machine-Learning-Workshop-MINI/master?filepath=WorkShopMerge.ipynb) 

## Materials

Workshop materials: [Machine-Learning-Worhshops-MINI](https://github.com/SaxMan96/Machine-Learning-Workshop-MINI)

<iframe width="420" height="315"
src="https://www.youtube.com/embed/pKWFBZafuK8?autoplay=1">
</iframe>


## Running the notebook

If you want to run your notebook from the workshop remotely click on the banner at the top and if you want to run it locally you will have to do some things:

## Fork

Fork my repo
![Fork](https://github.com/SaxMan96/Machine-Learning-Workshop-MINI/blob/master/images/Fork.png?raw=true)

## Git

Click on the [link](https://git-scm.com/downloads) and follow the instuctions. I recommend to mark **Git Bash** during installation and use this console. If you already do it, clone the forged repository:

```
git clone https://github.com/YOUR_GITHUB_USERNAME/Machine-Learning-Workshop-MINI.git
```
YOUR_GITHUB_USERNAME - That's your name on the GutHub - because the repo is in your account..

## Conda

We'll use Conda to install all the necessary Python packages. I strongly recommend installing **MiniCondy**, unless someone is a mega fan of the GUI then they can install Anaconda Navigator.

Here is [link](https://docs.conda.io/en/latest/miniconda.html), choose a version for **Python 3.7**. To verify the installation, run **Anaconda Promt** (Win + "Anaconda Prompt") or on a regular console if you are using Linux or MacOS and type:

```
conda -V
```

Make sure you have the latest version if you don't make an update:

```
conda update conda
```

## Environment

If you managed to install the conda correctly, we will now install a virtual environment with Python and packages. Run Anaconda Prompt, go to the folder with the downloaded repository and type:

```
conda env create -f workshop-env.yml
```

This command will create an environment and install the packages.

## Running it up

- Once you've managed this, enter the repository directory, click `Ctrl + L`, type `cmd`, press Enter. If you are on Linux or Mac open command line in folder with forked repo.

- If you're not scared of what popped up on the screen, that's great, let's go. 

- Type ``activate workshop-env`` (If no such command is found, it means you have to add conda to the environment variables - [link](https://stackoverflow.com/questions/44597662/conda-command-is-not-recognized-on-windows-10)) 

- Then just run our notebook with a command `jupiter notebook`then choose `WorkShopMerge.ipynb` and enjoy our notebook.
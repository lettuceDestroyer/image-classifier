# Image Classifiers for RaspCade

## Using jupyter notebooks in VSCode with a virtual environment

### Summary
Do you use jupyter notebooks? And virtual environment too, right? And do you know how to use them together? Ah! I got you. It is very simple: follow this guide to learn how to install a custom kernel.

Why?
Using virtual environments is important:

It helps you to maintain your system clean: don’t install system-wide libraries that you are only going to use once for a small project

it allows you to use a certain version of a library for one project and another version for another project: if you install the library system-wide and don’t use venv, then you can only use one version of the library

it helps reproducible research: you work hard on your project, you write a paper on it and then you release the code; one year later, the libraries you used are outdated but your package still works: by listing the particular versions that you used, another researcher can set up a new virtual environment and use those outdated libraries to reproduce your work

Basically, virtual environments simplify your life when you work with Python.

How to do it
I assume that you are a tidy person: you have all your work sorted out in folders; one of these folders contains your very important project and it looks like this:

``` bash
$ ls

project/
├── data
├── docs
├── src
└── test
```
Inside this folder create a new virtual environment:

```python
$ python -m venv .venv
```

Then activate it:
```python
# To activate it on Linux run:
$ . <project_name>/bin/activate

# To activate it on Windows run:
$ . <project_name>/Scripts/activate
```
Now, from inside the environment install ipykernel using pip:
```python
$ pip install ipykernel
```

And now install a new kernel:
```python
$ ipython kernel install --user --name=<project_name>
```

Before editing or creating a new notebook in VSCode make sure you have the Jupyter extension installed. By pressing `Ctrl + Shift + P` you can create a Jupyter notebook by selecting the command "Create: New Jupyter Notebook" or set the kernel by selecting "Jupyter. Select Interpreter to Start Jupyter Server".


The above script was copied and edited from: https://web.archive.org/web/20240430135149/https://anbasile.github.io/posts/2017-06-25-jupyter-venv/
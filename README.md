# scikitlearntour

Tour of [SciKit Learn](https://scikit-learn.org/stable/) and other Python Data Ecosystem Tools, [SciPy](https://www.scipy.org/), Matplotlib, Pandas and [Numpy](https://numpy.org/).

# Getting Started with Bindmount

# Prerequisites

* Docker, installed and running.

# Quick Install - Docker Version

1. With terminal, navigate to "/" - the root folder.
2. Run in the '/app' directory:

```
docker build -t jupyter/custom-notebook .
```

3. After image is built, go directly into the "target/app"  project directory from the terminal and run:

```
docker run -it --rm                                   \
-p 8888:8888                                          \
-e JUPYTER_ENABLE_LAB=yes                             \
-v "$PWD":/home/jovyan/work                           \
--name datanotebook                                   \
jupyter/custom-notebook
```
* -it ...is interactive tty mode.
* --rm ...Automatically removes the container when it exits
* -e ...Sets environment variables, in this case we ask to use the new version, "JUPYTER_ENABLE_LAB=yes" instead of Jupyter Notebook.
* -v ${PWD}:/home/jovyan/work mounts a volume, present within the LAB under, "work" at "current_directory/app"

* When you create a notebook within that location, using bind mounts, it is possible to persist data on the disk itself.

* Note, in order for a file to save on the disk, you must move it into the, "work" directory on the JupyterLab folder.

* Looking at the folder structure, if you create a jupyter notebook for example, title it, "helloworld.ipynb" and save it, it will persist on the disk at /target/app.

* The next time you start up your application in that same folder using the commands above, the notebook will be available again in the same state as when it was left off in the container.
# Notes on Startup of Application

Once the application is launched, you will get the following messages:

```
Executing the command: jupyter notebook
[I 22:11:41.725 NotebookApp] Writing notebook server cookie secret to /home/jovyan/.local/share/jupyter/runtime/notebook_cookie_secret
[I 2021-10-27 22:11:42.818 LabApp] JupyterLab extension loaded from /opt/conda/lib/python3.9/site-packages/jupyterlab
[I 2021-10-27 22:11:42.818 LabApp] JupyterLab application directory is /opt/conda/share/jupyter/lab
[I 22:11:42.827 NotebookApp] Serving notebooks from local directory: /home/jovyan
[I 22:11:42.827 NotebookApp] Jupyter Notebook 6.4.5 is running at:
[I 22:11:42.827 NotebookApp] http://{serverid}:8888/?token={tokenvariable1}
[I 22:11:42.827 NotebookApp]  or http://127.0.0.1:8888/?token={tokenvariable1}
[I 22:11:42.827 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 22:11:42.834 NotebookApp]

    To access the notebook, open this file in a browser:
        file:///home/jovyan/.local/share/jupyter/runtime/nbserver-8-open.html
    Or copy and paste one of these URLs:
        http://{serverid}:8888/?token={tokenvariable1}
     or http://127.0.0.1:8888/?token=f92f0e4fbd972c18aafe298ca95e529fea733daf74fe17b5

```
Since this is running from a Docker container and not direclty on the host machine, the way to run this is always going to be to visit 127.0.0.1:8888, followed by the token, since this is the port we set up on localhost to run this notebook via Docker.




# Other Stuff

## Google Colab Notebooks

Using [Google Colab](colab.research.google.com/) to tour the above.


# Matplotlib Plot Basics

* [matplotlib.plot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html)

### Scatter

### Plot

# Topics

## Supervised Learning

[Supervised Learning Documentation](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning)

### Linear Models

#### Ordinary Least Squares

* [Ordinary Least Squares Documentation](https://scikit-learn.org/stable/modules/linear_model.html#ordinary-least-squares)

* [Ordinary Least Squares Colab Notebook](https://colab.research.google.com/drive/1r8zxKgpzbDu4k3a6WKfDpUbX8mw9FyZq?usp=sharing)

#### Bayesian Regression

https://scikit-learn.org/stable/modules/linear_model.html#bayesian-regression

#### Logistic Regression

#### Generalized Linear Regression

#### Polynomial Regression


### Discriminant Analysis

* [Discriminant Analysis Documentation](https://scikit-learn.org/stable/modules/lda_qda.html)

Note - matching the colors to the labels on the plot is not working.

#### Linear Discriminant Analysis

* Note that X (features) and y (classes) must have the same length.
* n_components cannot be larger than min(n_features, n_classes - 1)

* [Linear Discriminant Analysis Colab Notebook](https://colab.research.google.com/drive/13tGIeG_5Ign8ylFb5w6OJcQK5ATg16MF?usp=sharing)

### Support Vector Machines

###


### Random Forest Classifier

* [Random Forest Classifier Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html#sklearn.ensemble.RandomForestClassifier)

[Random Forest Classifier Notebook](https://colab.research.google.com/drive/1ocCkHur3TooT8eDMF3lOMiLscpMU-ipw?usp=sharing)

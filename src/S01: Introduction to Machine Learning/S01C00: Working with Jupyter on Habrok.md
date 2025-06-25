---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.17.2
  kernelspec:
    display_name: ML Workshop
    language: python
    name: ml_workshop
---


# Working with Jupyter Notebooks

Throughout this workshop, we will be working in Jupyter Notebooks / JupyterLab. Jupyter Notebooks are a popular tool for data science and machine learning, allowing you to write and execute code in an interactive environment.

In order to have a uniform environment, we will be using the Habrok High Performance Computing (HPC) cluster, through the Jupyter Python Interactive App on the Habrok web portal, located at [https://portal.hb.hpc.rug.nl](https://portal.hb.hpc.rug.nl). You will need to log in with your university account, and then you can start the Jupyter Python Interactive App.

The app is already setup with the necessary packages for this workshop, but you will also build your own environment and Jupyter kernel.


## Building your own Jupyter kernel on Habrok

In order to build your own Jupyter kernel, you will need to create a new Python environment. This can be done on Habrok by following these steps:

-   From the Habrok web portal, navigate to the "Clusters" tab and select one of the available Shell sessions (e.g., "Habrok Login1 Shell").
-   In the Shell session, first load the Python module by running:

```shell
module load Python/3.13.1-GCCcore-14.2.0
```

-   Next, create a new Python environment using `venv`:

```shell
python3 -m venv $HOME/venvs/ml_workshop
```

-   Activate the new environment:

```shell
source $HOME/venvs/ml_workshop/bin/activate
```

-   Install the necessary packages for the workshop:

```shell
pip install -r requirements.txt
```

-   Finally, install the Jupyter kernel:

```shell
python -m ipykernel install --user --name=ml_workshop --display-name="ML Workshop"
```

Now that the kernel has been created, you can start the Jupyter Python Interactive App again from the Habrok web portal. In the app form, select the correct Python Version (3.13.1), the "Custom virtual environment" option for the Python Environment, and then select the path to your newly created environment, which should be `$HOME/venvs/ml_workshop`. When you start the app, the Jupyter kernel will be available, and you can select it from the "Kernel" menu in the Jupyter Lab interface ("ML Workshop").


## Building your own Jupyter kernel on your local machine

Similarly, you can build your own Jupyter kernel on your local machine. The steps are similar to those on Habrok, but you will need to install Python on your local machine first. You can download Python from the official website: [https://www.python.org/downloads/](https://www.python.org/downloads/).

After following the steps above, you can start Jupyter Lab on your local machine by running:

```shell
jupyter-lab
```

which will open a new tab in your web browser with the Jupyter Lab interface. You can then create a new notebook and select the kernel you created from the "Kernel" menu.


## Building your own Jupyter kernel on Google Colab

If you prefer to use Google Colab, you can also build your own Jupyter kernel there. Google Colab is a free Jupyter notebook environment that runs in the cloud and is particularly useful for machine learning and data science tasks.

To use Google Colab, you will need a Google account. Once you have an account, you can go to [Google Colab](https://colab.research.google.com/) and create a new notebook. You can then install the necessary packages by running the following code in a code cell:

```python
!pip install -r requirements.txt
```

We do not recommend using Google Colab for your research, as it is not a suitable environment for running large-scale machine learning models. However, it can be useful for quick prototyping and testing of small models.

```python
!pip list
```

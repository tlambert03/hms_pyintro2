# NIC@HMS python2: Intro to image processing

## setup

### install miniconda

https://docs.conda.io/en/latest/miniconda.html

If you haven't already, add conda forge to your channels

```shell
conda config --add channels conda-forge
conda config --set channel_priority strict
```

> tip: to download a version of miniconda with conda-forge already
> setup, use [miniforge](https://github.com/conda-forge/miniforge)

### create a new environment for this tutorial

```shell
conda create -n imgproc python
conda activate imgproc
```

> note: anytime you close and reopen your terminal, you'll need to
> reactivate your conda environment with `conda activate <name_of_env>`

### install requirements

```shell
pip install -r requirements.txt
```

> this will use pip to install all of the requirements listed
> in the `requirements.txt` file.  You could also install them with
> conda if you'd like.  See the [previous lecture](https://nic.med.harvard.edu/python/) for details on pip vs conda.

### start one of the tutorials

```shell
jupyter-lab image_io.ipynb
```

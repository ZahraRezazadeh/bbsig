# **Create the `bbsig_pipeline` virtual environment**

!!! warning

    The information contained in this page is updated to mostly covers the packages needed to run the first three BBSIG pipelines included in v0.0.1 (i.e., [ECG preprocessing](https://martager.github.io/bbsig/ecg-preprocessing/), [PPG preprocessing](https://martager.github.io/bbsig/ppg-preprocessing/), [HRV analysis](https://martager.github.io/bbsig/hrv-analysis/)). We will work on keeping the YAML file updated while we develop future pipelines using the same `bbsig_pipeline` environment. 


## **Why a dedicated virtual environment?**

An environment is a directory that contains a **self-isolated Python version and a specific collection of installed packages**. This keeps dependencies required by different projects separate and avoids complications in your base environment. 

To run the BBSIG pipelines, it is best to have a dedicated environment setup that guarantees the correct functioning of the packages. Following the steps below, you can create a `bbsig_pipeline` environment to start using our BBSIG preprocessing and analysis pipelines.

!!! note
    If you are already familiar with `conda` and/or setting up virtual environments, you can jump directly to [Sect. 3](https://martager.github.io/bbsig/setup-venv/#3-create-the-bbsig_pipeline-environment-from-yaml-file). Note that in the following instructions we have chosen to focus on `conda`, but you could also create your virtual environment using `mamba` or `venv` according to your preferences.  

For now, the `bbsig_pipeline` environment is based on Python v3.11 and mainly includes the following packages:

* [numpy](https://numpy.org/) (>=1.26)
* [pandas](https://pandas.pydata.org/) (>=2.2.0)
* [matplotlib](https://matplotlib.org/) (>=3.8.2)
* [bokeh](http://bokeh.org/) (=3.3.4) - newer versions create problems with Systole’s interactive visualization
* [seaborn](https://seaborn.pydata.org/) (>=0.13.2)
* [neurokit2](https://github.com/neuropsychology/NeuroKit) (>=0.2.7)
* [systole](https://embodied-computation-group.github.io/systole/) (=0.3.0)
* [rpy2](https://rpy2.github.io/doc/v3.5.x/html/index.html) (= 3.5)


## **How to create the `bbsig_pipeline` environment**

Follow these three steps to create the `bbsig_pipeline` environment on your local machine and start using our peripheral physiological analysis pipelines. 

### 1. Install `conda`

To install `conda`, we recommend using **`mini-forge`**, a minimal installer for [`Conda`](https://conda.io/) and [`Mamba`](https://github.com/mamba-org/mamba) specific to the [`conda-forge`](https://conda-forge.org/) channel[^1]. With `mini-forge`, the community-led  “conda-forge” channel is pre-configured as the default channel to obtain packages, both in the base environment and in the creation of any further virtual environments. For more information on the installation of `mini-forge` on different Operating Systems, visit the [mini-forge documentation](https://github.com/conda-forge/miniforge).

### 2. Start `conda` 

`Conda` can be used with any terminal application: if you have installed conda using `mini-forge`, you can use their pre-configured **Miniforge Prompt**. 

To verify that `conda` is installed correctly, in your terminal window of choice type and run:
``` console
conda --version
```
This will show the version number that you have installed, such as `conda 4.12.0`. You can read more about managing conda [here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-conda.html). 


### 3. Create the `bbsig_pipeline` environment from YAML file

In order to recreate the dedicated `bbsig_pipeline` virtual environment, you can use the `bbsig_pipeline_environment.yml` file provided here: 

[Download bbsig_pipeline_environment.yml](https://github.com/martager/bbsig/blob/main/bbsig_pipeline_environment.yml)

Use the terminal (e.g., Miniforge Prompt) to execute the following steps [inspired by the documentation [here](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file)]. 

1. Save the `bbsig_pipeline_environment.yml` file in your location of choice, then `cd` into that directory using the terminal, e.g.
    ``` console
    cd /path/to/bbsig_pipeline_directory
    ```
2. Create the environment from the `bbsig_pipeline_environment.yml` file by typing the following command in the terminal. The first line of the `.yml` file will set the new environment's name as `bbsig_pipeline`. It may take some time to download and extract all the required packages.
    ``` py
    conda env create -f bbsig_pipeline_environment.yml
    ```
3. Activate the newly created `bbsig_pipeline` environment: 
    ``` console
    conda activate bbsig_pipeline
    ```


## **Great, now your `bbsig_pipeline` environment is ready!**




[^1]: 

    If you have installed conda using `mini-forge`, `conda-forge` should be already pre-configured as default channel to install packages (i.e., it avoids pulling packages from the Anaconda Distribution `defaults` channel). However, if you have installed `conda` using the Anaconda Distribution or Miniconda, we recommend adding the `conda-forge` channel as the highest priority channel (i.e., `conda` will first search the `conda-forge` channel before the `defaults` channel to install packages):

    ``` console
    conda config --add channels conda-forge
    ```

# Brain-Body Analysis Special Interest Group (BBSIG)

*Open-access, reproducible pipelines for peripheral physiological signal analysis*

![BBSIG banner](/docs/bbsig_banner.png)

![Dynamic TOML Badge](https://img.shields.io/badge/dynamic/toml?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmartager%2Fbbsig%2Frefs%2Fheads%2Fmain%2Fpyproject.toml&query=%24.project.version&label=version&color=blue)
![Dynamic TOML Badge](https://img.shields.io/badge/dynamic/toml?url=https%3A%2F%2Fraw.githubusercontent.com%2Fmartager%2Fbbsig%2Frefs%2Fheads%2Fmain%2Fpyproject.toml&query=%24.project.updated&label=last%20update&color=green)
![Static Badge](https://img.shields.io/badge/License-MIT-orange)


## What is BBSIG?

BBSIG is a **collaborative initiative aimed at streamlining and standardizing the analysis of peripheral physiological data** – mainly cardiovascular activity (electrocardiography [ECG], photoplethysmography [PPG]) and respiration – in relation to brain and behavioral data. Our goal is to develop **accessible, reproducible, and well-documented** analysis pipelines that researchers can integrate into their projects. 

We provide a **set of open-access, Python-based pipelines**, implemented with the modular structure of **Jupyter notebooks**. After comparing existing open-source packages, such as [NeuroKit2](https://neuropsychology.github.io/NeuroKit/index.html) and [Systole](https://legrandnico.github.io/systole/index.html), we integrated the most suitable functions for peripheral physiological data processing into a recommended sequence of preprocessing and analysis steps, which can be adapted to each research project. Our pipelines are compatible with the [Brain Imaging Data Structure (BIDS)](https://bids-specification.readthedocs.io/en/stable/) specification for file organization and naming conventions.

Our mission is to **facilitate and enhance the reproducibility and transparency** in peripheral physiological signal analysis by offering **open-access, customizable pipelines with step-by-step tutorials**. Whether you are a novice or an expert in brain-body interactions, BBSIG provides tools and guidance to support your research.


## Current version (v0.0.1)

Currently, BBSIG v0.0.1 includes the following pipelines:

* **Electrocardiography (ECG) preprocessing (`ecg_preproc.ipynb`)**: preprocess raw ECG data, including signal cleaning, R-peak detection and QRS complex delineation. Then, export key ECG features such as R-peak and T-wave offset locations, RR intervals time-series and interpolated heart rate (HR), useful for later analysis stages. 
* **Photoplethysmography (PPG) preprocessing (`ppg_preproc.ipynb`)**: process raw PPG data, including signal normalization, cleaning, clipping artifacts correction and systolic peaks detection. Then, export key PPG information such as systolic peak locations, RR intervals time-series and interpolated heart rate (HR), useful for later analysis stages. 
* **Heart Rate Variability (HRV) analysis (`hrv_analysis.ipynb`)**: compute time-domain and frequency-domain HRV metrics, starting from the previously preprocessed ECG or PPG data (or from your own RR intervals time-series).

For the full documentation and step-by-step tutorials, visit the [Overview page](https://martager.github.io/bbsig/overview). 

## Quick setup

In order to run the BBSIG pipelines, we recommend you follow these two quick setup steps:

1. **Create the `bbsig_pipeline` environment**: create a dedicated virtual environment, called `bbsig_pipeline`, from the provided `bbsig_pipeline_environment.yml` file. This is based on Python >=3.11 and features a pre-specified collection of packages, including:
    * [numpy](https://numpy.org/) (>=1.26)
    * [pandas](https://pandas.pydata.org/) (>=2.2.0)
    * [matplotlib](https://matplotlib.org/) (>=3.8.2)
    * [bokeh](http://bokeh.org/) (=3.3.4) 
    * [seaborn](https://seaborn.pydata.org/) (>=0.13.2)
    * [neurokit2](https://github.com/neuropsychology/NeuroKit) (>=0.2.7)
    * [systole](https://embodied-computation-group.github.io/systole/) (=0.3.0)
    * [rpy2](https://rpy2.github.io/doc/v3.5.x/html/index.html) (= 3.5)

    To know more, check our documentation at [Create the virtual environment](https://martager.github.io/bbsig/setup-bbsig-env/).

2. **Organize your folders and physiological recordings according to the BIDS standards**: for optimal compatibility with our pipelines, standardize the folder structure, file naming and file formats of your peripheral physiological data according to the [Brain Imaging Data Structure (BIDS)](https://bids-specification.readthedocs.io/en/stable/) specification. To know more, check our documentation at [Organize your BIDS folders](https://martager.github.io/bbsig/bids-structure/). 


## Citation

When using or adapting the BBSIG pipelines in your research work, please cite us in your publication as: 

**APA**

> *Gerosa M., Agrawal N., Ciston A.B., Fischer A., Fourcade A., Koushik A., Neubauer M., Patyczek A., Piejka A., Reinwarth E., Roellecke L., Shum Y.H., Verschooren S., Gaebler M. (2025). Brain-Body Analysis Special Interest Group (BBSIG) (version 0.0.1) [Computer software]. [https://martager.github.io/bbsig/](https://martager.github.io/bbsig/)*


**BibTeX**

    ```
    @software{bbsig2025,
    author = {Gerosa, Marta and Agrawal, Niket and Ciston, Anthony Buck and Fischer, Anna and Fourcade, Antonin and Koushik, Abhay and Neubauer, Mia and Patyczek, Agata and Piejka, Aleksandra and Reinwarth, Elias and Roellecke, Lucy and Shum, Yu Hei and Verschooren, Sam and Gaebler, Michael},
    month = {4},
    title = {Brain-Body Analysis Special Interest Group (BBSIG)},
    url = {https://martager.github.io/bbsig/},
    year = {2025}
    }
    ```


## To-do:

- [ ] ECG preprocessing: enable looping over multiple participants (without manual correction)
- [ ] HRV analysis: solve NeuroKit2's bug in frequency-domain plotting (or develop our own plot)
- [ ] Make BBSIG into a Python package
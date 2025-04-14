# **Quick overview**

## **Current version (v0.0.1)**

Currently, BBSIG v0.0.1 includes the following pipelines:

* **Electrocardiography (ECG) preprocessing (`ecg_preproc.ipynb`)**: preprocess raw ECG data, including signal cleaning, R-peak detection and QRS complex delineation. Then, export key ECG features such as R-peak and T-wave offset locations, RR intervals time-series and interpolated heart rate (HR), useful for later analysis stages. 
* **Photoplethysmography (PPG) preprocessing (`ppg_preproc.ipynb`)**: process raw PPG data, including signal normalization, cleaning, clipping artifacts correction and systolic peaks detection. Then, export key PPG information such as systolic peak locations, RR intervals time-series and interpolated heart rate (HR), useful for later analysis stages. 
* **Heart Rate Variability (HRV) analysis (`hrv_analysis.ipynb`)**: compute time-domain, frequency-domain and non-linear HRV metrics, starting from the previously preprocessed ECG or PPG data (or from your own RR intervals time-series).

All our pipelines are **compatible with the [Brain Imaging Data Structure (BIDS)](https://bids-specification.readthedocs.io/en/stable/) specification** for file organization and naming conventions. If you have stored your raw physiological recordings according to the BIDS standards, our pipelines are ready to work without major adjustments! Otherwise, you can learn how to structure your data according to the BIDS standards [here](https://martager.github.io/bbsig/bids-structure/). 

### A flowchart for peripheral physiological signal analysis
*Don't know where to start?* Follow this flowchart to know which BBSIG pipeline is best suited for your project, depending on the peripheral physiological modality and the analysis step to be performed: 

``` mermaid
stateDiagram-v2
    s1: What type of peripheral physiological data do you have?
    ECG: Electrocardiography (ECG)
    PPG: Photoplethysmography (PPG)
    RESP: Respiration (RESP)
    TBD: Coming soon...
    TBD2: Coming soon...
    ECGpre: ecg_preproc.ipynb
    PPGpre: ppg_preproc.ipynb
    HRVpip: hrv_analysis.ipynb
    
    s1 --> ECG 
    s1 --> PPG
    s1 --> RESP 

    ECGpre --> TBD2: Cardiac phase analysis?

    ECG --> ECGpre: Preprocessing needed?
    PPG --> PPGpre: Preprocessing needed?
    RESP --> TBD: Preprocessing needed?

    ECGpre --> HRVpip: HRV analysis?
    PPGpre --> HRVpip: HRV analysis?

    classDef Future font-style:italic;
    classDef Bold font-weight:bold;
    class TBD, TBD2 Future
    class ECGpre, PPGpre, HRVpip Bold
```

## **Setup**

In order to run the BBSIG pipelines, we recommend you follow these two setup steps:

1. **Create the `bbsig_pipeline` environment**: as a starting point, we recommend every user to create a dedicated virtual environment, called `bbsig_pipeline`. This features a pre-specified collection of packages, and can be easily created thanks to the provided YAML file. The virtual environment will allow you to work with the Jupyter notebooks of all our BBSIG pipelines smoothly. *Unsure what a virtual environment is?* Check our documentation at [Create the virtual environment](https://martager.github.io/bbsig/setup-bbsig-env/). 

2. **Organize your folders and physiological recordings according to the BIDS standards**: for optimal compatibility with our pipelines, we recommend every user to standardize their folder structure, file naming and file formats according to the [Brain Imaging Data Structure (BIDS)](https://bids-specification.readthedocs.io/en/stable/) specification. In particular, peripheral physiological data should be saved as a compressed TSV.GZ file, stored within the respective neuroimaging `<datatype>` modality it was acquired with (e.g., `beh` for behavioral only experiments, `eeg` for EEG experiments, or `func` for fMRI experiments). *Unsure how the BIDS folder structure looks like?* Check our documentation at [Organize your BIDS folders](https://martager.github.io/bbsig/bids-structure/). 

Once you have completed these two steps, you are ready to use the BBSIG pipeline that best fits your physiological data and analysis step. You can proceed to the [Pipelines](https://martager.github.io/bbsig/ecg-preprocessing/) section. 
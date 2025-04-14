# **Frequently Asked Questions (FAQs)**

!!! tip 

    Do you have other questions regarding our BBSIG pipelines? Open an issue on GitHub, or send us an email at **bbsig-contact [at] cbs.mpg.de**. 


## **Setup**

### Jupyter Notebooks

***Q: I've never used a Jupyter notebook before. How can I run the BBSIG pipelines?***

**A:** No worries - Jupyter notebooks are easy to get started with! Jupyter notebooks are interactive documents that allow you to run code in small sections (called cells) and document it using Markdown syntax. These files are recognizable by the `.ipynb` extension. To get familiar with how they work, check out the official [Jupyter Notebook documentation](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html).

You have two main options to run Jupyter notebooks: locally, in your IDE (e.g., VS Code or PyCharm), or in a web browser (e.g., using [JupyterLab](https://jupyter.org/try#jupyterlab)). **We recommend running the BBSIG pipelines *locally* in an IDE**, especially for interactive tasks like manual peak correction during ECG or PPG preprocessing, where the browser version can sometimes be laggy or crash unexpectedly.

To run the BBSIG pipelines locally, first make sure you have created the dedicated `bbsig_pipeline` environment following the our instructions at [Create the virtual environment](https://martager.github.io//bbsig/setup-bbsig-env/). This already comes with the [Jupyter package](https://pypi.org/project/jupyter/) installed. You can then proceed to open the desired BBSIG pipeline (e.g., `ecg_preproc.ipynb`) in your preferred IDE. Then, if prompted, select the Python interpreter or kernel associated with the `bbsig_pipeline` environment. If you are using VS Code, we recommend following this tutorial on how to work with [Jupyter Notebooks in VS Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks). 

Inside the notebook, **run each code cell by clicking on it and pressing `Shift + Enter`**. This will allow you to work through the notebook step by step, changing default or optional parameters as desired. 


### Brain Imaging Data Structure (BIDS)

***Q: Does my data need to be BIDS-compliant?***

**A:** This section is under construction. 

# 🌟 ParkerNet: A Deep Learning Tool for Switchback Classification in Parker Solar Probe Data 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.14902721.svg)](https://doi.org/10.5281/zenodo.14902721)  


**ParkerNet v1.0** is the original model architecture and weights.
**Notebook Version 1.1** refers to updated documentation, robustness testing, and visualization.

## Installation

To install all required packages, run:

```bash
pip install -r requirements.txt
```

## 🔥 Project Highlights  
Switchbacks—**abrupt disturbances or reversals in the radial magnetic field of the solar wind**—have been extensively studied since NASA’s **Parker Solar Probe (PSP)** mission. These disturbances could hold the key to understanding how the **solar wind is heated and accelerated**.  

In this project, we introduce **ParkerNet**—a **Deep Learning model** designed to classify switchbacks in **PSP data** for the first time!  

- **Trained on PSP FIELDS and SWEAP (SPC) instrument measurements obtained from publicly available data on CDAweb**.  
- **Quickly classifies switchbacks** in PSP data.  
- **ParkerNet Version 1.0** is introduced here.

For full model details, see the [Model Card](https://github.com/DonaK695/PSP_ParkerNet_switchback_classifier/blob/main/Model_Card_ParkerNet_v1.0.md)


---  

### 📂 What's Included in the Main folder ParkerNetVersion01?  
This repository contains **three** subfolders containing **four** Jupyter Notebooks, and accompanying datasets. The subfolders contain the following:  

- 📂 ParkerNet_Training: Subfolder containing Jupyter Notebook needed for training ParkerNet
	
	📜 **ParkerNet_Training/ParkerNet_Version1_1_Training_ApJS_Notebook1of3**  
	- **Train ParkerNet** with different **seeds** and **train-validation splits**. 
	


- 📂 ParkerNet_Ensemble_Prediction: Subfolder containing Jupyter notebook needed to perform ensemble prediction on new (prediction) datasets.
	
	📜 **ParkerNet_Ensemble_Prediction/ParkerNet_Version1_1_Ensemble_Prediction_ApJS_Notebook2of3_SPC_SPANI.ipynb**  
	- Computes **ensemble (weighted average) predictions** from **71 pre-trained ParkerNet models**.  
	- Includes **datasets for prediction**, or use your own data! 



- 📂 ParkerNet_ApJS_Figures: Data Visualization & Figures  
	
	📜 **ParkerNet_ApJS_Figures/ParkerNet_Version1_1_DataViz_Figures_ApJS_Notebook3of3.ipynb**  
	- Reproduce figures from the research paper:  
		 *"An Iterative, Deep Learning Approach for Switchback Classification in Parker Solar Probe Data"* 📊 
	- Includes **datasets needed to recreate figures**.

	📜 **ParkerNet_ApJS_Figures/ParkerNet_Version1_1_ApJS_Appendix_B_Figures.ipynb**   

	- Provides code to perform occlusion and AUC-PRC comparison between MAG + SPC and MAG + SPANI datasets.

	- Recreates figures shown in Appendix A.

---

**General Instructions**

- To run in Colab, upload the files from this repo to your Google drive and then mount your drive. You should be able to run the notebooks as they are.  
- To run on your local machine, download this repo, create a virtual environment,  install all the packages you need from the provided requirements.txt file, and run the notebook in a Jupyter environment or you can obtain the Python and Jupyter extensions for VS code.  

*Note : you will have to adjust the data loading code but that's about it (provide path to your folder containing the repo files). The notebooks contain detailed instructions and will also tell you what files are needed.*

**For Notebooks 1,2 and 4**: You will need to obtain the training data file "PSP_E1toE7_July23_nonoise.txt" from [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.14902750.svg)](https://doi.org/10.5281/zenodo.14902750)   

---

**📌 Instructions for using Notebook 1:** 

⚙️ To Open **ParkerNet_Training/ParkerNet_Version1_1_Training_ApJS_Notebook1of3**, click here :[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DonaK695/PSP_ParkerNet_switchback_classifier/blob/main/ParkerNetVersion01/ParkerNet_Training/ParkerNet_Version1_1_Training_ApJS_Notebook1of3.ipynb)


**📌 Instructions for using Notebook 2:** 

⚙️To open **ParkerNet_Ensemble_Prediction/ParkerNet_Version1_1_Ensemble_Prediction_ApJS_Notebook2of3_SPC_SPANI**, click here:  
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DonaK695/PSP_ParkerNet_switchback_classifier/blob/main/ParkerNetVersion01/ParkerNet_Ensemble_Prediction/ParkerNet_Version1_1_Ensemble_Prediction_ApJS_Notebook2of3_SPC_SPANI.ipynb)


**📌 Instruction for using Notebook 3:** 

⚙️To open **ParkerNet_Version1_1_DataViz_Figures_ApJS_Notebook3of3**, click here: [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DonaK695/PSP_ParkerNet_switchback_classifier/blob/main/ParkerNetVersion01/ParkerNet_ApJS_Figures/ParkerNet_Version1_1_DataViz_Figures_ApJS_Notebook3of3.ipynb)


**📌 Instruction for using Notebook 4:** 

⚙️To open **ParkerNet_Version1_1_ApJS_Appendix_B_Figures**, click here: [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DonaK695/PSP_ParkerNet_switchback_classifier/blob/main/ParkerNetVersion01/ParkerNet_ApJS_Figures/ParkerNet_Version1_1_ApJS_Appendix_B_Figures.ipynb)

---

📜 **Notes for user:** 

**ParkerNet Version 1.0** is our base model, we have future improvements planned, including adding **explainable AI** and upgraded capabilities. 

---

## Cite this Repository

If you use ParkerNet in your work, please cite the appropriate model version:

- Zenodo Concept DOI (all versions): [10.5281/zenodo.14902721](https://doi.org/10.5281/zenodo.14902721)  
- Specific release (e.g., v1.1): [10.5281/zenodo.15684176](https://doi.org/10.5281/zenodo.15684176)


---

## Author and Maintainer

This project is developed and maintained by **Dona Chathuni P. Kuruppuaratchi**.  
For questions or contributions, please open an issue or submit a pull request.
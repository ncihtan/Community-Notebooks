

# Human Tumor Atlas Network (HTAN) BigQuery Notebooks

<a id="introduction"></a>
## Introduction

[HTAN](https://humantumoratlas.org) is a National Cancer Institute (NCI)-funded Cancer Moonshot initiative to
construct 3-dimensional atlases of the dynamic cellular, morphological, and molecular features of human cancers as they
evolve from precancerous lesions to advanced disease [(Cell, April 2020)](https://www.sciencedirect.com/science/article/pii/S0092867420303469).

Clinical data, sample biospecimen data, and assay files in HTAN have a rich set of annotations supplied by HTAN data
contributors. These annotations are made according to the [HTAN Data model](https://docs.humantumoratlas.org/data_model/overview/),
a set of standards defined by the HTAN consortium. The supplied values of these attributes have been collected into
comprehensive data tables in the cloud, accessed using [Google BigQuery standard SQL](https://cloud.google.com/bigquery/docs/query-overview).

This folder contains example notebooks that illustrate how to query and process both file metadata and molecular data
that are available in Google BigQuery tables.

In order to access the cloud-based data used in these notebooks, please see: [ISB-CGC Documentation: Getting started with Analysis](https://isb-cancer-genomics-cloud.readthedocs.io/en/latest/sections/HowToGetStarted-Analysis.html).

## Table of Contents
* [Introduction](#introduction)
* [Notebook Environment](#environment)
* [Contents](#contents)
  * [HTAN Clinical, Biospecimen, and Assay File Annotation Data](#annotation)
  * [Molecular and Cellular Data in HTAN](#molecular)
  * [HTAN Processing and Workflows](#workflows)

<a id="environment"></a>
## Notebook Environment

These notebooks rely on multiple Python packages with specific version requirements. You can either run them locally using a Conda environment or execute them directly in Google Colab.

### Option 1: Run Locally with Conda
This notebooks use multiple Python packages with specific version requirements. We recommend using `conda` to create an isolated Python environment with all necessary packages. The list of necessary packages can be found at in the [`environment.yml`](./environment.yml) file.

To create the specified `community-notebooks-env` Conda environment, run the following command:
```bash
conda env create -f environment.yml
```

Once the Conda environment is created, it can be activated by:
```bash
conda activate community-notebooks-env
```
After coding inside the environment, it can be deactivated with the command:
```bash
conda deactivate
```

### Option 2: Run in Google Colab
You can also run these notebooks in Google Colab without setting up a local environment. Keep in mind that you may need to install any missing packages within the notebook using `pip` if they are not already available in the Colab runtime.

<a id="contents"></a>
## Contents

Notebooks illustrating the ease of accessing HTAN metadata and wordflows are made available in both the R (R markdown) and Python (Jupyter) programming languages. There is a also a folder with templates, if you would like to create and share your own notebooks!

Below, we outline some of the different topics covered by our notebooks.

<a id="annotation"></a>
### HTAN Clinical, Biospecimen, and Assay File Annotation Data

- **R Notebooks/Explore_HTAN_Clinical_Biospecimen_Assay_Metadata.Rmd**: Illustrates how to make use of HTAN Google BigQuery metadata tables to tabulate and plot available HTAN clinical, biospecimen, and assay metadata in R.
- **Python Notebooks/Explore_HTAN_Clinical_Biospecimen_Assay_Metadata.ipynb**: Illustrates how to make use of HTAN Google BigQuery metadata tables to tabulate and plot available HTAN clinical, biospecimen, and assay metadata in Python.
- **Python Notebooks/HTAN_ID_Provenance_In_BQ.ipynb**: Introduces the HTAN Google BigQuery ID provenance table and provides example use cases for the table in Python.
- **Python Notebooks/Identifying_HTAN_Data_Files_by_Organ_in_ISB-CGC.ipynb**: Demonstrates how users can identify and access assay data for a particular organ or cancer type using Google BigQuery metadata tables.
- **Python Notebooks/Identifying_and_Compiling_Precancer_Cases_and_Samples_in_HTAN.ipynb**: Illustrates how to make use of HTAN Google BigQuery clinical and biospecimen tables to identify precancer cases and specimens in HTAN.

<a id="molecular"></a>
### Molecular and Cellular Data in HTAN

- **Python Notebooks/Investigating_Single_Cell_HTAN_Data.ipynb**: Illustrates how to query HTAN single-cell RNA sequencing data for cell content and gene expression.
- **Python Notebooks/Building_AnnData_with_Subset_of_Cells_from_BQ.ipynb**: Illustrates how to query HTAN single-cell RNA sequencing data for specific cell types and construct an Scanpy Anndata object from the result.
- **Python Notebooks/Analyzing_HTAN_MIBI_Imaging_Data.ipynb**: Demonstrates how higher level HTAN MIBI data can be pulled from Synapse and Google BigQuery for analysis or visualization.
- **R Notebooks/Explore_HTAN_Spatial_Cellular_Relationships.Rmd**: Illustrates how to make use of HTAN Google BigQuery cell spatial tables, which contain information on cellular locations and the estimated expression of key marker proteins, based on multiplexed imaging and cell segmentation.
- **Python Notebooks/Analyzing_HTAN_spatial_data_with_BigQuery_geospatial_analytics.ipynb**: Offers examples demonstrating how Google BigQuery spatial analytics can assist in the analysis and exploration of spatial data accessible within HTAN BigQuery table

<a id="workflows"></a>
### HTAN Processing and Workflows

- **Python Notebooks/Analyzing_HTAN_Data_in_SB_Data_Studio.ipynb**: Illustrates how open-access HTAN data can be integrated with controlled-access data in CDS Data Studio. Utilizes the HTAN ID provenance BigQuery table in ISB-CGC to pull in relevant files.

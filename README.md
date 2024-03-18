Early detection of cytokine release syndrome (CRS) after CART-therapy through machine learning (ML) models using cytokine and wearable data.
==============================

Introduction :
CRS stands for Cytokine Release Syndrome, which is a potentially serious side effect associated with certain immunotherapy treatments, particularly CAR T-cell therapy. CAR T-cell therapy is a type of immunotherapy where a patient's T cells (a type of immune cell) are genetically modified to express chimeric antigen receptors (CARs). These receptors allow the T cells to recognize and attack cancer cells more effectively. In multiple myeloma, CAR T-cell therapy holds promise as a potential treatment option, particularly for patients who have relapsed or become refractory to standard treatments. However, like in other cancers, the development of CRS is a significant concern in the context of CAR T-cell therapy for multiple myeloma.

Multiple myeloma is a cancer of plasma cells, which are a type of white blood cell responsible for producing antibodies. CAR T-cell therapy for multiple myeloma involves genetically modifying a patient's T cells to target a specific protein, such as BCMA (B-cell maturation antigen), which is highly expressed on the surface of myeloma cells.

When infused into the patient, these engineered CAR T cells recognize and bind to myeloma cells, leading to their destruction. However, this process can trigger an immune response and the release of cytokines, resulting in CRS. CRS is a systemic inflammatory response syndrome characterized by the excessive release of pro-inflammatory cytokines into the bloodstream. It can manifest as fever, hypotension, capillary leak syndrome, and multi-organ dysfunction, ranging from mild to life-threatening severity. CRS is particularly prevalent in patients undergoing CAR T-cell therapy, where the activation and expansion of genetically engineered T cells lead to an immune cascade and cytokine storm.

Overview :
The objective of this capstone project is to develop machine learning models to enable the early detection of Cytokine Release Syndrome (CRS) in patients undergoing Chimeric Antigen Receptor T-cell (CAR T-cell) therapy. CRS is a potentially severe complication associated with CAR T-cell therapy, particularly in the treatment of multiple myeloma. Early detection of CRS is crucial for timely intervention and management, ultimately improving patient outcomes.

This project focuses on leveraging machine learning techniques to analyze cytokine levels and wearable device data for the early detection of CRS.

Dataset Overview:
This dataset contains information related to patients undergoing CAR T-cell therapy for the treatment of multiple myeloma, a type of cancer. The data includes various biomarkers, patient demographics, treatment details, and clinical outcomes. Here's an overview of the columns in the dataset:

Patient Information: Sample ID: Identifier for each sample. PT_ID: Patient identifier. Agent: The type of therapy agent used (JNJ/BMS/Caribou). Date of CAR-T infusion: Date when CAR T-cell therapy was administered. DOB: Date of birth of the patient. Age: Age of the patient at the time of treatment. Date of Sample: Date when the sample was collected. Days in relation to CAR-T infusion: Number of days before or after CAR T-cell infusion. Patient experienced CRS at any point (Yes/No): Indicates whether the patient experienced CRS during the treatment. CRS on date (0 No, 1 Yes): Binary indicator of CRS occurrence. CRS Grade: CRS grade indicates the severity of Cytokine Release Syndrome. Here's a breakdown:

Grade 1 (Mild): Mild symptoms not requiring specific medical intervention. Grade 2 (Moderate): Moderate symptoms requiring medical intervention but not life-threatening. Grade 3 (Severe): Severe symptoms requiring medical intervention, potentially in an intensive care setting. Grade 4 (Life-threatening): Life-threatening symptoms requiring urgent medical attention.

ICANS on date: Indication of neurotoxicity. TOCI given on day (0 no, 1 yes): Administration of tocilizumab. Anakinra given on day (0 no, 1 yes): Administration of anakinra. Steroids given: Administration of steroids. Highest Temp: Highest recorded temperature. Dose (10^6 cells): Dosage of CAR T-cells (in millions). Dose (10^6 cells/kg): Dosage of CAR T-cells normalized by patient's weight. Bridging Chemo Therapy: Indication of prior chemotherapy treatment. WBC: White blood cell count. abs Monocyte: Absolute monocyte count. ANC: Absolute neutrophil count. ABS Lymphocyte count: Absolute lymphocyte count. Highest Ferritin: Maximum ferritin level recorded. Highest CRP: Maximum C-reactive protein level recorded. Best Response as of 1_24_2024: Best response refers to the most favorable treatment response observed during the course of therapy. This could include categories such as Severe Complete Response (sCR), Partial Response (PR), Stable Disease (SD), Progressive Disease (PD), etc Date of PD (1_24_24): Date of disease progression. Date of Last Response Assess if No PD (1_24_24): Last assessment date if no disease progression occurred.

Biomarkers: The dataset includes various biomarkers measured during the treatment. Some of the key biomarkers are:

IL8, TNFRSF9, TIE2, MCP-3, CD40-L, IL-1 alpha, CD244, EGF, ANGPT1: Biomarkers related to inflammation and immune response. CD4, CD8A, CD40, CD27, CD5, CD70, CD83: Biomarkers associated with immune cell types. IL2, IL6, IL7, IL10, IL12, IL15, IL18, IL33, IL4, IL5, IL13: Various interleukins involved in immune regulation. MCP-1, MCP-2, MCP-4: Monocyte chemoattractant proteins involved in inflammation. CXCL1, CXCL5, CXCL9, CXCL10, CXCL11, CXCL12, CXCL13: Chemokines involved in immune cell migration. TNF, TNFSF14, TNFRSF12A, TNFRSF4: Tumor necrosis factor and related receptors. GZMB, GZMH: Granzymes involved in cytotoxicity. VEGFA, VEGFR-2: Vascular endothelial growth factor and its receptor. CSF-1: Colony-stimulating factor 1. Plate and Quality Control: Plate ID: Identifier for the plate associated with the data. QC Warning: Quality control warning, if any. QC Deviation from median: Deviation from the median in quality control. QC Deviation from median.1: Another measure of deviation from the median in quality control.

Usage: This dataset is suitable for exploratory data analysis (EDA), building predictive models to identify early signs of CRS, understanding the impact of biomarkers on treatment outcomes, and investigating factors influencing treatment response and toxicity. Machine learning models, statistical analyses, and visualization techniques can be applied to derive insights and support clinical decision-making in CAR T-cell therapy for multiple myeloma.


# Project Title  
  
Pre-symptomatic detection of CRS using wearable data 
  
## Project Description 

Cytokine Release Syndrome (CRS) is a significant and potentially life-threatening condition associated with immune-based therapies, especially in cancer treatment. CRS occurs due to elevated levels of circulating cytokines, such as interleukin (IL)-6 and interferon γ, which can result from the administration of therapies like bispecific antibodies and adoptive T-cell therapies. Symptoms of CRS can range from mild to severe, including fever, nausea, hypotension, and life-threatening organ dysfunction 

The rapid identification and treatment of CRS are critical for patient outcomes. This capstone project proposes the development of a predictive model leveraging machine learning algorithms to anticipate the onset of CRS in patient's multiple myeloma (MM). Utilizing continuous, real-time physiological data collected from wearable monitoring devices alongside discrete biomarker data from bloodwork, we aim to predict the likelihood of CRS before clinical symptoms manifest. 

The project will involve working with timeseries data, including temperature, pulse, respiratory rate, and oxygen saturation, and biomarker levels indicative of inflammatory responses. Preprocessing techniques will standardize and clean the dataset, preparing it for exploratory data analysis to identify patterns correlated with CRS events. Subsequent feature engineering will aim to improve the predictive power of the machine learning models by synthesizing the raw data into informative metrics. 

We plan to evaluate several algorithms, ranging from traditional machine learning approaches, like Random Forest and Gradient Boosting Machines, to advanced deep learning models, such as Long Short-Term Memory (LSTM) networks, for their ability to predict CRS. The performance of these models will be rigorously tested through validation techniques, and their predictions will be compared against standard clinical observations to determine the earliest and most reliable indicators of CRS. 

This research aspires to facilitate the transition from inpatient to outpatient CAR-T therapy administration by providing a robust framework for early CRS detection. If successful, this predictive model could significantly reduce hospital stays, healthcare costs, and improve patient quality of life, marking a notable advancement in the personalized care of MM patients. 
  
  
## Data Dictionary  
  
Column Name | Data Type | Units | Description | Possible Values | Source  
--- | --- | --- | --- | --- | ---  
Sample ID | Text | N/A | Unique identifier for each sample | N/A | Both  
PT_ID | Text | N/A | Unique identifier for each patient | N/A | Both  
Agent (JNJ/BMS/Caribou) | Categorical | N/A | Name of the pharmaceutical agent used for CAR-T therapy | JNJ, BMS, Caribou | Both  
Date of CAR-T infusion | Date | N/A | Date on which the patient received the CAR-T cell infusion | N/A | Both  
respiratory_rate_obscount | Numeric | N/A | Number of respiratory rate observations recorded by the wearable device | N/A | Wearable  
respiratory_rate_avg | Numeric | Breaths/min | Average respiratory rate recorded by the wearable device | N/A | Wearable  
covered_skin_temperature_max | Numeric | Degrees Celsius | Maximum skin temperature recorded by the wearable device | N/A | Wearable  
systolic_bp_obscount | Numeric | N/A | Number of systolic blood pressure observations recorded by the wearable device | N/A | Wearable  
systolic_bp_avg | Numeric | mmHg | Average systolic blood pressure recorded by the wearable device | N/A | Wearable  
weight_obscount | Numeric | N/A | Number of weight observations recorded by the wearable device | N/A | Wearable  
weight_avg | Numeric | Kilograms | Average weight of the patient as recorded by the wearable device | N/A | Wearable  
diastolic_bp_obscount | Numeric | N/A | Number of diastolic blood pressure observations recorded by the wearable device | N/A | Wearable  
diastolic_bp_avg | Numeric | mmHg | Average diastolic blood pressure recorded by the wearable device | N/A | Wearable  
motion_obscount | Numeric | N/A | Number of motion observations recorded by the wearable device | N/A | Wearable  
motion_avg | Numeric | N/A | Average motion detected by the wearable device | N/A | Wearable  
step_count_sum | Numeric | Steps | Total number of steps counted by the wearable device | N/A | Wearable  
step_count_obscount | Numeric | N/A | Number of step count observations recorded by the wearable device | N/A | Wearable  
date | Date | N/A | Date of the observations | N/A | Wearable  
time | Time | N/A | Time of the observations | N/A | Wearable   
patient_id | Text | N/A | Unique identifier for each patient | N/A | Both  
pr_display | Categorical | N/A | Display status of Pulse Rate | Various | Wearable  
spo2_display | Categorical | N/A | Display status of Oxygen Saturation | Various | Wearable  
resp_display | Categorical | N/A | Display status of Respiratory Rate | Various | Wearable  
pulse_rate_obscount | Numeric | N/A | Number of pulse rate observations recorded by the wearable device | N/A | Wearable  
pulse_rate_avg | Numeric | Beats/min | Average pulse rate recorded by the wearable device | N/A | Wearable  
pulse_rate_min | Numeric | Beats/min | Minimum pulse rate recorded by the wearable device | N/A | Wearable  
pulse_rate_max | Numeric | Beats/min | Maximum pulse rate recorded by the wearable device | N/A | Wearable  
pulse_rate_iqr | Numeric | Beats/min | Interquartile range of pulse rate recorded by the wearable device | N/A | Wearable  
covered_axil_temperature_obscount | Numeric | N/A | Number of axillary temperature observations recorded by the wearable device | N/A | Wearable  
covered_axil_temperature_avg | Numeric | Degrees Celsius | Average axillary temperature recorded by the wearable device | N/A | Wearable  
covered_axil_temperature_min | Numeric | Degrees Celsius | Minimum axillary temperature recorded by the wearable device | N/A | Wearable  
covered_axil_temperature_max | Numeric | Degrees Celsius | Maximum axillary temperature recorded by the wearable device | N/A | Wearable  
weight_min | Numeric | Kilograms | Minimum weight of the patient as recorded by the wearable device | N/A | Wearable  
weight_max | Numeric | Kilograms | Maximum weight of the patient as recorded by the wearable device | N/A | Wearable   
DOB | Date | N/A | Date of birth of the patient | N/A | Both  
Age | Numeric | Years | Age of the patient | N/A | Both  
Days in relation to CAR-T infusion | Numeric | Days | Number of days in relation to the date of CAR-T infusion | N/A | Both  
Patient experienced CRS at any point (Yes/No) | Binary | N/A | Whether the patient experienced Cytokine Release Syndrome at any point | Yes, No | Both  
CRS on date (0 No, 1 Yes) | Binary | N/A | Whether the patient experienced Cytokine Release Syndrome on a specific date | 0, 1 | Both  
CRS Grade | Numeric | N/A | The severity grade of Cytokine Release Syndrome experienced by the patient | N/A | Both  
ICANS on date | Binary | N/A | Whether the patient experienced Immune effector Cell-Associated Neurotoxicity Syndrome on a specific date | 0, 1 | Both  
TOCI given on day (0 no, 1 yes) | Binary | N/A | Whether Tocilizumab was given on a specific day | 0, 1 | Both  
Anakinra given on day (0 no, 1 yes) | Binary | N/A | Whether Anakinra was given on a specific day | 0, 1 | Both  
Steroids given | Binary | N/A | Whether steroids were administered | Yes, No | Both  
Highest Temp | Numeric | Degrees Fahrenheit | Highest recorded body temperature | N/A | Both  
Dose (10^6 cells) | Numeric | Million cells | Dose of CAR-T cells administered in millions of cells | N/A | Both  
Dose (10^6 cells/kg) | Numeric | Million cells/kg | Dose of CAR-T cells administered per kilogram of body weight | N/A | Both  
Bridging Chemo Therapy | Categorical | N/A | The type of bridging chemotherapy administered | Various | Both  
WBC | Numeric | Cells/µL | White Blood Cell count | N/A | Both  
abs Monocyte | Numeric | Cells/µL | Absolute Monocyte count | N/A | Both  
ANC | Numeric | Cells/µL | Absolute Neutrophil count | N/A | Both  
ABS Lymphocyte count | Numeric | Cells/µL | Absolute Lymphocyte count | N/A | Both  
Highest Ferritin | Numeric | ng/mL | Highest Ferritin level recorded | N/A | Both  
Highest CRP | Numeric | mg/L | Highest C-reactive protein level recorded | N/A | Both  
Best Response as of 1_24_2024 | Categorical | N/A | Best response to treatment as of 1/24/2024 | Various | Both  
Date of PD (1_24_24) | Date | N/A | Date of disease progression as of 1/24/2024 | N/A | Both  
Date of Last Response Assess if No PD (1_24_24) | Date | N/A | Date of last response assessment if no disease progression as of 1/24/2024 | N/A | Both  
IL8, TNFRSF9, TIE2, MCP-3, CD40-L, IL-1 alpha, CD244, EGF, ANGPT1, IL7, PGF, IL6, ADGRG1, MCP-1, CRTAM, CXCL11, MCP-4, TRAIL, FGF2, CXCL9, CD8A, CAIX, MUC-16, ADA, CD4, NOS3, IL2, Gal-9, VEGFR-2, CD40, IL18, GZMH, KIR3DL1, LAP TGF-beta-1, CXCL1, TNFSF14, IL33, TWEAK, PDGF subunit B, PDCD1, FASLG, CD28, CCL19, MCP-2, CCL4, IL15, Gal-1, PD-L1, CD27, CXCL5, IL5, HGF, GZMA, HO-1, CX3CL1, CXCL10, CD70, IL10, TNFRSF12A, CCL23, CD5, CCL3, MMP7, ARG1, NCR1, DCN, TNFRSF21, TNFRSF4, MIC-A/B, CCL17, ANGPT2, PTN, CXCL12, IFN-gamma, LAMP3, CASP-8, ICOSLG, MMP12, CXCL13, PD-L2, VEGFA, IL4, LAG3, IL12RB1, IL13, CCL20, TNF, KLRD1, GZMB, CD83, IL12, CSF-1 | Numeric | N/A | The concentration of the respective cytokine or cell marker | N/A | Both   


 
## Contributing  
  
  
  
## License  
  


Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>

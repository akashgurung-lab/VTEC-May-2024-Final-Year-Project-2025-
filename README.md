# 🛰️ A Study of Mid-Latitude Ionospheric VTEC Response to the Severe Geomagnetic Storm of May 2024

## 📜 Abstract

This repository contains the complete analytical framework and thesis documentation for investigating the mid-latitude ionospheric response to the severe geomagnetic storm of May 10-12, 2024, using Vertical Total Electron Content (VTEC) data derived from a global network of nine ground-based GNSS stations. An analysis comparing VTEC variations during the storm with a baseline established from geomagnetically quiet days (May 7-9) is presented, and the ionospheric response is correlated with interplanetary data from the OMNIWeb service.

The storm was characterized by a sustained period of southward IMF Bz and a minimum SYM-H index of -497 nT, classifying it as a severe event. A major positive ionospheric storm was observed on a global scale, with the normal diurnal VTEC pattern being completely disrupted. During the storm's main phase, VTEC values showed a dramatic enhancement, with peaks at some stations exceeding 120 TECU, representing an increase of over 100% compared to the quiet day baseline.

**Note**: This repository serves as the computational component of the corresponding Bachelor's project work. For detailed theoretical background, methodology, and comprehensive analysis, please refer to the complete project paper, **[available here](https://drive.google.com/file/d/15atNYLF-9NCdUYBem1RGAXQNlZ2y193W/view?usp=drive_link)**.

**Key Findings:**
- **Strong Local Time Dependence**: Stations on the dayside during the storm's onset exhibited prompt and intense VTEC enhancement consistent with Prompt Penetration Electric Fields (PPEFs), while stations on the nightside showed a more gradual and delayed response characteristic of the Disturbance Dynamo effect
- **Prolonged Recovery Phase**: VTEC patterns remained disturbed for several days, highlighting the long-lasting impact of the storm's energy input
- **Global Scale Response**: Complete disruption of normal diurnal VTEC patterns across the mid-latitude network
- **Cause-and-Effect Relationships**: Comprehensive characterization of solar wind drivers and the complex, geographically dependent response of the mid-latitude ionosphere

**Note**: This repository serves as the computational component of the corresponding Bachelor's project work. For detailed theoretical background, methodology, and comprehensive analysis, please refer to the complete thesis document.

**Keywords**: VTEC, Geomagnetic Storm, Ionosphere, Prompt Penetration Electric Fields, Disturbance Dynamo Electric Fields

## 🔬 Scientific Motivation

The May 2024 geomagnetic storm represents a unique opportunity to study extreme space weather impacts on the Earth's ionosphere. This event provides critical insights into:

- Solar wind-magnetosphere-ionosphere coupling mechanisms
- Mid-latitude ionospheric response to severe geomagnetic disturbances
- Temporal evolution of storm-induced electric field penetration
- Regional variations in ionospheric disturbance patterns

## 🛠️ Methodology

### Data Sources
- **GNSS Observations**: Raw RINEX data from global IGS stations, accessed via the UNAVCO public data archives.
- **Solar Wind Parameters**: OMNI dataset (`Data/OMNI_PARAMETERS/solar_parameters.txt`) including IMF Bz, solar wind velocity (Vsw), dynamic pressure (Psw), proton density (Np), and temperature (T)
- **Geomagnetic Indices**: SYM-H index (`Data/OMNI_PARAMETERS/SYM-H.txt`) for storm intensity characterization

### ☁️ Data Access
The complete dataset used in this analysis is available via Google Drive:
**Dataset Link**: [https://drive.google.com/drive/folders/1a4euIDKiMGjl0C1NIjEdgRd4FXbBhLuu?usp=sharing](https://drive.google.com/drive/folders/1a4euIDKiMGjl0C1NIjEdgRd4FXbBhLuu?usp=sharing)

This shared folder contains:
- **GNSS Station DATA**: Daily .Cmn files from nine mid-latitude GNSS stations
- **RAW Station DATA**: Contains raw data downloaded from UNAVCO

**Note**: Download the data folder and place it in your local repository directory to run the analysis notebooks.

### Analysis Framework
1. **Data Processing**: Standardized pipeline for multi-day, multi-station GNSS data in .Cmn format implemented in interactive Jupyter notebooks
2. **VTEC Calculation**: Systematic derivation of slant TEC to VTEC conversion with step-by-step visualization
3. **Disturbance Quantification**: Percentage deviation analysis (dTEC) relative to quiet-day baseline with interactive plots
4. **Correlation Analysis**: Statistical assessment of ionospheric response to solar wind drivers (IMF Bz, Vsw, Psw, Np, T) and geomagnetic indices using pandas and numpy

## 📁 Repository Structure

```
├── Code/
│   ├── VTEC_Variation/
│   │   ├── VTEC_IN_QUIET_DAYS.ipynb      # Quiet day VTEC analysis (May 7-9)
│   │   ├── VTEC_IN_RECOVERY_DAYS.ipynb   # Recovery phase analysis (May 13-15)
│   │   └── VTEC_IN_STORM_DAYS.ipynb      # Storm phase analysis (May 10-12)
│   ├── dTEC_VARIATION.ipynb              # Disturbance quantification
│   ├── vtec_plot_for_storm_day.ipynb     # Storm day visualization
│   ├── GNSS_PLOT.ipynb                   # Global station distribution map
│   └── Omni_parameters.ipynb             # Solar wind and geomagnetic analysis
├── Data/
│   └── OMNI_PARAMETERS/
│       ├── SYM-H.txt                     # Storm-time geomagnetic index
│       └── solar_parameters.txt          # Solar wind parameters (Bz, Vsw, Psw, Np, T)
├── PLOTS/
│   ├── corrected_dTEC_variation_15min.pdf    # Multi-station dTEC analysis
│   ├── simplified_space_weather_analysis.pdf # Solar wind conditions
│   ├── station_map_final.pdf                 # GNSS station distribution
│   ├── vtec_plot_for_quiet_days.pdf          # Baseline VTEC behavior
│   ├── vtec_plot_for_recovery.pdf            # Recovery phase VTEC
│   └── vtec_plot_for_storm_day.pdf           # Storm phase VTEC
├── requirements.txt            # Python dependencies
└── README.md
```

## ⚙️ Technical Requirements

### Dependencies
```python
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.4.0
seaborn>=0.11.0
cartopy>=0.20.0
jupyter>=1.0.0
```

### Installation and Setup
```bash
git clone https://github.com/akashgurung-lab/VTEC-May-2024-Final-Year-Project-2025-.git
cd VTEC-May-2024-Final-Year-Project-2025-
pip install -r requirements.txt
```

### Data Setup
1. **Download the dataset** from the provided Google Drive link
2. **Extract and organize** the data folder in your local repository directory
3. **Verify data paths** in the notebooks match your local directory structure
4. **Launch Jupyter**: `jupyter notebook`

**Important**: Ensure all data file paths in the notebooks correspond to your local data organization before running the analysis.

## 📄 Data Format Specifications

### GNSS Data (.Cmn format)
Generated by GOPI SEEMALA GPS-TEC analysis program from RINEX files:
- Temporal resolution: 30-second intervals
- Parameters: Slant TEC, elevation angle, azimuth, satellite PRN
- **Access**: Available via the Google Drive dataset link above
- **Format**: Daily files organized by station and date

### Solar Wind Data
OMNI high-resolution dataset parameters:
- **IMF Bz**: Interplanetary magnetic field z-component (nT)
- **Vsw**: Solar wind velocity (km/s)
- **Psw**: Solar wind dynamic pressure (nPa)
- **Np**: Solar wind proton density (cm⁻³)
- **T**: Solar wind temperature (K)
- **SYM-H**: Storm-time geomagnetic index (nT)

## 🗺️ Analysis Workflow

The analysis is conducted through a series of Jupyter notebooks organized by functionality. Execute the notebooks based on your specific analysis requirements.

### 1. Solar Wind and Geomagnetic Conditions
```bash
jupyter notebook Code/Omni_parameters.ipynb
```
Analyzes solar wind parameters (IMF Bz, Vsw, Psw, Np, T) and SYM-H index to characterize the geomagnetic storm conditions. Generates `simplified_space_weather_analysis.pdf`.

### 2. GNSS Station Network
```bash
jupyter notebook Code/GNSS_PLOT.ipynb
```
Creates global distribution map of GNSS stations with geographic coordinates and coverage assessment. Generates `station_map_final.pdf`.

### 3. VTEC Analysis During Different Phases

#### Quiet Day Analysis
```bash
jupyter notebook Code/VTEC_Variation/VTEC_IN_QUIET_DAYS.ipynb
```
Establishes baseline VTEC behavior during magnetically quiet conditions (May 7-9, 2024). Generates `vtec_plot_for_quiet_days.pdf`.

#### Storm Phase Analysis
```bash
jupyter notebook Code/VTEC_Variation/VTEC_IN_STORM_DAYS.ipynb
jupyter notebook Code/vtec_plot_for_storm_day.ipynb
```
Examines VTEC variations during the main phase of the geomagnetic storm (May 10-12, 2024). Generates `vtec_plot_for_storm_day.pdf`.

#### Recovery Phase Analysis
```bash
jupyter notebook Code/VTEC_Variation/VTEC_IN_RECOVERY_DAYS.ipynb
```
Investigates ionospheric recovery processes following storm cessation (May 13-15, 2024). Generates `vtec_plot_for_recovery.pdf`.

### 4. Disturbance Quantification
```bash
jupyter notebook Code/dTEC_VARIATION.ipynb
```
Calculates percentage VTEC deviations and generates comprehensive multi-station disturbance analysis. Generates `corrected_dTEC_variation_15min.pdf`.

## 📈 Scientific Results

### Storm Characteristics
- **IMF Conditions**: Sustained period of southward IMF Bz driving magnetospheric coupling
- **Storm Intensity**: Minimum SYM-H index of -497 nT, classifying it as a severe geomagnetic event
- **Global Impact**: Complete disruption of normal diurnal VTEC patterns across mid-latitude regions

### Ionospheric Response Patterns
- **Peak Enhancement**: VTEC values exceeding 120 TECU at some stations
- **Relative Increase**: Over 100% enhancement compared to quiet day baseline
- **Local Time Dependence**: 
  - **Dayside Response**: Prompt and intense VTEC enhancement consistent with Prompt Penetration Electric Fields (PPEFs)
  - **Nightside Response**: Gradual and delayed response characteristic of Disturbance Dynamo effects

### Recovery Phase Characteristics
- **Duration**: Prolonged recovery with VTEC patterns remaining disturbed for several days
- **Impact Assessment**: Long-lasting effects highlighting the significant energy input from the storm
- **Geographic Variations**: Complex, location-dependent recovery patterns across the global network

## 🎓 Documentation and Thesis

This repository accompanies the comprehensive thesis: **"A Study of Mid-Latitude Ionospheric VTEC Response to the Severe Geomagnetic Storm of May 2024"**

The complete project paper, including detailed analysis and discussion, can be accessed directly via the link below.

➡️ **[View the Full Project Paper on Google Drive (PDF)](https://drive.google.com/file/d/15atNYLF-9NCdUYBem1RGAXQNlZ2y193W/view?usp=drive_link)**

### Repository Purpose
This computational repository provides:
- **Reproducible Analysis**: All data processing and visualization code
- **Interactive Exploration**: Jupyter notebooks for step-by-step analysis
- **Code Documentation**: Detailed comments and explanations for each analytical step
- **Data Transparency**: Complete workflow from raw data to final results

The notebooks in this repository generate the figures and results presented in the thesis, ensuring full reproducibility of the research findings.

## 🤝 Contributing to the Scientific Community

We encourage contributions from the space weather research community:

### For Researchers
- Access complete thesis and dataset for comprehensive theoretical background
- Extend analysis to additional geographic regions using provided notebooks and data
- Implement alternative TEC processing algorithms with the available .Cmn files
- Add comparative analysis with physics-based models using the standardized dataset

### For Students
- Use as reference for ionospheric physics research methodologies
- Adapt Jupyter notebooks for similar geomagnetic storm studies
- Learn GNSS data processing and visualization techniques with real datasets
- Understand space weather impact assessment procedures with comprehensive examples

### Data Usage Guidelines
- **Citation Required**: Please cite the thesis when using the dataset
- **Data Integrity**: Maintain original data format and quality flags
- **Methodology**: Reference the processing pipeline when adapting the analysis
- **Collaboration**: Contact for questions about data interpretation or methodology

### For Data Scientists
- Develop machine learning approaches for storm prediction
- Implement automated detection algorithms for ionospheric disturbances
- Create real-time processing pipelines

### Contribution Guidelines
1. Fork the repository
2. Create feature branch: `git checkout -b feature/analysis-enhancement`
3. Implement changes with appropriate documentation
4. Add unit tests for new functionality
5. Submit pull request with detailed description

## 📝 Citation

If you use this code, methodology, or findings in your research, please cite the project report:

```bibtex
@techreport{gurung2024vtec,
  title={A Study of Mid-Latitude Ionospheric VTEC Response to the Severe Geomagnetic Storm of May 2024},
  author={Gurung, Akash},
  year={2024},
  institution={[St. Xavier's College, Kathmandu]},
  type={Bachelor's Project Work (TU)},
  url={https://drive.google.com/file/d/15atNYLF-9NCdUYBem1RGAXQNlZ2y193W/view?usp=drive_link}
}
```

### Related Publications
If this work leads to journal publications, they will be listed here with appropriate citation information.

## 🙏 Acknowledgments

This research was made possible through:
- **UNAVCO**: For providing public access to the raw GNSS RINEX observation data used in this study.
- **GOPI SEEMALA GPS-TEC Analysis Program**: RINEX to TEC processing capabilities
- **NASA OMNIWeb Service**: Solar wind and geomagnetic data provision
- **International GNSS Service (IGS)**: Global network maintenance and data distribution
- **Space Weather Research Community**: Ongoing collaboration and data sharing initiatives

## 📧 Contact Information

**Principal Investigator**: Akash Gurung  
**Institution**: [St. Xavier's College, Kathmandu]  
**Email**: [gurunglienux11@gmail.com]  

For technical inquiries, please open an issue on GitHub. For collaboration opportunities, contact the PI directly.

---

**Keywords**: VTEC, Geomagnetic Storm, Ionosphere, Prompt Penetration Electric Fields, Disturbance Dynamo Electric Fields, Mid-Latitude Response, Solar Wind-Magnetosphere Coupling

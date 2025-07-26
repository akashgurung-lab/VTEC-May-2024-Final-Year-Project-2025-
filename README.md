# Mid-Latitude Ionospheric VTEC Response to the Severe G5 Geomagnetic Storm of May 2024

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📜 Overview

[cite_start]This repository contains the Python-based data analysis and visualization pipeline for the research project, **"A Study of Mid-Latitude Ionospheric VTEC Response to the Severe Geomagnetic Storm of May 2024"**[cite: 1, 2]. [cite_start]This work presents a comprehensive analysis of the ionospheric disturbances recorded by a global network of nine mid-latitude GNSS stations following the historic G5-level geomagnetic storm of May 10-12, 2024. The storm, triggered by a series of powerful CMEs from the merged active regions 13664 and 13668, was the most intense in over two decades, providing a rare opportunity to study the near-Earth space environment under extreme forcing[cite: 521, 522].

The scripts included here process raw GNSS data to derive Vertical Total Electron Content (VTEC), correlate ionospheric behavior with solar wind parameters, and quantify the storm's impact using percentage deviation (dTEC). [cite_start]The analysis clearly distinguishes between the initial, rapid VTEC enhancements driven by **Prompt Penetration Electric Fields (PPEFs)** and the delayed, prolonged disturbances associated with the **Disturbance Dynamo Electric Field (DDEF)**[cite: 89, 90].

This event serves as a unique natural laboratory, and this codebase provides the tools to reproduce the key findings of our study, which include:
* [cite_start]A massive, dayside-dominant positive ionospheric storm, with VTEC enhancements exceeding **700%** above quiet-day levels[cite: 1103].
* [cite_start]A subsequent, widespread negative storm phase with VTEC depletions reaching **-80%**[cite: 1104].
* A clear illustration of the spatio-temporal evolution of ionospheric phenomena across different geographical longitudes.

We encourage fellow researchers in the space weather and ionospheric physics communities to use and adapt this code for further analysis of this significant event.

---

## 🛰️ Features

* **Data Processing**: Scripts for parsing, cleaning, and merging multi-day, multi-station GNSS data files.
* **VTEC Calculation**: Leverages the output from standard TEC processing software (see Acknowledgements) to prepare data for scientific analysis.
* [cite_start]**Quantitative Disturbance Analysis**: Calculates the percentage deviation of VTEC (dTEC) to normalize and quantify the ionospheric response relative to a quiet-day baseline[cite: 658, 662].
* [cite_start]**Correlation Analysis**: Generates multi-panel plots aligning ionospheric data with key solar wind parameters (IMF $B_{z}$, $V_{sw}$, $P_{sw}$) and geomagnetic indices (SYM-H) to establish cause-and-effect relationships[cite: 548].
* **Publication-Quality Visualizations**: Creates high-quality, multi-panel time-series plots using Matplotlib and Seaborn, complete with annotations and clear labeling, suitable for scientific publications and presentations. The code includes modules to plot:
    * [cite_start]GNSS Station Distribution Map [cite: 1190]
    * [cite_start]Solar Wind and Geomagnetic Conditions [cite: 1322]
    * [cite_start]Quiet Day VTEC Behavior [cite: 1805]
    * [cite_start]Storm Period VTEC Disturbance [cite: 2142]
    * [cite_start]Recovery Phase VTEC Analysis [cite: 2447]
    * [cite_start]Comprehensive dTEC Variation Plots [cite: 2783]

---

## 🚀 Getting Started

### Prerequisites

To run these scripts, you will need Python 3.x and the following libraries installed:
* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
* `cartopy`

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Install the required packages:**
    ```bash
    pip install numpy pandas matplotlib seaborn cartopy
    ```

### Data Requirements

The scripts are structured to process specific data formats. Place your data in the appropriate directories as referenced in the scripts.

* [cite_start]**GNSS Data**: Daily station data in the `.Cmn` format, which is the output of the **GOPI SEEMALA GPS-TEC analysis program**[cite: 72, 607]. This software is used to process raw RINEX files. The scripts expect a directory structure like `/STATIONS/[STATION_NAME]/[filename].Cmn`.
* **Solar Wind & Geomagnetic Data**:
    * [cite_start]**OMNIWeb Data**: Hourly solar wind and IMF parameters obtained from the [NASA/GSFC's OMNIWeb Plus data service](https://omniweb.gsfc.nasa.gov/) in a text format[cite: 596, 604].
    * [cite_start]**SYM-H Index**: 5-minute resolution SYM-H index data from the [World Data Center for Geomagnetism, Kyoto](https://wdc.kugi.kyoto-u.ac.jp/)[cite: 602, 775].

---

## ⚙️ Usage

The codebase is organized into several Python scripts, each responsible for a specific part of the analysis. The scripts are extensively commented for clarity.

1.  [cite_start]`6.1_station_map.py`: Generates a global map showing the geographical distribution of the GNSS stations used in the study[cite: 1190].
2.  [cite_start]`6.2_solar_wind_plot.py`: Parses and plots the OMNI solar wind data and the SYM-H index, creating the foundational time-series plot of the storm's drivers and geomagnetic response[cite: 1322].
3.  [cite_start]`6.3_quiet_day_analysis.py`: Processes and plots VTEC data for the quiet days (May 7-9) to establish a baseline[cite: 1805].
4.  [cite_start]`6.4_storm_day_analysis.py`: Plots VTEC data for the main storm phase (May 10-12) for comparative analysis[cite: 2142].
5.  [cite_start]`6.5_recovery_phase_analysis.py`: Plots VTEC data for the recovery period (May 13-15) to analyze long-lasting effects[cite: 2447].
6.  [cite_start]`6.6_dTEC_calculation.py`: The core script that calculates dTEC by comparing storm days to the quiet-day baseline and generates the final multi-station dTEC visualization[cite: 2783].

To run a specific analysis, execute the desired script from your terminal:
```bash
python 6.6_dTEC_calculation.py

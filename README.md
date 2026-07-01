# Processed Seismic Datasets for the 2020 Elazığ Earthquakes (Mw 6.8 and Mw 5.3)

This repository contains the processed datasets generated during the study of the 2020 Elazığ-Türkiye earthquakes. The data were derived from 31-day continuous-time broadband seismic station records, filtered, and segmented using a sliding window technique to analyze the temporal evolution of chaotic parameters.

## Signal Processing and Windowing Details
To ensure signal continuity and stability for chaotic analysis, the raw seismic records were preprocessed with the following steps:

* **Preprocessing:** Gaps in the raw records were detected. The signals were then detrended, band-pass filtered (0.1–2.0 Hz), and downsampled to 5 Hz.
* **Segmentation:** The signals were split into 200-second windows. Each window contains 1,000 data points, a 75% overlapping windowing technique was applied.
* **Normalization:** Each segment was normalized separately using an adaptive z-normalization method. 

## Data Description
The repository includes two processed CSV files representing different seismic events:

* **`ELZG_Mw6_8_2020_01_09-2020_02_08_N_windows_labeled.csv`**: Contains the segmented raw/normalized signal metrics and calculated non-linear features (Lyapunov exponents, Correlation Dimension, Sample Entropy) for the Mw 6.8 mainshock period.
* **`ELZG_Mw5_3_2020_12_12-2021_01_11_N_windows_labeled.csv`**: Contains the identical feature set calculated for the Mw 5.3 earthquake period.

### Data Dictionary (Column Details)

* **`Window_ID`**: Unique identifier for the segmented signal window.
* **`Time_Min`**: Time step in minutes.
* **`Raw_Mean`**: Mean value of the raw seismic signal.
* **`Raw_Std`**: Standard deviation of the raw seismic signal.
* **`Raw_Min`**: Minimum amplitude of the raw signal.
* **`Raw_Max`**: Maximum amplitude of the raw signal.
* **`Norm_Min`**: Minimum amplitude of the normalized signal.
* **`Norm_Max`**: Maximum amplitude of the normalized signal.
* **`Activity_Std`**: Standard deviation representing seismic activity.
* **`Wolf_LyE`**: Largest Lyapunov Exponent calculated using Wolf's algorithm.
* **`Rosenstein_LyE`**: Largest Lyapunov Exponent calculated using Rosenstein's algorithm.
* **`Samp_Ent`**: Sample Entropy of the signal.
* **`CorDim`**: Correlation Dimension of the reconstructed phase space for the given windowed signal.
* **`Time_Interval`**: The time range covered by the current window.
* **`Magnitude`**: Earthquake magnitude.
* **`Latitude`**: Latitude coordinate of the event.
* **`Longitude`**: Longitude coordinate of the event.
* **`Distance_km`**: Earthquake epicenter distance from the station in kilometers.
* **`Distance_Degree`**: Earthquake epicentral distance from the station in degrees.
* **`Direction`**: Azimuth or directional information between the earthquake and the station.
* **`Earthquake_Count`**: Total number of earthquake events in the given window.
* **`Label`**: Classification label assigned to the window for data-driven modeling.

## Data Availability Statement
* **Raw Data:** The raw seismic waveform data of the 2020 Elazığ-Sivrice earthquake were provided by the AFAD Turkish Earthquake Data Center System (TDVMS). These raw data can be accessed directly from the original provider. (Disaster and Emergency Management Authority (AFAD), Continuous seismic data (2026). URL https://tdvms.afad.gov.tr/continuous_data)
* **Code Availability:** The customized analytical codes developed for this study are tied to an ongoing platform development and are not publicly shared at this time.

## Citation
If you use these datasets in your research, please cite the following conference paper:

Z. Çalım, S. Çimen, T. Yıldırım, and Ş. Ersoy, "Analysis and Visualization of Seismic Activity Before and After a Major Earthquake for Earthquake Prediction in High-Risk Areas," 2025 33rd Signal Processing and Communications Applications Conference (SIU), Sile, Istanbul, Turkiye, 2025, pp. 1-4, doi: 10.1109/SIU66497.2025.11111859.

**BibTeX:**
```bibtex
@inproceedings{calim2025analysis,
  author    = {Çalım, Zeynep and Çimen, Sibel and Yıldırım, Tülay and Ersoy, Şükrü},
  booktitle = {2025 33rd Signal Processing and Communications Applications Conference (SIU)},
  title     = {Analysis and Visualization of Seismic Activity Before and After a Major Earthquake for Earthquake Prediction in High-Risk Areas},
  year      = {2025},
  pages     = {1--4},
  doi       = {10.1109/SIU66497.2025.11111859}
}

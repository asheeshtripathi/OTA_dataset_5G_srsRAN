# OTA_dataset_5G_srsRAN  
[![IEEE Paper](https://img.shields.io/badge/IEEE%20WCNC%202025-Paper-blue)](https://doi.org/10.1109/WCNC61545.2025.10978285)

 
This repository contains the over-the-air throughput and received signal strength measurements collected and analyzed for the following paper:

**A. Tripathi, F. Bashar, M. R. Chowdhury, A. Da Silva and S. F. Midkiff,  
"Benchmarking Software Defined Radio Based 5G Deployments With srsRAN: Lessons Learned,"  
2025 IEEE Wireless Communications and Networking Conference (WCNC), Milan, Italy, 2025, pp. 1-6.**  
[https://doi.org/10.1109/WCNC61545.2025.10978285](https://doi.org/10.1109/WCNC61545.2025.10978285)

  

The dataset was collected using various USRP (Universal Software Radio Peripheral) devices under different transmission modes and configurations. It is structured into multiple folders and files for easy navigation and understanding.
 
## Repository Structure
 
The repository contains the following top-level folders:
 
- **B210**
- **N310**
- **X310**
 
Each folder corresponds to a specific model of the USRP device used for data collection. Additionally, there are two important CSV files:
 
- **usrp_rssi_data_organized.csv** – This file contains the final received signal strength measurements (by COTS UE).
- **final_performance_evaluations.csv** – This file contains the final combined performance evaluation metrics, which were used to generate the graphs in the paper. It has pilot measurements and the final measurements sheets.
 
### USRP Model Folders (B210, N310, X310)
 
Each of the USRP model folders contains subdirectories for **uplink (UL)** and **downlink (DL)** transmission modes. Inside each of these transmission mode directories, there are further directories corresponding to four different scenarios.
 
#### Scenario Overview
 
The following table outlines the different scenarios, including key configuration parameters for each of the USRP models:
 
| **SDR**  | **Scenario** | **Master Clock Rate** | **Srate** | **Tx and Rx Gains** | **LO Offset** |
|----------|--------------|-----------------------|-----------|---------------------|---------------|
| **X310** | Scenario-1   | 184.32 MHz            | 23.04     | Tx 31, Rx 34        | 0             |
|          | Scenario-2   | 184.32 MHz            | 30.72     | Tx 31, Rx 34        | 0             |
|          | Scenario-3   | 184.32 MHz            | 23.04     | Tx 31, Rx 34        | 23.04         |
|          | Scenario-4   | 184.32 MHz            | 30.72     | Tx 31, Rx 34        | 30.72         |
| **N310** | Scenario-1   | 122.88 MHz            | 30.72     | Tx 62, Rx 75        | 0             |
|          | Scenario-2   | 122.88 MHz            | 30.72     | Tx 62, Rx 75        | 11.52         |
|          | Scenario-3   | 122.88 MHz            | 30.72     | Tx 62, Rx 75        | 23.04         |
|          | Scenario-4   | 122.88 MHz            | 30.72     | Tx 62, Rx 75        | 30.72         |
| **B210** | Scenario-1   | 23.04 MHz             | 23.04     | Tx 89, Rx 60        | 0             |
|          | Scenario-2   | 30.72 MHz             | 30.72     | Tx 89, Rx 60        | 0             |
|          | Scenario-3   | 46.08 MHz             | 23.04     | Tx 89, Rx 60        | 11.52         |
|          | Scenario-4   | 61.44 MHz             | 30.72     | Tx 89, Rx 60        | 11.52         |
 
Each **USRP model** folder contains subdirectories for:
 
- **UL** (Uplink)
- **DL** (Downlink)
 
Within each of these directories, you will find further subdirectories corresponding to the **four scenarios**. Each file inside these directories follows the naming schema:
 
`<USRP>_<Scenario>_<Iteration>_<Distance>_<UL or DL>.csv`
 

For example, a file named `X310_Scenario-1_1_10_UL.csv` represents the following:
 
- **X310**: The USRP model used.
- **Scenario-1**: The scenario as outlined in the table.
- **Iteration-1**: The first iteration of data collection for this scenario.
- **Distance-10**: The distance between the transmitter and receiver.
- **UL**: The uplink transmission mode (could also be DL for downlink).
 
## Data Files
 
- **usrp_rssi_data_organized.csv**: This file contains the final received signal strength(as measured by COTS UE) measurements. The RSSI values are organized for easy analysis and comparison across different devices and scenarios.
- **final_performance_evaluations.csv**: This file includes the final combined measurements used to generate the graphs presented in the paper. These performance evaluations were derived from the data collected under the various configurations and scenarios.

The summary of final OTA throughput performance and received signal strength with varying distances is visualized in the graphs below.

📌 **These figures are directly adapted from the results presented in our WCNC 2025 paper**  
(see full citation at the top or in the Citation section below for details on the experiment design and analysis).

### 📈 Throughput vs Distance
![image](https://github.com/user-attachments/assets/95775470-2785-4547-b089-587b4b2b81e4)

### 📉 Signal Strength vs Distance
![image](https://github.com/user-attachments/assets/7aabd209-cf72-4429-8290-0a8adc8f0069)


  
 
## How to Use This Repository
 
### 1. Exploring the Data
 
You can explore the dataset by navigating to the appropriate USRP model folder (B210, N310, or X310), and then selecting the desired transmission mode (UL or DL). Inside these folders, you will find the CSV files for each scenario and iteration.
 
### 2. Analyzing RSSI and Performance Data
 
- **RSSI Data**: The `usrp_rssi_data_organized.csv` file contains all the necessary RSSI measurements across different scenarios. You can analyze these measurements to compare signal strength variations for different configurations.
- **Performance Data**: The `final_performance_evaluations.csv` file provides the summarized performance evaluation metrics, which were used to generate the graphs in the paper. This includes various key performance indicators for each of the transmission modes and configurations.
 
### 3. Scenario Analysis
 
Each scenario in the dataset corresponds to a specific set of configuration parameters. Refer to the table above for details on each scenario. The USRP configurations, master clock rates, sample rates, transmission and reception gains, and local oscillator offsets are critical for understanding the context of each measurement.
 
### 4. File Naming Conventions
 
To ensure consistency, each file in the repository follows this naming schema:
 
`<USRP>_<Scenario>_<Iteration>_<Distance>_<UL or DL>.csv`
 

Where:
- **USRP** is the model (B210, N310, or X310),
- **Scenario** is the specific configuration scenario (Scenario-1 to Scenario-4),
- **Iteration** is the iteration number of data collection for the scenario,
- **Distance** refers to the distance between the transmitter and receiver (in meters),
- **UL or DL** refers to whether the data was collected during uplink or downlink transmission mode.
 
## Citation

If you use this dataset in your research or projects, please cite the following paper:

> A. Tripathi, F. Bashar, M. R. Chowdhury, A. Da Silva and S. F. Midkiff,  
> "**Benchmarking Software Defined Radio Based 5G Deployments With srsRAN: Lessons Learned**,"  
> *2025 IEEE Wireless Communications and Networking Conference (WCNC)*, Milan, Italy, 2025, pp. 1–6.  
> [https://doi.org/10.1109/WCNC61545.2025.10978285](https://doi.org/10.1109/WCNC61545.2025.10978285)


## Contact
 
For further information or inquiries regarding the dataset, please contact the authors at:
 
- **Asheesh Tripathi**: asheesh@vt.edu
- **Fahim Bashar**: fahimbashar@vt.edu
---
 
We hope this dataset and the paper supports your research on benchmarking Software Defined Radio (SDR) systems, particularly in the context of 5G deployments. This dataset is intended for use in O-RAN-based machine learning model training, leveraging over-the-air (OTA) throughput and received signal strength metrics collected from a real-world 5G indoor deployment. Potential use cases include digital twins, intelligent resource allocation, QoS/QoE optimization, load balancing, and other RAN-level decision-making tasks.


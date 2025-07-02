# SM_residential_Portugal



## 📊 Energy Dataset – HAN Interface from E-REDES
Smart meter eletricity data collected through HAN port for residential sector in Portugal. Each Parquet file corresponds to one calendar month of continuous data collection and is organized by timestamp, measurement channel, and device identifier.

---

### 📁 Test Files Provided

Two datasets examples are available for testing and demonstration purposes:

1. **Longitudinal Dataset:**

   * Contains **multi-month data** from **two individual consumption points** .
   * Suitable for **time series analysis**, device-level profiling, and behavioral modeling.

2. **Cross-sectional Dataset:**

   * Contains **two months of data** from **dozens of consumption points**.
   * Suitable for **comparative studies**, cluster analysis, and anomaly detection across users.

---

### 🔧 Dataset Structure

* **Format:** Parquet
* **Temporal Granularity:** Minute-level
* **Devices:** Identified by `device_slug`
* **Channels Available:** 19
* **Columns:**

| Column         | Description                                              |
| -------------- | -------------------------------------------------------- |
| `timestamp`    | Measurement date and time                                |
| `entry_id`     | Unique identifier for each measurement                   |
| `device_slug`  | Unique identifier of the smart meter or device           |
| `channel_name` | Name of the measurement channel (see below)              |
| `channel_type` | Type of value (e.g., `number`, `total`, `dif`)           |
| `number`       | Absolute meter reading                                   |
| `total`        | Accumulated value                                        |
| `dif`          | Delta value between consecutive measurements (increment) |

---

### ⚡ Tariff-based Active Energy Channels

| Channel | Description                              | Unit | Direction |
| ------- | ---------------------------------------- | ---- | --------- |
| `r1iae` | Active energy import – Off-peak (rate 1) | kWh  | Import    |
| `r2iae` | Active energy import – Peak (rate 2)     | kWh  | Import    |
| `r3iae` | Active energy import – Shoulder (rate 3) | kWh  | Import    |
| `r1eae` | Active energy export – Off-peak (rate 1) | kWh  | Export    |
| `r2eae` | Active energy export – Peak (rate 2)     | kWh  | Export    |
| `r3eae` | Active energy export – Shoulder (rate 3) | kWh  | Export    |
| `tiae`  | Active energy import – Total             | kWh  | Import    |
| `teae`  | Active energy export – Total             | kWh  | Export    |

---

### 🔋 Phase-specific Active Energy (HAN Measurements)

| Channel  | Description                             | Unit | Direction |
| -------- | --------------------------------------- | ---- | --------- |
| `hl1iae` | Phase L1 forward active energy (import) | kWh  | Import    |
| `hl2iae` | Phase L2 forward active energy (import) | kWh  | Import    |
| `hl3iae` | Phase L3 forward active energy (import) | kWh  | Import    |
| `hl1eae` | Phase L1 reverse active energy (export) | kWh  | Export    |
| `hl2eae` | Phase L2 reverse active energy (export) | kWh  | Export    |
| `hl3eae` | Phase L3 reverse active energy (export) | kWh  | Export    |

---

### ⚙️ Instantaneous Measurements

| Channel | Description                       | Unit |
| ------- | --------------------------------- | ---- |
| `iapi`  | Instantaneous active power import | W    |
| `iape`  | Instantaneous active power export | W    |
| `ivl1`  | Instantaneous voltage L1          | V    |
| `ivl2`  | Instantaneous voltage L2          | V    |
| `ivl3`  | Instantaneous voltage L3          | V    |

---

### ✅ Use Cases and Applications

* Time series energy consumption and export analysis
* Phase balancing and power quality assessment
* Tariff impact and optimization
* Behavioral profiling and appliance-level inference
* Autoconsumption vs. grid injection analytics
* Anomaly detection and forecasting



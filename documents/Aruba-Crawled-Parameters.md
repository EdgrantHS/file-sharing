# Aruba Crawling Parameter

This document outlines the parameters crawled from Aruba networking devices. The data is categorized into several sections, each providing specific details about the network's performance and status.

## Table of Contents

- [Aruba Crawling Parameter](#aruba-crawling-parameter)
  - [Table of Contents](#table-of-contents)
  - [📊 Summary of Crawled Parameters](#-summary-of-crawled-parameters)
  - [📶 AP (Access Point) Data](#-ap-access-point-data)
    - [AP Radio Information](#ap-radio-information)
    - [AP Radio Stats](#ap-radio-stats)
    - [AP Active Details](#ap-active-details)
    - [Example: AP Active Summary](#example-ap-active-summary)
    - [Example: AP Radio Stats](#example-ap-radio-stats)
    - [Example: AP Active Details](#example-ap-active-details)
  - [📱 STA (Station) Data](#-sta-station-data)
    - [Example: STA Data](#example-sta-data)
  - [📡 RSSI (Received Signal Strength Indication) Data](#-rssi-received-signal-strength-indication-data)
    - [Example: AP RSSI](#example-ap-rssi)
    - [Example: STA RSSI](#example-sta-rssi)
  - [⚙️ Utilization](#️-utilization)
    - [Example: Utilization](#example-utilization)
  - [🔌 Switch Data](#-switch-data)
    - [Example: Switch AP Throughput](#example-switch-ap-throughput)
    - [Example: Switch AP Power](#example-switch-ap-power)
  - [⏱️ Crawler Runtime](#️-crawler-runtime)

## 📊 Summary of Crawled Parameters

The following table provides a comprehensive list of all data points collected.

| Category | Parameters |
| :--- | :--- |
| **AP Data** | |
| AP Radio Information | Radio Band, Noise Floor, Utilization, Interference, rx\_time, tx\_time |
| AP Radio Stats | AP Name, MAC Address, Radio Band, Tx Bytes Transmitted, Rx Total Bytes Recvd, tx\_throughput, rx\_throughput, total\_throughput |
| AP Active Details | AP Name, Radio Band, Channel, EIRP, MaxEIRP, Clients, Active Clients, IP Address |
| **STA Data** | |
| STA | STA Address, bssid-name, radio\_band, Station Rx Total Bytes Recvd, Station Tx Bytes Transmitted, Tx Throughput, Rx Throughput, Total Throughput, Username, Device, Speed, SNR |
| **RSSI Data** | |
| AP RSSI | Receiver AP Name, Radio Band, Source AP BSSID Name, Source AP BSSID, Source AP Name, Received SNR, RSSI |
| STA RSSI | Receiver AP Name, Radio Band, Source STA MAC, Received SNR, RSSI |
| **Utilization** | |
| CPU Load | user, system, idle |
| Memory | total, used, free |
| **Switch Data** | |
| Switch Throughput | Wired MAC Address Converted, In Octets, Out Octets, PoE Type, Bridge Index, Port Index, AP Name, Wired MAC Address, in\_throughput, out\_throughput, total\_throughput, PoE Port |
| Switch Power | Wired MAC Address Converted, peak, average, current, PoE Type, Bridge Index, Port Index, AP Name, Wired MAC Address, PoE Port |

-----

## 📶 AP (Access Point) Data

This section details the information collected for each Access Point.

### AP Radio Information

  * **Radio Band**
  * **Noise Floor**
  * **Utilization**
  * **Interference**
  * **rx\_time**
  * **tx\_time**

### AP Radio Stats

  * **AP Name**
  * **MAC Address**
  * **Radio Band**
  * **Tx Bytes Transmitted**
  * **Rx Total Bytes Recvd**
  * **tx\_throughput**
  * **rx\_throughput**
  * **total\_throughput**

### AP Active Details

  * **AP Name**
  * **Radio Band**
  * **Channel**
  * **EIRP**
  * **MaxEIRP**
  * **Clients**
  * **Active Clients**
  * **IP Address**

### Example: AP Active Summary

```json
{
    "AP Name": "Balairung-Barat Luar 1",
    "IP Address": "[REDACTED]",
    "AP Radio Information": {
        "Radio Band": "5 GHz",
        "Noise Floor": -96,
        "Utilization": 58,
        "Interference": 1,
        "rx_time": 53,
        "tx_time": 4
    }
},
{
    "AP Name": "Balairung-Barat Luar 1",
    "IP Address": "[REDACTED]",
    "AP Radio Information": {
        "Radio Band": "2.4 GHz",
        "Noise Floor": -93,
        "Utilization": 19,
        "Interference": 9,
        "rx_time": 7,
        "tx_time": 3
    }
}
```

### Example: AP Radio Stats

```json
{
    "AP Name": "Balairung-Barat Luar 1",
    "MAC Address": "[REDACTED]",
    "AP Radio Stats": [
        {
            "Radio Band": "5 GHz",
            "Tx Bytes Transmitted": 13023673817,
            "Rx Total Bytes Recvd": 6199671965,
            "tx_throughput": 135046.8187501013,
            "rx_throughput": 6963.685971444798,
            "total_throughput": 142010.50472154608
        },
        {
            "Radio Band": "2.4 GHz",
            "Tx Bytes Transmitted": 1635425982,
            "Rx Total Bytes Recvd": 372255449,
            "tx_throughput": 49105.22312791981,
            "rx_throughput": 11477.071948820809,
            "total_throughput": 60582.295076740615
        },
        {
            "Radio Band": "6 GHz",
            "Tx Bytes Transmitted": 952,
            "Rx Total Bytes Recvd": 888,
            "tx_throughput": 0.0,
            "rx_throughput": 0.0,
            "total_throughput": 0.0
        }
    ]
}
```

### Example: AP Active Details

```json
{
    "AP Name": "Balairung-Barat Luar 1",
    "IP Address": "[REDACTED]",
    "AP Radio Stats": [
        {
            "Radio Band": "5 GHz",
            "Channel": "64E",
            "EIRP": 15.0,
            "MaxEIRP": 15.0,
            "Clients": 2
        },
        {
            "Radio Band": "2.4 GHz",
            "Channel": 6,
            "EIRP": 9.0,
            "MaxEIRP": 9.0,
            "Clients": 2
        },
        {
            "Radio Band": "6 GHz",
            "Channel": 85,
            "EIRP": 42.0,
            "MaxEIRP": 42.0,
            "Clients": null
        }
    ],
    "Active Clients": 4
}
```

-----

## 📱 STA (Station) Data

This section outlines parameters related to connected client devices (Stations).

### Example: STA Data

```json
"FT-Gd. Kimia B-4-R.Staff": [
    {
        "STA Address": "[REDACTED]",
        "bssid-name": "HotSpot UI",
        "radio_band": "2.4 GHz",
        "Station Rx Total Bytes Recvd": "77800469",
        "Station Tx Bytes Transmitted": "205743075",
        "Tx Throughput": 4162.402225641727,
        "Rx Throughput": 7822.048396820194,
        "Total Throughput": 11984.450622461922,
        "Username": "",
        "Device": "Win 10",
        "Speed": 72.0,
        "SNR": 52.0
    },
    {
        "STA Address": "[REDACTED]",
        "bssid-name": "HotSpot UI",
        "radio_band": "2.4 GHz",
        "Station Rx Total Bytes Recvd": "47982469",
        "Station Tx Bytes Transmitted": "19678518",
        "Tx Throughput": 6420.0341105877105,
        "Rx Throughput": 11068.46892283011,
        "Total Throughput": 17488.503033417823,
        "Username": "",
        "Device": "iPhone",
        "Speed": 173.0,
        "SNR": 46.0
    }
]
```

-----

## 📡 RSSI (Received Signal Strength Indication) Data

Details on signal strength from the perspective of both APs and STAs.

### Example: AP RSSI

```json
[
    {
        "Receiver AP Name": "FT-ICELL-LIS-KORIDOR-AP4",
        "Radio Band": "5 GHz",
        "Source AP BSSID Name": "eduroam",
        "Source AP BSSID": "[REDACTED]",
        "Source AP Name": "FT-ICELL-LT7-KORIDOR-AP4",
        "Received SNR": 17,
        "RSSI": -81
    },
    {
        "Receiver AP Name": "FT-ICELL-LT8-KORIDOR-AP4",
        "Radio Band": "5 GHz",
        "Source AP BSSID Name": "HotSpot - UI"
    }
]
```

### Example: STA RSSI

```json
[
    {
        "Receiver AP Name": "FT-ICELL-LIS-KORIDOR-AP4",
        "Radio Band": "5 GHz",
        "Source STA MAC": "[REDACTED]",
        "Received SNR": 16,
        "RSSI": -82
    },
    {
        "Receiver AP Name": "FT-ICELL-LT8-KORIDOR-AP4",
        "Radio Band": "5 GHz",
        "Source STA MAC": "[REDACTED]",
        "Received SNR": 10,
        "RSSI": -88
    }
]
```

-----

## ⚙️ Utilization

Provides CPU and memory usage statistics for the controller.

### Example: Utilization

```json
{
    "CPU Load": {
        "user": 12.95,
        "system": 5.25,
        "idle": 81.8
    },
    "Memory": {
        "total": 130900264,
        "used": 26151720,
        "free": 104748544
    }
}
```

-----

## 🔌 Switch Data

Information regarding switch throughput and power consumption.

### Example: Switch AP Throughput

```json
{
    "Throughput": {
        "Wired MAC Address Converted": "[REDACTED]",
        "In Octets": 250468387,
        "Out Octets": 4747957531,
        "PoE Type": "HPE",
        "Bridge Index": 8,
        "Port Index": 8,
        "AP Name": "FT-5-2-R.Kelas 5",
        "Wired MAC Address": "[REDACTED]",
        "in throughput": 2246.709256847063,
        "out_throughput": 39370.46397492263,
        "total throughput": 41617.173230969696,
        "PoE Port": "[REDACTED]"
    }
}
```

### Example: Switch AP Power

```json
"Power": [
    {
        "Wired MAC Address Converted": "[REDACTED]",
        "peak": 12.9,
        "average": 10.32,
        "current": 10.2,
        "PoE Type": "HPE",
        "Bridge Index": 8,
        "Port Index": 8,
        "AP Name": "FT-5-2-R.Kelas 5",
        "Wired MAC Address": "[REDACTED]",
        "PoE Port": "[REDACTED]"
    },
    {
        "Wired MAC Address Converted": "[REDACTED]",
        "peak": 13.2,
        "average": 10.37,
        "current": 10.3,
        "PoE Type": "HPE",
        "Bridge Index": 9,
        "Port Index": 9,
        "AP Name": "FT-S-1-R.Kelas 70",
        "Wired MAC Address": "[REDACTED]",
        "PoE Port": "[REDACTED]"
    }
]
```

-----

## ⏱️ Crawler Runtime

Performance metrics for the crawling process for approximately 1500 APs.

  * **AP+STA**: 27 seconds
  * **RSSI**: 6:41 minutes
  * **Utilization**: 0.05 seconds
  * **PoE (1 switches)**: 15 seconds
  * **PoE (3 switches)**: 50 seconds

The UI controller is equipped with 130GB of RAM and 20 CPUs.


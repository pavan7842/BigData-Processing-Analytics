# Spatiotemporal Big Data Processing

This repository contains implementations of **Hotzone Analysis** and **Hotcell Analysis** using Apache Spark and Scala. These projects analyze large-scale spatial-temporal datasets to identify significant patterns in geographical data.

---

## **Project Overview**
- **Hotzone Analysis**: Identifies high-density geographical areas based on spatial queries.
- **Hotcell Analysis**: Determines statistically significant spatial hotspots using the Getis-Ord statistic.

Both analyses leverage **Apache Spark** for distributed computing and **Scala** for efficient data processing.

---

## **Project Structure**

Spatiotemporal-BigData-Processing/ 
│── README.md 
│── src/ 
│ │── HotzoneAnalysis.scala 
│ │── HotzoneUtils.scala 
│ │── HotcellAnalysis.scala 
│ │── HotcellUtils.scala 
│── data/ # Input datasets (e.g., NYC taxi data) 
│── report/ # Project reports and documentation 
│── jar/ # Compiled JAR file for execution


---

## **How to Run the Project**
### **1. Running Directly from Scala**
If you are running the project in **Scala Spark**, compile and run the scripts directly:

#### **Run Hotzone Analysis**
```sh
spark-shell --master local[*] -i src/HotzoneAnalysis.scala

#### **Run Hotcell Analysis**

spark-shell --master local[*] -i src/HotcellAnalysis.scala


**2. Running Using the Precompiled JAR**

You can also execute the project using the provided JAR file.

**2.1. Running Hotzone Analysis**

spark-submit --class HotzoneAnalysis --master local[*] jar/Spatiotemporal-BigData-Processing.jar data/NYC_Taxi.csv output/hotzone_result

**2.2. Running Hotcell Analysis**

spark-submit --class HotcellAnalysis --master local[*] jar/Spatiotemporal-BigData-Processing.jar data/NYC_Taxi.csv output/hotcell_result

**Environment & Dependencies**

Apache Spark (≥ 3.0.0)

Scala (≥ 2.12)

Java 8+

Dataset: NYC Taxi Trip Records or any geospatial dataset

**To install dependencies:**

sudo apt update && sudo apt install openjdk-8-jdk scala

**Dataset**

The input dataset should be a structured CSV file with latitude, longitude, timestamp values. Example dataset: NYC Taxi Trip Records.

**References**

Apache Spark Documentation
Getis-Ord Hotspot Analysis
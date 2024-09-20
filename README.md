# Uber-Data-Analytics-GCP-Data-Engineering-Project


## Introduction
This project is an end-to-end Data Engineering solution that focuses on analyzing the Uber dataset. The project leverages various cloud technologies, including **Google Cloud Platform (GCP)**, to perform data ingestion, transformation, and visualization. Key tools include **GCP Storage**, **Python**, **Compute Instances**, **Mage Data Pipeline Tool**, **BigQuery**, and **Looker Studio**. The goal is to perform analytics operations such as data cleaning, transformation, and distance calculation, culminating in meaningful insights through data visualization.

## Architecture
![Architecture](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/6045301dfa74120f381e72880cc6439157ac97f0/Assets/Architecture%20diagram.png)
*The architecture outlines the data flow from storage to analytics using GCP tools.*

## Technology Used
- **Google Cloud Platform (GCP):** For cloud storage, compute, and database management.
- **Python:** For data cleaning, transformation, and calculation of distance.
- **GCP Compute Instances:** To run the data pipeline.
- **[Mage](https://www.mage.ai/) Data Pipeline Tool:** For orchestrating the data pipeline.
- **BigQuery:** For structured querying and large-scale analytics.
- **Looker Studio:** For data visualization and reporting.

## Dataset Used
- **Uber Trips Dataset**: Contains trip records, including pickup and dropoff locations, fare amounts, passenger counts, and timestamps.
![UberData](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/6045301dfa74120f381e72880cc6439157ac97f0/Uber%20Data%20Model.png)
## Data Model
The project uses a star schema that includes the following tables:
- **Dim_time:** Captures details about the trip time, such as date, hour, and day of the week.
- **Dim_Location (Pickup & Dropoff):** Contains geographical coordinates for trip pickup and dropoff points.
- **Dim_Distance:** Stores calculated distances between pickup and dropoff locations.
- **Dim_RateRide:** Categorical data on fare rates based on distance.
- **Fact_Fare:** Fact table containing fare amounts, passenger counts, and foreign keys linking to other dimension tables.

## Getting Started

To replicate this project, follow these steps:

### 1. **Setup Google Cloud Platform (GCP)**

- **Create Service Accounts:** 
  - Navigate to the GCP Console and create a service account with the necessary permissions to access Google Cloud Storage and BigQuery.
  - ![Instance](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/a1b01e72ef805d3ceea9b88f2dab9c4bf2902030/Assets/Instance.png)

### 2. **Prepare the Environment**

- **Install Google Cloud SDK:** 
  - Download and install the Google Cloud SDK from [here](https://cloud.google.com/sdk/docs/install).
  
- **Authenticate Google Cloud SDK:** 
  - Authenticate using the service account key:
       ```bash
       gcloud auth activate-service-account --key-file=path-to-your-service-account-key.json
       ```
  
- **Install Python and Required Libraries:** 
  - Ensure you have Python installed and run the following command to install required libraries:
    ```bash
    pip install pandas haversine google-cloud-storage
    ```


### 3. **Upload Data to Google Cloud Storage**

- **Create a Storage Bucket:** 
  - In the GCP Console, create a new Cloud Storage bucket to store your Uber dataset.
  
- **Upload Dataset:** 
  - Upload the `uber.csv` file into the created storage bucket.

### 4. **Setup Mage Data Pipeline**

- **Create a Mage.ai Account:** 
  - Sign up for a free account at [Mage.ai](https://www.mage.ai/).
  
- **Configure Data Pipeline:** 
  - Set up a data pipeline in Mage.ai to automate data ingestion and transformation steps, and configure the data to be loaded into BigQuery.
  - ![DataPipeLine](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/a1b01e72ef805d3ceea9b88f2dab9c4bf2902030/Assets/Mage%20Pipeline.png)
  - ![MageDataTransform](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/a1b01e72ef805d3ceea9b88f2dab9c4bf2902030/Assets/Mage%20Transform.png)

### 5. **Data Analysis in BigQuery**

- **Create a BigQuery Dataset:** 
  - In GCP Console, create a new dataset in BigQuery to store the cleaned and processed data.
  
- **Load Data into BigQuery:** 
  - Use Mage Data Pipeline to load the transformed data into BigQuery.
  
- **Run SQL Queries:** 
  - Perform analysis by writing SQL queries in the BigQuery console.
   - Example SQL query:
   - ![SQL Query](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/a1b01e72ef805d3ceea9b88f2dab9c4bf2902030/Assets/BQ%20Quieres)
     

### 6. **Data Visualization with Looker Studio**

- **Create a Looker Studio Account:** 
  - Sign up for a free account at [Looker Studio](https://lookerstudio.google.com/).
  
- **Connect to BigQuery:** 
  - Connect your Looker Studio to the BigQuery dataset where your transformed data is stored.
  
- **Design Dashboards:** 
  - Design and customize dashboards to visualize key metrics such as ride distances, fare amounts, and passenger counts.
    ![Looker Dashbord](https://github.com/Keroles-Ramses/Uber-Data-Analytics-GCP-Data-Engineering-Project-/blob/a1b01e72ef805d3ceea9b88f2dab9c4bf2902030/Assets/Looker%20Visual.png)
     [Looker Studio Dashbord](Uber_Dashboard.pdf) 

## Conclusion
This project demonstrates the power of integrating multiple tools and platforms, from data ingestion in Google Cloud to insights visualization with Looker Studio. By orchestrating the data flow, we can derive meaningful insights about Uber trips and ride patterns.

## Connect with Me
If you have any questions, feel free to contact me:

- **Email**: keroles.ramses612@gmail.com
- **LinkedIn**: [Keroles Ramses](https://www.linkedin.com/in/keroles-ramses/)

---

Thank you for checking out this project! I hope you find it useful.

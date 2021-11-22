# CP4D-notebook-datastage
<p align="justify">This project demonstrates the integration between notebook and DataStage in IBM CP4D Environment. IBM CP4D environment is IBM Cloud Pak for Data, which is an open, extensible data platform that provides a data fabric to make all data available for AI and analytics, on any cloud.</p>

## Description
<p align="justify">Validations that are performed on files are done by a notebook in Analytics Project and transformations are performed on files through DataStage Jobs in Data Transformation Project. The functionality of the implemented functions can be viewed via notebook. Basic functionalities are listed below:</p>

1. Connect to IBM COS (s3) and DB2
2. Take the data from the IBM COS landing bucket
3. Perform checks and validations
4. Insert the status into DB2
5. Saved the data in IBM COS processed bucket
6. Call DataStage REST APIs for data transformation

## Advantages
1. Customization of functionalities can be achieved via using Notebooks.
2. Transformation on millions of rows processing done through DataStage Tool integrated into IBM CP4D Environment.
3. No need to lift and shift data in different environments based on their usage.

## Environment Details
This implementation is done on IBM CP4D which runs on top of the Openshift cluster on IBM Cloud. IBM CP4D allows three kinds of projects:
1. Analytics Project: Notebooks, AUTO AI, Data connections, dashboards, Federated Learning Environment
2. Data Transformation Project: DataStage ETL
3. Data Quality Project: Data Cleansing and Data Matching, Business Terms, Rules

`conf` directory consists of `sample_configuration_file.txt` the configuration file which holds the user-provided input parameter. <p align="justify">It holds the client name, file name, target table name, DataStage job name, data transformation project name, username, and password of the user on this IBM CP4D cluster hosted on OpenShift. User will store all their files along with this configuration file separated by the "|" (pipe) symbol in the IBM COS bucket. The notebook will read the parameters from this configuration file and trigger the functionality.
Packages required to build this project were pre-installed in Analytics Notebook.
</p>

## Working Details
<p align="justify">Analytics Notebook works like a Jupyter Notebook. When the user receives the request from client then they have to keep the parameters in configuration file and execute the code stored in Notebook. Notebook code will run as per the functionalities written in the Description section.</p>

Analytics Project holds the data connectors for IBM COS and DB2.

## Highlights
1. IBM COS and DB2 connectors.
2. Loading and storing data in s3 buckets.
3. Integration between Analytics and Data Transformation Project using APIs.

## Demo Screenshots
The output of the functionality can be seen through Analytics notebook as shown below:
![IBM JUPYTER NOTEBOOK SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/Jupyter%20Notebook%20Screenshot.JPG)

IBM COS Bucket Structure:
![IBM COS SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/IBM%20COS%20Screenshot.JPG)

Count Metrics in AUDIT_TABLE for file:
![AUDIT TABLE SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/AUDIT%20TABLE.JPG)

File Status in AUDIT_TABLE_STATUS:
![AUDIT TABLE STATUS SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/AUDIT%20STATUS%20TABLE.JPG)

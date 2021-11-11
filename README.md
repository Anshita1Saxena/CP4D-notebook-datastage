# CP4D-notebook-datastage
This projects demonstrates the integration between notebook and DataStage in IBM CP4D Environment. IBM CP4D environment is IBM Cloud Pak for Data, which is an open, extensible data platform that provides a data fabric to make all data available for AI and analytics, on any cloud.

## Description
Validations that are performed on files is done by notebook in Analytics Project and transformations that are performed on files through DataStage Jobs in Data Transformation Project. Functionality of the implemented functions can be viewed via notebook. Basic functionalities are listed below:
1. Connect to IBM COS (s3) and DB2
2. Take the data from IBM COS landing bucket
3. Perform checks and validations
4. Insert the status into DB2
5. Saved the data in IBM COS processed bucket
6. Call DataStage REST APIs for data transformation

## Advantages
1. Customization of functionalities can be achieved via using Notebooks.
2. Transformation on million of rows processing done through DataStage Tool integrated in IBM CP4D Environment.
3. No need to lift and shift of data in different environments based on their usage.

## Environment Details
This implementation is done on IBM CP4D which runs on top of Openshift cluster on IBM Cloud. IBM CP4D allows three kind of projects:
1. Analytics Project: Notebooks, AUTO AI, Data connections, dashboards, Federated Learning Environment
2. Data Transformation Project: DataStage ETL
3. Data Quality Project: Data Cleansing and Data Matching, Business Terms, Rules

`conf` directory consists of `sample_configuration_file.txt` configuration file which holds the user provided input parameter. It holds client name, file name, target table name, DataStage job name, data transformation project name, username and password of the user on this IBM CP4D cluster hosted on OpenShift. User will store all their files along with this configuration file separated by "|" (pipe) symbol in IBM COS bucket. Notebook will read the parameters from this configuration file and trigger the functionality.
Packages required to build this project were pre-installed in Analytics Notebook.

## Working Details
Analytics Notebook works like a Jupyter Notebook. When the user receives the request from client then they have to keep the parameters in configuration file and execute the code stored in Notebook. Notebook code will run as per the functionalities written in Description section.
Analytics Project hold the data connectors for IBM COS and DB2.

## Highlights
1. IBM COS and DB2 connectors.
2. Loading and storing data in s3 buckets.
3. Integration between Analytics and Data Transformation Project using APIs.

## Demo Screenshot Details
The output of the functionality can be seen through Analytics notebook.
![IBM JUPYTER NOTEBOOK SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/Jupyter%20Notebook%20Screenshot.JPG)

IBM COS Bucket Structure:
![IBM COS SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/IBM%20COS%20Screenshot.JPG)

Count Metrics in AUDIT_TABLE for file:
![AUDIT TABLE SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/AUDIT%20TABLE.JPG)

File Status in AUDIT_TABLE_STATUS:
![AUDIT TABLE STATUS SCREENSHOT](https://github.com/Anshita1Saxena/CP4D-notebook-datastage/blob/main/demo-image/AUDIT%20STATUS%20TABLE.JPG)

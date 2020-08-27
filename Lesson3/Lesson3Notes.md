# Introduction to Machine Learning on Azure

## Lesson 3

### 3.1 Lesson Overview

* Before training a model, we first need to handle **data preparation**, so we'll explore this topic first.
	* Data importing and transformation
	* The data management process, including:
	* The use of datastores and datasets
	* Versioning
	* Feature engineering
	* How to monitor for data drift
* Next, we will introduce the basics of **model training**.
	* The core model training process
	* Two of the fundamental machine learning models: Classifier and regressor
	* The model evaluation process and relevant metrics
* Finally, we'll conclude with an introduction to **ensemble learning** and **automated machine learning**, two core techniques used to make decisions based on multiple—rather than single—trained models.

### 3.2 Prelaunch Lab

**No notes here**

### 3.3 Lab Instructions

** No notes here**

### 3.4 Data Import and Transformation

* **Data wrangling** is the process of cleaning and transforming data to make it more appropriate for data analysis.
	* Explore the raw data and check the general quality of the dataset.
	* Transform the raw data, by restructuring, normalizing, and cleaning the data. 
		* Handling missing values.
		* Detecting errors.
	* Validate and publish the data.
* Data wrangling is an iterative process where you do some data transformation then check the results and come back to the process to make improvements.

#### Quizzes:

![Question 1](https://i.imgur.com/YAuDmb2.png)

### 3.3 Lab: Import, Transform, and Export Data

#### Getting Started 

1. If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![azure portal](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

2. If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following credentials:

Username:odl_user_91019@udacitylabs.onmicrosoft.com

Password:ujoz11UAZ*br

and Click on Sign in.

3. After sign-in please click on Next button in bottom right corner of lab guide.

#### Lab Overview

In this lab you learn how to import your own data in the designer to create custom solutions. There are two ways you can import data into the designer in Azure Machine Learning Studio:

* Azure Machine Learning datasets

* Register datasets in Azure Machine Learning to enable advanced features that help you manage your data.

* Import Data module

* Use the Import Data module to directly access data from online datasources.

The first approach will be covered later in the next lab, which focuses on registering and versioning a dataset in Azure Machine Learning studio.

While the use of datasets is recommended to import data, you can also use the Import Data module from the designer. Data comes into the designer from either a Datastore or from Tabular Datasets. Datastores will be covered later in this course, but just for a quick definition, you can use Datastores to access your storage without having to hard code connection information in your scripts. As for the second option, the Tabular datasets, the following datasources are supported in the designer: Delimited files, JSON files, Parquet files or SQL queries.

The following exercise focuses on the Import Data module to load data into a machine learning pipeline from several datasets that will be merged and restructured. We will be using some sample data from the UCI dataset repository to demonstrate how you can perform basic data import transformation steps with the modules available in Azure Machine Learning designer.

#### Exercise 1: Import, transform and export data using the Visual Pipeline Authoring Editor

**Task 1: Open Pipeline Authoring Editor**

1. In Azure portal, open the available machine learning workspace.
2. Select Launch now under the Try the new Azure Machine Learning studio message.

![Azure ML Studio](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/01a.png)

3. When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![Setup studio](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started.*

4. From the studio, select Designer, +. This will open a visual pipeline authoring editor.

![Select designer](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/01.png)

**Task 2: Setup Compute Target**

1. In the settings panel on the right, select Select compute target.

![select compute target](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/02.png)

2. In the Set up compute target editor, select the existing compute target, and then select Save.

*Note: If you are facing difficulties in accessing pop-up windows or buttons in the user interface, please refer to the Help section in the lab environment.*

![select existing compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/03.png)

**Task 3: Import data from Web URL**

1. Select Data Input and Output section in the left navigation. Next, select Import Data and drag and drop the selected module on to the canvas.

![Import data module](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/04.png)

2. In the `Import data` panel on the right, select the URL via HTTP option in the `Data Source` drop-down and provide the following `Data source URL` for the first CSV file you will import in your pipeline: `https://introtomlsampledata.blob.core.windows.net/data/crime-data/crime-dirty.csv`

![URL via HTTP](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/05.png)

3. Select the Preview schema to filter the columns you want to include. You can also define advanced settings like Delimiter in Parsing options. Select Save to close the dialog.

![preview schema](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/06.png)

**Task 4: Create Experiment and Submit Pipeline**

1. Back to the pipeline canvas, select Submit on the top right corner to open the Setup pipeline run editor.
2. In the Setup pipeline run editor, select Experiment, Create new and provide New experiment name: designer-data-import, and then select Submit.

![submit pipeline[(https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/08.png)

*Please note that the button name in the UI is changed from Run to Submit.*

3. Wait for pipeline run to complete. It will take around 10 minutes to complete the run.

**Task 5: Visualize Import Data results**

1.Select the Import Data module on the canvas and then select Outputs on the right pane. Click on the Visualize icon to open the Import Data result visualization dialog.

![visualize](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/09.png)

2. In the `Import Data result visualization` dialog take some moments to explore all the metadata that is now available to you, such as: number of rows, columns, preview of data and for each column you select you can observe: Mean, Median, Min, Max and also number of Unique Values and Missing Values. Data profiles help you glimpse into the column types and summary statistics of a dataset. Scroll right and select the X Coordinate column. Notice the `Nan` value on the third row in the preview table and check the `Missing values` number in the Statistics section.

![check metrics](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/10.png)

3. Select Close to return to the pipeline designer canvas where you can continue the data import phase.

#### Exercise 2: Restructure the data split across multiple files

**Task 1: Append rows from two additional data sources**

1. Select Data Input and Output section in the left navigation. Next, drag and drop two Import Data modules on to the canvas as demonstrated in the first exercise and fill in the Web URLs as follows:

	* for the first one, Data source URL : 		`https://introtomlsampledata.blob.core.windows.net/data/crime-data/crime-spring.csv`
	* for the second one, Data source URL :
`https://introtomlsampledata.blob.core.windows.net/data/crime-data/crime-winter.csv`

![data source URL](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/11.png)

2. For each of the three Import Data modules, select Preview schema and ensure that the data type for FBI Code and Location is of type String and then select Save.

![schema preview](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/11_1.png)

3. Select the Data Transformation section in the left navigation. Drag and drop the Add rows module and connect it to the above added Import data modules.

![import data module](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/12.png)

4. Repeat the same step and add a second Add rows module that connects the output from the first Import data module to the output of the first Add rows module.

![add rows](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/13.png)

**Task 2: Clean missing values**

1. Drag the Clean Missing Data module from the Data Transformation section in the left navigation.

![Clean missing data](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/14.png)

2. Select Edit column in the right pane to configure the list of columns to be cleaned. Select Column names from the available include options and type the name of the columns you intend to clean at this step: X Coordinate and Y Coordinate. Select Save to close the dialog.

![select column to clean](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/15.png)

3. Set the Minimum missing value ratio to 0.1 and the Maximum missing value ratio to 0.5. Select Replace with mean in the Cleaning mode field.

![parameters](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/16.png)

**Task 3: Submit Pipeline**

1. Select Submit to open the `Setup pipeline run` editor.
2. In the `Setup pipeline run` editor, select Select existing, designer-data-import for `Experiment`, and then select Submit.

![submit pipeline](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/17.png)

*Please note that the button name in the UI is changed from Run to Submit.*

3. Wait for pipeline run to complete. It will take around 8 minutes to complete the run.

**Task 4: Save the clean dataset**

1. Select the Clean missing data module you created on the canvas and then select Outputs + logs on the right pane. Click on the Save icon under the Cleaned dataset section to open the Save as dataset dialog.

![save dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/18.png)

2. Check the option to create a new dataset and enter crime-all in the dataset name field. Select Save to close the dialog.

![name of cleaned dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/19.png)

3. From the left navigation, select Datasets. This will open the Registered datasets page. See your registered dataset among the other datasets you used during this lesson.

![check saved dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-02/images/21.png)

#### Next Steps

Congratulations! You completed a few basic steps involved in the data explore and transform process, using the prebuilt modules you can find in the visual editor provided by Azure Machine Learning Studio. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 3.6 Walkthrough

[Video](https://www.youtube.com/watch?v=LllJB5LQtb0&feature=emb_logo)

### 3.7 Managing Data

* As we just discussed, Azure Machine Learning has two data management tools that we need to consider: Datastores and datasets. 
* **Datastores**:
	* Datastores offer a layer of abstraction over the supported Azure storage services. 
	* They store all the information needed to connect to a particular storage service. 
	* Datastores provide an access mechanism that is independent of the computer resource that is used to drive a machine learning process.
* **Datasets**:
	* Datasets are resources for exploring, transforming, and managing data in Azure ML. 
	* A dataset is essentially a reference that points to the data in storage.
	*  It is used to get specific data files in the datastores.
* **The steps of the data access workflow are**:
	* **Create a datastore** so that you can access storage services in Azure.
	* **Create a dataset**, which you will subsequently use for model training in your machine learning experiment.
	* **Create a dataset** monitor to detect issues in the data, such as data drift.
* Over time, the input data that you are feeding into your model is likely to change—and this is what we mean by *data drift*.
* Data drift can be problematic for model accuracy. Since you trained the model on a certain set of data, it can become increasingly inaccurate and the data changes more and more over time. 
	* If you train a model to detect spam in email, it may become less accurate as new types of spam arise that are different from the spam on which the model was trained.
* When data drift is detected, you can have the system automatically update the input dataset so that you can retrain the model and maintain its accuracy.

#### Data Management in Azure Machine Learning

![Data Management in Azure Machine Learning](https://i.imgur.com/IJ90UKV.png)

#### Azure Machine Learning

![Azure Machine Learning](https://i.imgur.com/t23k6yL.png)

#### Datastores supported in AML service

![Datastores supported in AML service](https://i.imgur.com/Mho4bai.png)

#### Quizzes

![Question 1](https://i.imgur.com/ei72dI4.png)
![Question 2](https://i.imgur.com/MyfqqOY.png)

### 3.9 More About Datasets

* **Key points to remember about datasets**:
	* They are used to interact with your data in the datastore and to package data into consumable objects.
	* They can be created from local files, public URLs, Azure Open Datasets, and files uploaded to the datastores.
	* They are not copies of the data but references that point to the original data. This means that no extra storage cost is incurred when you create a new dataset.
	* Once a dataset is registered in Azure ML workspace, you can share it and reuse it across various other experiments without data ingestion complexities.
* **In summary, here are some of the main things that datasets allow you to do**:
	* Have a single copy of some data in your storage, but reference it multiple times—so that you don't need to create multiple copies each time you need that data available.
	* Access data during model training without specifying connection strings or data paths.
	* More easily share data and collaborate with other users.
	* Bookmark the state of your data by using dataset versioning.
* **You would do versioning most typically when**:
	* New data is available for retraining.
	* When you are applying different approaches to data preparation or feature engineering.
* **Keep in mind that there are two dataset types supported in Azure ML Workspace**:
	* The Tabular Dataset, which represents data in a tabular format created by parsing the provided file or list of files.
	* The Web URL (File Dataset), which references single or multiple files in datastores or from public URLs.

#### Quizzes:

![Question 1](https://i.imgur.com/KLqw5mF.png)

### 3.10 Lab: Create and Version a Dataset

#### Getting Started

1. If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![quick start](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

2. If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following credentials:

Username:odl_user_91167@udacitylabs.onmicrosoft.com

Password:rdkb51QMB*Tb

and Click on Sign in.

3. After sign-in please click on Next button in bottom right corner of lab guide.

#### Create and version a dataset

**Lab Overview**

To access your data in your storage account, Azure Machine Learning offers datastores and datasets. Create an Azure Machine Learning datasets to interact with data in your datastores and package your data into a consumable object for machine learning tasks. Register the dataset to your workspace to share and reuse it across different experiments without data ingestion complexities.

Datasets can be created from local files, public urls, Azure Open Datasets, or specific file(s) in your datastores. To create a dataset from an in memory pandas dataframe, write the data to a local file, like a csv, and create your dataset from that file. Datasets aren’t copies of your data, but are references that point to the data in your storage service, so no extra storage cost is incurred.

In this lab, we are using a subset of NYC Taxi & Limousine Commission - green taxi trip records available from Azure Open Datasets to show how you can register and version a Dataset using the AML designer interface. In the first exercises we use a modified version of the original CSV file, which includes collected records for five months (January till May). The second exercise demonstrates how we can create a new version of the initial dataset when new data is collected (in this case, we included records collected in June in the CSV file).

#### Exercise 1: Register Dataset with Azure Machine Learning studio

**Task 1: Upload Dataset from web file**

1. In Azure portal, open the available machine learning workspace.
2. Select Launch now under the Try the new Azure Machine Learning studio message.

![launch now](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/01a.png)

3. When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![Copy image address](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started.*

4. From the studio, select Datasets, + Create dataset, From web files. This will open the Create dataset from web files dialog on the right.

![web file](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/02.png)

5. Provide the following information and then select Next:

	1. Web URL: `https://introtomlsampledata.blob.core.windows.net/data/nyc-taxi/nyc-taxi-sample-data-5months.csv`

	2. Name: `nyc-taxi-sample-dataset`

![name](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/03.png)

**Task 2: Preview Dataset**

1. On the Settings and preview panel, set the Column headers drop down to `All files have same headers`.
2. Scroll the data preview to right to observe the target column: `totalAmount`. After you are done reviewing the data, select Next.

![Create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/05.png)

**Task 3: Select Columns**

1. Select columns from the dataset to include as part of your training data. Leave the default selections and select Next.

![Select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/06.png)

**Task 4: Create Dataset**

1. Confirm the dataset details and select Create.

![Confirm](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/07.png)

#### Exercise 2: Create a version of the existing Dataset

**Task 1: Register new dataset version**

1. From the Azure Machine Learning studio, select Datasets and select the `nyc-taxi-sample-dataset` dataset created in the first exercise. This will open the Dataset details page.

2. Select New version, From web files to open the same `Create dataset from web files` dialog you already entered in the first exercise.

![new version creation](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/08.png)

3. This time, the Name and Dataset version fields are already filled in for you. Provide the following information and select Next to move on to the next step:

	1. Web URL: `https://introtomlsampledata.blob.core.windows.net/data/nyc-taxi/nyc-taxi-sample-data-6months.csv`

![new data URL](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/09.png)

4. Select All files have the same headers in the Column headers drop-down and move on to the schema selection step.

5. On the Schema page, let’s suppose you decided to exclude some columns from your dataset. Exclude columns: snowDepth, prcipTime, precipDepth. Select Next to move on to the final step.

![Confirm dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/091.png)

6. Notice the Dataset version value in the basic info section. Select Create to close the new version confirmation page.

![dataset version](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/10.png)

**Task 2: Review both versions of the dataset**

1. Back to the Datasets page, in the Registered datasets list, notice the version value for the `nyc-taxi-sample-dataset dataset`.

![Version value](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/11.png)

2. Select the `nyc-taxi-sample-dataset` dataset link to open the dataset details page, where Version 2(latest) is automatically selected. Go to the Explore section to observe the structure and content of the new version. Notice the columns and rows structure in the dataset preview pane:

	* Number of columns: 11

	* Number of rows: 10000

	* Scroll right to check that the three excluded columns are missing. (snowDepth, prcipTime, precipDepth)

![Check updated dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/12.png)

3. Select Version 1 from the drop-down near the dataset name title and notice the changing values for:

	* Number of columns: 14 (since the previous version still contains the three excluded columns)

	* Number of rows: 9776 (since the previous version contains only data for 5 months)

![check version 1](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-03/images/13.png)

#### Next Steps

Congratulations! You have now explored a first simple scenario for dataset versioning using the Azure Machine Learning studio. You found out how you can create and version a simple dataset when new training data is available. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 3.11 Walkthrough

[Video](https://www.youtube.com/watch?v=aIvMainDa1E&feature=emb_logo)

### 3.12 Introducing Features

* Recall that the columns in a table can be referred to as features. In the above example, `color` and `quantity` are features of the products. 
* In the last lesson, we mentioned briefly that **feature engineering** is an important part of data preparation. In this lesson, we'll look at this topic in more detail.
* You can use feature engineering to derive new features based on the values of existing features. 
* This process can be as simple as applying a mathematical function to a feature (such as adding 1 to all values in an existing feature ) or it can be as complex as training a separate machine learning model to create values for new features.
* Once you have the features, another important task is selecting the features that are most important or most relevant. This process is called **feature selection**.
* Many machine learning algorithms cannot accommodate a large number of features, so it is often necessary to do **dimensionality reduction** to decrease the number of features.

#### Quizzes:

![Question 1](https://i.imgur.com/UzFLbdM.png)

### 3.13 Feature Engineering

#### Feature Engineering (with Classical ML and Deep Learning)

![Feature Engineering (with Classical ML and Deep Learning)](https://i.imgur.com/KkMkJpq.png)

#### Feature Engineering Tasks

![Feature Engineering Tasks](https://i.imgur.com/a1dsea6.png)

#### Summary of feature engineering approaches by data type

![Summary of feature engineering approaches by data type](https://i.imgur.com/Av1HVBo.png)

#### Quizzes:

![Question 1](https://i.imgur.com/jhCVOYA.png)
![Question 2](https://i.imgur.com/tpsiw6X.png)
![Question 3](https://i.imgur.com/Hjmk5ts.png)

### 3.14 Prelaunch Lab

**No notes here**

### 3.15 Feature Selection

* There are mainly two reasons for feature selection. Some features might be highly irrelevant or redundant. 
* So it's better to remove these features to simplify the situation and improve performance. 
* Additionally, it may seem like engineering more features is always a good thing, but as we mentioned earlier, many machine learning algorithms suffer from the curse of dimensionality—that is, they do not perform well when given a large number of variables or features.
We can improve the situation of having too many features through **dimensionality reduction**.
* Commonly used techniques are:
	* PCA (Principal Component Analysis)
	* t-SNE (t-Distributed Stochastic Neighboring Entities)
	* Feature embedding
* **Azure ML prebuilt modules**:
	* Filter-based feature selection: identify columns in the input dataset that have the greatest predictive power.
	* Permutation feature importance: determine the best features to use by computing the feature importance scores.

#### Quizzes:

![Question 1](https://i.imgur.com/Y7H6CH1.png)

### 3.16 Lab: Engineer and Select Features

#### Getting Started

1. If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![Getting started](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

2. If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following credentials:

Username: odl_user_92456@udacity
Password: ztji63UCC*od
and Click on Sign in.

3. After sign-in please click on Next button in bottom right corner of lab guide.

#### Engineer and select features

**Engineer and select features**

This lab demonstrates the feature engineering process for building a regression model using bike rental demand prediction as an example. In machine learning predictions, effective feature engineering will lead to a more accurate model. We will use the Bike Rental UCI dataset as the input raw data for this experiment. This dataset is based on real data from the Capital Bikeshare company, which operates a bike rental network in Washington DC in the United States. The dataset contains 17,379 rows and 17 columns, each row representing the number of bike rentals within a specific hour of a day in the years 2011 or 2012. Weather conditions (such as temperature, humidity, and wind speed) were included in this raw feature set, and the dates were categorized as holiday vs. weekday etc.

The field to predict is `cnt` which contains a count value ranging from 1 to 977, representing the number of bike rentals within a specific hour. Our main goal is to construct effective features in the training data, so we build two models using the same algorithm, but with two different datasets. Using the Split Data module in the visual designer, we split the input data in such a way that the training data contains records for the year 2011, and the testing data, records for 2012. Both datasets have the same raw data at the origin, but we added different additional features to each training set:

*  Set A = weather + holiday + weekday + weekend features for the predicted day
*  Set B = number of bikes that were rented in each of the previous 12 hours
    
We are building two training datasets by combining the feature set as follows:

* Training set 1: feature set A only
* Training set 2: feature sets A+B

For the model, we are using regression because the number of rentals (the label column) contains continuous real numbers. As the algorithm for the experiment, we will be using the Boosted Decision Tree Regression.

#### Exercise 1: Data pre-processing using the Pipeline Authoring Editor

**Task 1: Upload Dataset**

1. In Azure portal, open the available machine learning workspace.

2. Select Launch now under the Try the new Azure Machine Learning studio message.

![Upload dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/01a.png)

3. When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![Select compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started.*

4. From the studio, select Datasets, + Create dataset, From web files. This will open the Create dataset from web files dialog on the right.

![Create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/02.png)

5. In the Web URL field provide the following URL for the training data file: `https://introtomlsampledata.blob.core.windows.net/data/bike-rental/bike-rental-hour.csv`

6. Provide `Bike Rental Hourly` as the Name, leave the remaining values at their defaults and select Next.

![Name](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/03.png)

7. Select the option to `Use headers from the first file` in the Settings and preview dialog and then select Next, Next and Create to confirm all details in registering the dataset.

![use header](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/04.png)

**Task 2: Open Pipeline Authoring Editor**

1. From the left navigation, select Designer, +. This will open a visual pipeline authoring editor.

![Select designer](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/05.png)

**Task 3: Setup Compute Target**

1. In the settings panel on the right, select Select compute target.

![select compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/06.png)

2. In the Set up compute target editor, select the existing compute target, choose a name for the pipeline draft: Bike Rental Feature Engineering and then select Save.

*Note: If you are facing difficulties in accessing pop-up windows or buttons in the user interface, please refer to the Help section in the lab environment.*

**Task 4: Select columns in the dataset**

1. Drag and drop on the canvas, the available Bike Rental Hourly dataset under the Datasets category on the left navigation.

![Drag and drop dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/07.png)

2. Under the Data transformation category drag and drop the Edit Metadata module, connect the module to the dataset, and select Edit column on the right pane.

![Edit metadata](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/08.png)

3. Add the `season` and `weathersit` column and select Save.

![edit column](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/09.png)

4. Configure the Edit metadata module by selecting the `Categorical` attribute for the two columns.

![categorical attribute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/10.png)

*Note that you can submit the pipeline at any point to peek at the outputs and activities. Running pipeline also generates metadata that is available for downstream activities such selecting column names from a list in selection dialogs. Please refer ahead to Exercise 1, Task 8, Step 3 on details of submitting the pipeline. It can take up to 5-10 minutes to run the pipeline.*

5. Under the Data transformation category drag and drop the Select Columns in Dataset module, connect the module to the Edit Metadata module, and select Edit column on the right pane.

![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/11_1.png)

6. Configure the Select Columns in Dataset module as follows:

   *  Include: All columns

   *  Select +

   * Exclude Column names: instant, dteday, casual,registered

    * Select Save
    


*Note: You can copy and paste all four column names separated by comma (`instant, dteday, casual,registered`) in the text box, then select anywhere on the dialog, and then select Save.*

7. Under the Python Language category on the left, select the Execute Python Script module and connect it with the Select Columns in Dataset module. Make sure the connector is connected to the very first input of the Execute Python Script module.

![execute script](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/12.png)

8. We are using the Python script to append a new set of features to the dataset: number of bikes that were rented in each of the previous 12 hours. Feature set B captures very recent demand for the bikes. This will be the B set in the described feature engineering approach.

Select Edit code and use the following lines of code:

```
# The script MUST contain a function named azureml_main
# which is the entry point for this module.

# imports up here can be used to
import pandas as pd

# The entry point function MUST have two input arguments.
# If the input port is not connected, the corresponding
# dataframe argument will be None.
#   Param<dataframe1>: a pandas.DataFrame
#   Param<dataframe2>: a pandas.DataFrame
def azureml_main(dataframe1 = None, dataframe2 = None):

    # Execution logic goes here
    print(f'Input pandas.DataFrame #1: {dataframe1}')

    # If a zip file is connected to the third input port,
    # it is unzipped under "./Script Bundle". This directory is added
    # to sys.path. Therefore, if your zip file contains a Python file
    # mymodule.py you can import it using:
    # import mymodule
    for i in np.arange(1,13):
        prev_col_name = 'cnt' if i == 1 else 'Rentals in hour -{}'.format(i -1)
        new_col_name = 'Rentals in hour -{}'.format(i)
        dataframe1[new_col_name] = dataframe1[prev_col_name].shift(1).fillna(0)
    # Return value must be of a sequence of pandas.DataFrame
    # E.g.
    #   -  Single return value: return dataframe1,
    #   -  Two return values: return dataframe1, dataframe2
    return dataframe1,
# The script MUST contain a function named azureml_main
# which is the entry point for this module.

# imports up here can be used to
import pandas as pd
import numpy as np

# The entry point function can contain up to two input arguments:
#   Param<dataframe1>: a pandas.DataFrame
#   Param<dataframe2>: a pandas.DataFrame
def azureml_main(dataframe1 = None, dataframe2 = None):

    # Execution logic goes here
    print(f'Input pandas.DataFrame #1: {dataframe1}')

    # If a zip file is connected to the third input port,
    # it is unzipped under "./Script Bundle". This directory is added
    # to sys.path. Therefore, if your zip file contains a Python file
    # mymodule.py you can import it using:
    # import mymodule

    for i in np.arange(1, 13):
        prev_col_name = 'cnt' if i == 1 else 'Rentals in hour -{}'.format(i-1)
        new_col_name = 'Rentals in hour -{}'.format(i)

        dataframe1[new_col_name] = dataframe1[prev_col_name].shift(1).fillna(0)

    # Return value must be of a sequence of pandas.DataFrame
    # E.g.
    #   -  Single return value: return dataframe1,
    #   -  Two return values: return dataframe1, dataframe2
    return dataframe1,
```

Don’t worry if you do not fully understand the details of the Python code above. For now, it’s enough to keep in mind that is adds 12 new columns to your dataset containing the number of bikes that were rented in each of the previous 12 hours.

**Task 5: Split data into train and test datasets**

1. Use the Split Data module under the Data Transformation module and connect its input with output from the Select Columns in Dataset module. Use the following configuration:

   * Splitting mode: `Relative Expression`

   * Relational expression: `\"yr" == 0`

![Split data](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/E01.png)

2. Select the Split Data module block and use the menu buttons to Copy and Paste it on the canvas. Connect the second one to the output of the Python Script execution step, which is the featured B set.

![connect to Python script](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/E02.png)

**Task 6: Select columns from the test and training resulted sets**

1. Next, using the Select columns module under the Data transformation category, create four identical modules to exclude the `yr` column from all the outputs: test and training sets in both branches: A and A+B.

![branches A and A+B](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/E08.png)

2. Use the following structure for the columns field in each module:

![Select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/16.png)

**Task 7: Create the regression model**

  1.  Under the Machine Learning Algorithms, Regression category, select the Boosted Decision Tree Regression module. Drag and drop it on the canvas and use the default settings provided.

![choose algorithm](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/E05.png)

2. Next, use the Train model module under the Model training category and enter the cnt column in the Label column field.
3. Link the Boosted Decision Tree Regression module as the first input and the training dataset as the second input like in the image below.

![link algorithm](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/E06.png)

4. Use the exact same configuration on the right branch that uses the output from the Python Script.

![same config](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/E07.png)

**Task 8: Evaluate and score models**

1. Use two Score Model modules (under the Model Scoring and Evaluation category) and link on the input the two trained models and the test datasets.

2. Drag the Evaluate Model module which stands in the same category, Model Scoring and Evaluation and link it to the two Score Model modules.

![score and evaluate](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/20.png)

3. Select Submit to open the `Setup pipeline run editor`. In the `Setup pipeline run editor`, select Experiment, Create new and provide `New experiment name`: BikeRentalHourly.

![Setup run](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/21.png)

*Please note that the button name in the UI is changed from Run to Submit.*

4. Wait for pipeline run to complete. It will take around 10 minutes to complete the run.
5. Once the pipeline execution completes, right click on the Evaluate Model module and select Visualize Evaluation results.

![Visualize](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/22.png)

6. The Evaluate Model result visualization popup shows the results of the evaluation.

![results](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-04/images/23.png)

*Notice the values for the **Mean_Absolute_Error** metric. The first value (the bigger one) corresponds to the model trained on feature set A. 
The second value (the smaller one) corresponds to the model trained on feature sets A + B.*

*It is remarkable how, using simple feature engineering to derive new features from the existing data set, a new context was created that allowed the model to better understand the dynamics of the data and hence, produce a better prediction.*

#### Next Steps

Congratulations! You have trained and compared performance of two models using the same algorithm, but with two different datasets. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 3.17 Walkthrough

[Video 1](https://www.youtube.com/watch?time_continue=33&v=pIOkoTphyR8&feature=emb_logo)
[Video 2](https://www.youtube.com/watch?v=KpO1Wa_TvT4&feature=emb_logo)

### 3.18 Data Drift

* As we mentioned earlier, data drift is change in the input data for a model.
*  Over time, data drift causes degradation in the model's performance, as the input data drifts farther and farther from the data on which the model was trained. 
* Monitoring for Data Drift:
	* Specifying a baseline dataset – usually the training dataset.
	* Specifying a target dataset – usually the input data for the model.
	* Comparing these two datasets over time, to monitor for differences.
	* Comparing input data vs. training data:
		* This is a proxy for model accuracy; that is, an increased difference between the input vs. training data is likely to result in a decrease in model accuracy.
	* Comparing different samples of time series data:
		*  In this case, you are checking for a difference between one time period and another. 
		* For example, a model trained on data collected during one season may perform differently when given data from another time of year. 
		* Detecting this seasonal drift in the data will alert you to potential issues with your model's accuracy.

#### Quizzes:

![Question 1](https://i.imgur.com/nYod3c9.png)
![Question 2](https://i.imgur.com/DZpe7PT.png)

### 3.19 Model Training Basics

* Remember that our ultimate goal is to produce a model we can use to make predictions. Put another way, we want to be able to give the model a set of input features, `X`, and have it predict the value of some output feature, `y`.
* Parameters and Hyperparameters:
	* When we train a model, a large part of the process involves learning the values of the parameters of the model.
		* `y=B0​+B1​∗x1​+B2​∗x2​+B3​∗x3​...+Bn​∗xn`
		* The coefficients in this equation, `B0…Bn`​, determine the intercept and slope of the regression line. 
		* When training a linear regression model, we use the training data to figure out what the value of these parameters should be. 
		* Thus, we can say that a major goal of model training is to learn the values of the model parameters.
	* In contrast, some model parameters are not learned from the data. These are called hyperparameters and their values are set before training:
		* The number of layers in a deep neural network.
		* The number of clusters (such as in a k-means clustering algorithm).
		* The learning rate of the model.
	* We must choose some values for these hyperparameters, but we do not necessarily know what the best values will be prior to training. 
	* Because of this, a common approach is to take a best guess, train the model, and then tune adjust or tune the hyperparameters based on the model's performance.
	* Splitting the Data:
		* Training data:
			* We use the training data to learn the values for the parameters. 
		* Validation data:
			* Then, we check the model's performance on the validation data and tune the hyperparameters until the model performs well with the validation data.
		* Test data:
			* Finally, once we believe we have our finished model (with both parameters and hyperparameters optimized), we will want to do a final check of its performance—and we need to do this on some fresh test data that we did not use during the training process.

#### Quizzes

![Question 1](https://i.imgur.com/YfZ2sVa.png)

### 3.20 Model Training in Azure Machine Learning

#### Data Science Process

![Data Science Process](https://i.imgur.com/HvRSv4X.png)

#### Taxonomy of Azure Machine Learning Workspace

![Taxonomy of Azure Machine Learning Workspace](https://i.imgur.com/J0O2AfT.png) 

#### Quizzes

![Question 1](https://i.imgur.com/nclQdB6.png)

### 3.21 Training Classifiers

* As we described in the last lesson, two of the main types of supervised learning are classification and regression. In this section, we'll get some practice training both of these types of models. 
* But first, let's discuss the concepts in more detail—starting with classification.
* In a classification problem, the outputs are categorical or discrete.
	* For example, you might want to classify emails as spam or not spam; each of these is a discrete category.

#### Training Classifiers

![Training Classifiers](https://i.imgur.com/gPZRlRX.png)

#### Quizzes:

![Question 1](https://i.imgur.com/TfwTG47.png)

### 3.22  Training Regressors

* Now let us turn to regression. The main distinction that sets a regression problem apart from a classification problem is the form of the output
* In a regression problem, the output is numerical or continuous.
	* A classic example would be a problem in which you are given data concerning houses and then asked to predict the price; this is a regression problem because price is a continuous, numerical output.

#### Training Regressors

![Training Regressors](https://i.imgur.com/kWeOy2Z.png)

#### Quizzes

![Question 1](https://i.imgur.com/ndwGdIL.png)

### 3.23 Evaluating Model Performance

* It is not enough to simply train a model on some data and then assume that the model will subsequently perform well on future data. 
* Instead, as we've mentioned previously, we need to split off a portion of our labeled data and reserve it for evaluating our model's final performance. We refer to this as the test dataset.
* The test dataset is a portion of labeled data that is split off and reserved for model evaluation.
* If a model learns to perform well with the training data, but performs poorly with the test data, then there may be a problem that we will need to address before putting our model out into the real world. * In practice, we will also need to decide what metrics we will use to evaluate performance, and whether there are any particular thresholds that the model needs to meet on these metrics in order for us to decide that it is "good enough."
* When splitting the available data, it is important to preserve the statistical properties of that data. 
* This means that the data in the training, validation, and test datasets need to have similar statistical properties as the original data to prevent bias in the trained model.

Quizzes:

![Question 1](https://i.imgur.com/6QvIN6r.png)

### 3.24 Confusion Matrices

* Suppose that we have trained a simple binary classification model: Given an image, this model will indicate whether it is a picture of a cat or a picture of a dog. 
* How can we evaluate our model's performance? What is a good metric for doing so?
* Let us first consider what it means for the model to perform well. 
* If the model tells us an image has a dog in it and that image actually has a dog, we would say it performs well. And similarly, if it says that the image has a cat and it actually has a cat that would also be good.

#### Confusion Matrix

![Confusion Matrix](https://i.imgur.com/zb62OPH.png)

#### Detecting incorrect classifications

![Detecting incorrect classifications](https://i.imgur.com/YqBcIn4.png)

#### Modified Confusion Matrix

![Modified Confusion Matrix](https://i.imgur.com/d0FO3VT.png)

#### Quizzes:

![Question 1](https://i.imgur.com/sr2l4oa.png)
![Question 2](https://i.imgur.com/CSBFXUF.png)
![Question 3](https://i.imgur.com/Db1z1Rb.png)

### 3.25 Evaluation Metrics for Classification

#### Model Evaluation Metrics for Classification

![Model Evaluation Metrics for Classification](https://i.imgur.com/3W6IYLE.png)

#### Model Evaluation Charts for Classification (ROC)

![Model Evaluation Charts for Classification (ROC)](https://i.imgur.com/O27B5cV.png)

#### Model Evaluation Charts for Classification (Gains and Lifts chart)

![Model Evaluation Charts for Classification (Gains and Lifts chart)](https://i.imgur.com/PPmZVOc.png)

#### Quizzes:

![Question 1](https://i.imgur.com/T3izfY5.png)
![Question 2](https://i.imgur.com/OTH50PR.png)

### 3.26 Prelaunch Lab

**No notes here**

### 3.27 Evaluation Metrics for Regression

#### Model Evaluation Metrics for Regression

![Model Evaluation Metrics for Regression](https://i.imgur.com/QXc55wZ.png)

#### Model Evaluation Charts for Regression

![Model Evaluation Charts for Regression](https://i.imgur.com/pz7CtJY.png)

#### Model Evaluation Charts for Regression

![Model Evaluation Charts for Regression](https://i.imgur.com/vM9MYFv.png)

#### Quizzes:

![Question 1](https://i.imgur.com/JFEuZi6.png)

### 3.27 Lab: Train and Evaluate a Model

#### Getting Started

  1. If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![Quickstart](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

2. If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following credentials:

Username: odl_user_92582@udacitylabs.onmicrosoft.com
Password: njns74TJO*sS

and Click on Sign in.

3. After sign-in please click on Next button in bottom right corner of lab guide.

#### Lab Overview

Azure Machine Learning designer (preview) gives you a cloud-based interactive, visual workspace that you can use to easily and quickly prep data, train and deploy machine learning models. It supports Azure Machine Learning compute, GPU or CPU. Machine Learning designer also supports publishing models as web services on Azure Kubernetes Service that can easily be consumed by other applications.

In this lab, we will be using the `Flight Delays` data set that is enhanced with the weather data. Based on the enriched dataset, we will learn to use the Azure Machine Learning Graphical Interface to process data, build, train, score, and evaluate a classification model to predict if a particular flight will be delayed by 15 minutes or more. To train the model, we will use Azure Machine Learning Compute resource. We will do all of this from the Azure Machine Learning designer without writing a single line of code.

#### Exercise 1: Register Dataset with Azure Machine Learning studio

**Task 1: Upload Dataset**

1. In Azure portal, open the available machine learning workspace.
2. Select Launch now under the Try the new Azure Machine Learning studio message.

![launch](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/01a.png)

When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![select compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started.*

4. From the studio, select Datasets, + Create dataset, From web files. This will open the `Create dataset from web files` dialog on the right

![create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/04.png)

5. In the Web URL field provide the following URL for the training data file:
` https://introtomlsampledata.blob.core.windows.net/data/flightdelays/flightdelays.csv`

6. Provide `flightdelays` as the Name, leave the remaining values at their defaults and select Next.

**Task 2: Preview Dataset**

1. On the Settings and preview panel, set the column headers drop down to All files have same headers.

2. Review the dataset and then select Next.

![previe](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/06.png)

**Task 3: Select Columns**

1. Select columns from the dataset to include as part of your training data. Leave the default selections and select Next.

![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/07.png)

**Task 4: Create Dataset**

1. Confirm the dataset details and select Create

![create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/08.png)

#### Exercise 2: Create New Training Pipeline

**Task 1: Open Pipeline Authoring Editor**

1. From the studio, select Designer, +. This will open a visual pipeline authoring editor.

![designer](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/09.png)

**Task 2: Setup Compute Target**

1. In the settings panel on the right, select Select compute target.

 2. In the Set up compute target editor, select the available compute, and then select Save.

*Note: If you are facing difficulties in accessing pop-up windows or buttons in the user interface, please refer to the Help section in the lab environment.*

![existing compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/11.png)

**Task 3: Add Dataset**

1. Select Datasets section in the left navigation. Next, select My Datasets, flightdelays and drag and drop the selected dataset on to the canvas.

![drag dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/12.png)

**Task 4: Split Dataset**

1. We will split the dataset such that months prior to October will be used for model training and months October to December will be used for model testing.

 2.Select Data Transformation section in the Modules. Follow the steps outlined below:

	* Select the Split Data prebuilt module

	* Drag and drop the selected module on to the canvas

	* Splitting mode: Relative Expression

	* Relational expression: \”Month” < 10 (please make sure that the expression is provided exactly as seen in the image below, starting with backslash.)

	* Connect the `Dataset` to the `Split Data` module

![connect dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/13.png)

*Note that you can submit the pipeline at any point to peek at the outputs and activities. Running pipeline also generates metadata that is available for downstream activities such selecting column names from a list in selection dialogs. Please refer ahead to Exercise 3, Task 1, Step 2 on details of submitting the pipeline. It can take up to 5-10 minutes to run the pipeline.*

**Task 5: Select Columns in Dataset**

1. Select Data Transformation section in the left navigation. Follow the steps outlined below:

	* Select the Select Columns in Dataset prebuilt module
	* Drag and drop the selected module on to the canvas
	* Connect the first output of the `Split Data` module to the `Select Columns in Dataset` module
	* Select Edit column link to open the Select columns` editor
	
![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/13_1.png)

2. In the Select columns editor, follow the steps outlined below:

	* Include: All columns
	* Select +
	* Exclude: Column names, provide the following column names to exclude: Month, Year, Year_R, Timezone, Timezone_R
	* Select Save

![exclude columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/13_2.png)

**Task 6: Initialize Classification Model**

1. Select Machine Learning Algorithms section in the left navigation. Follow the steps outlined below:

	* Select the Two-Class Logistic Regression prebuilt module
	*  Drag and drop the selected module on to the canvas

![select algorithm](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/14.png)

**Task 7: Setup Train Model Module**

1. Select Model Training section in the left navigation. Follow the steps outlined below:

	* Select the `Train Model` prebuilt module
	* Drag and drop the selected module on to the canvas
	* Connect the `Two-Class Logistic Regression` module to the first input of the `Train Model` module
	* Connect the `Select Columns in Dataset` module to the second input of the `Train Model` module
	* Select the Edit column link to open the Label column editor

![train](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/15.png)

2. The `Label column editor` allows you to specify your `Label or Target column`. Type in the label column name ArrDel15 and then select Save.

![chooe target](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/16.png)

**Task 8: Setup Score Model Module**

1. Select Model Scoring & Evaluation section in the left navigation. Follow the steps outlined below:
	1. Select the `Score Model` prebuilt module
	2. Drag and drop the selected module on to the canvas
	3. Connect the `Train Model` module to the first input of the `Score Model` module
	4. Connect the second output of the `Split Data` module to the second input of the `Score Model` module.

![score model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/17.png)

*Note that Split Data module will feed data for both model training and model scoring.*

**Task 9: Setup Evaluate Model Module**

1. Select Model Scoring & Evaluation section in the left navigation. Follow the steps outlined below:
	
	* Select the `Evaluate Model` prebuilt module
	* Drag and drop the selected module on to the canvas
	* Connect the `Score Model` module to the first input of the `Evaluate Model` module

![evaluate model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/18.png)

#### Exercise 3: Submit Training Pipeline

**Task 1: Create Experiment and Submit Pipeline**

1. Select Submit to open the Setup pipeline run editor.

![create](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/19.png)

2. In the `Setup pipeline run editor`, select Experiment, Create new and provide `New experiment name`: flight-delay, and then select Submit.

![new experiment](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/20.png)

3. Wait for pipeline run to complete. It will take around 10 minutes to complete the run.

4. While you wait for the model training to complete, you can learn more about the evaluation metrics for the classification algorithm used in this lab by selecting [Metrics for classification models](https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-module-reference/evaluate-model#bkmk_classification)

### Exercise 4: Visualize the Evaluation Results

**Task 1: Open the Result Visualization Dialog**

1. Select Evaluate Model, Outputs, Visualize to open the Evaluate Model result visualization dialog.

![visualize](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/23.png)

**Task 2: Evaluate Model Performance**

1. Evaluate the model performance by reviewing the various evaluation curves, such as ROC curve, Precision-recall curve, and Lift curve.

![evaluate](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/24_1.png)

2.  Scroll down to review the following:

	* Review the key metrics for classifiers: Accuracy, Precision, Recall, F1 Score, and AUC
	* Review the binary classifier’s Confusion Matrix

![review metrics](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-05/images/24_2.png)

#### Next Steps

Congratulations! You have trained and evaluated your first classification machine learning model. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 3.29 Walkthrough

[Video](https://www.youtube.com/watch?v=P8XkYitGtXE&feature=emb_logo)

### 3.30 Prelaunch Lab

**No notes here**

### 3.31 Strength in Numbers

* Remember, no matter how well-trained an individual model is, there is still a significant chance that it could perform poorly or produce incorrect results. 
* Rather than relying on a single model, you can often get better results by training multiple models or using multiple algorithms and in some way capturing the collective results. 
* As we mentioned, there are two main approaches to this: Ensemble learning and automated machine learning. Let's have a closer look at each of them.
* Remember, ensemble learning combines multiple machine learning models to produce one predictive model. There are three main types of ensemble algorithms:
	* **Bagging or bootstrap aggregation**:
  		 * Helps reduce overfitting for models that tend to have high variance (such as decision trees)
    		* Uses random subsampling of the training data to produce a bag of trained models.
    		* The resulting trained models are homogeneous
    		* The final prediction is an average prediction from individual models
	* **Boosting**:
		* Helps reduce bias for models.
		*  In contrast to bagging, boosting uses the same input data to train multiple models using different hyperparameters.
		* Boosting trains model in sequence by training weak learners one by one, with each new learner correcting errors from previous learners
		* The final predictions are a weighted average from the individual models
	* **Stacking**:
		*  Trains a large number of completely different (heterogeneous) models
    		* Combines the outputs of the individual models into a meta-model that yields more accurate predictions
* Automated machine learning, like the name suggests, automates many of the iterative, time-consuming, tasks involved in model development (such as selecting the best features, scaling features optimally, choosing the best algorithms, and tuning hyperparameters). 
* Automated ML allows data scientists, analysts, and developers to build models with greater scale, efficiency, and productivity—all while sustaining model quality. 

#### Quizzes: 

![Question 1](https://i.imgur.com/dA2VCuC.png)

### 3.32 Lab: Train a Two-Class Boosted Decision Tree

#### Getting Started

* If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![quickstart](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

* If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following credentials:

Username:odl_user_92747@udacitylabs.onmicrosoft.com

Password:mopq01QNO*p3

 and Click on Sign in.

* After sign-in please click on Next button in bottom right corner of lab guide.

#### Lab Overview

Azure Machine Learning designer (preview) gives you a cloud-based interactive, visual workspace that you can use to easily and quickly prep data, train and deploy machine learning models. It supports Azure Machine Learning compute, GPU or CPU. Machine Learning designer also supports publishing models as web services on Azure Kubernetes Service that can easily be consumed by other applications.

In this lab, we will be using the Flight Delays data set that is enhanced with the weather data. Based on the enriched dataset, we will learn to use the Azure Machine Learning Graphical Interface to process data, build, train, score, and evaluate a classification model to predict if a particular flight will be delayed by 15 minutes or more. The classification algorithm used in this lab will be the ensemble algorithm: Two-Class Boosted Decision Tree. To train the model, we will use Azure Machine Learning Compute resource. We will do all of this from the Azure Machine Learning designer without writing a single line of code.

#### Exercise 1: Register Dataset with Azure Machine Learning studio

**Task 1: Upload Dataset**

1. In Azure portal, open the available machine learning workspace.

2. Select Launch now under the Try the new Azure Machine Learning studio message.

![launch](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/01a.png)

3. When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![select compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started.*

4. From the studio, select Datasets, + Create dataset, From web files. This will open the `Create dataset from web files` dialog on the right.

![web file](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/04.png)

5. In the Web URL field provide the following URL for the training data file:

` https://introtomlsampledata.blob.core.windows.net/data/flightdelays/flightdelays.csv`

6. Provide `flightdelays` as the Name, leave the remaining values at their defaults and select Next.

![name data](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/05.png)

**Task 2: Preview Dataset**

1. On the Settings and preview panel, set the column headers drop down to `All files have same headers`.

2. Review the dataset and then select Next

![dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/06.png)

**Task 3: Select Columns**

1. Select columns from the dataset to include as part of your training data. Leave the default selections and select Next

![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/07.png)

**Task 4: Create Dataset**

1. Confirm the dataset details and select Create

![create](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/08.png)

#### Exercise 2: Create New Training Pipeline

**Task 1: Open Pipeline Authoring Editor**

1. From the studio, select Designer, +. This will open a `visual pipeline authoring editor`.

![pipeline](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/09.png)

**Task 2: Setup Compute Target**

1. In the settings panel on the right, select Select compute target.

![select compute target](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/10.png)

2. In the Set up `compute target editor`, select the available compute, and then select Save.

*Note: If you are facing difficulties in accessing pop-up windows or buttons in the user interface, please refer to the Help section in the lab environment.*

![compute target](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/11.png)

**Task 3: Add Dataset**

1. Select Datasets section in the left navigation. Next, select My Datasets, flightdelays and drag and drop the selected dataset on to the canvas.

![select data](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/12.png)

**Task 4: Split Dataset**

1. We will split the dataset such that months prior to October will be used for model training and months October to December will be used for model testing.

2. Select Data Transformation section in the left navigation. Follow the steps outlined below:

	1. Select the Split Data prebuilt module

	2. Drag and drop the selected module on to the canvas

	3. Splitting mode: Relative Expression

	4. Relational expression: \”Month” < 10 (please make sure that the expression is provided exactly as seen in the image below, starting with backslash.)

	5. Connect the `Dataset` to the `Split Data` module

![split data](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/13.png)

*Note that you can submit the pipeline at any point to peek at the outputs and activities. Running pipeline also generates metadata that is available for downstream activities such selecting column names from a list in selection dialogs.*

**Task 5: Select Columns in Dataset**

1. Select Data Transformation section in the left navigation. Follow the steps outlined below:
	1. Select the Select Columns in Dataset prebuilt module
	2. Drag and drop the selected module on to the canvas
	3. Connect the first output of the `Split Data` module to the `Select Columns in Dataset` module
	4. Select Edit column link to open the Select columns` editor

![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/13_1.png)

2. In the `Select columns` editor, follow the steps outlined below:
	1. Include: All columns
	2. Select +
	3.  Exclude: Column names, provide the following column names to exclude: Month, Year, Year_R, Timezone, Timezone_R
	4. Select Save

![exclude columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/13_2.png)

**Task 6: Initialize Classification Model**

1. Select Machine Learning Algorithms section in the left navigation. Follow the steps outlined below:
	1. Select the Two-Class Boosted Decision Tree prebuilt module
	2. Drag and drop the selected module on to the canvas

![select algorithm](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/14.png)

Task 7: Setup Train Model Module

1. Select Model Training section in the left navigation. Follow the steps outlined below:

	1. Select the Train Model prebuilt module
	2. Drag and drop the selected module on to the canvas
 	3. Connect the Two-Class Boosted Decision Tree module to the first input of the Train Model module
	4. Connect the Select Columns in Dataset module to the second input of the Train Model module
	5. Select the Edit column link to open the Label column editor

![setup train](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/15.png)

2. The Label column editor allows you to specify your Label or Target column. Type in the label column name ArrDel15 and then select Save.

![save target](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/16.png)

**Task 8: Setup Score Model Module**

1. Select Model Scoring & Evaluation section in the left navigation. Follow the steps outlined below:

	1. Select the Score Model prebuilt module
	2. Drag and drop the selected module on to the canvas
	3. Connect the Train Model module to the first input of the Score Model module
	4. Connect the second output of the Split Data module to the second input of the Score Model module

![model scoring](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/17.png)

*Note that Split Data module will feed data for both model training and model scoring.*

**Task 9: Setup Evaluate Model Module**

1. Select Model Scoring & Evaluation section in the left navigation. Follow the steps outlined below:
	1. Select the Evaluate Model prebuilt module
	2. Drag and drop the selected module on to the canvas
	3. Connect the Score Model module to the first input of the Evaluate Model module

![evaluate](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/18.png)

### Exercise 3: Submit Training Pipeline

**Task 1: Create Experiment and Submit Pipeline**

 1. Select Submit to open the Setup pipeline run editor.

![submit pipeline](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/19.png)

*Please note that the button name in the UI is changed from Run to Submit.*

2. In the `Setup pipeline run editor`, select Experiment, Create new and provide `New experiment name`: flight-delay, and then select Submit.

![new experiment name](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/20.png)

3. Wait for pipeline run to complete. It will take around 10 minutes to complete the run.

4. While you wait for the model training to complete, you can learn more about the classification algorithm used in this lab by selecting [Two-Class Boosted Decision Tree](https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-module-reference/two-class-boosted-decision-tree).

#### Exercise 4: Visualize the Evaluation Results

**Task 1: Open the Result Visualization Dialog**

1. Select Evaluate Model, Outputs, Visualize to open the Evaluate Model result visualization dialog.

![visualize](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/23.png)

**Task 2: Evaluate Model Performance**

1. Evaluate the model performance by reviewing the various evaluation curves, such as ROC curve, Precision-recall curve, and Lift curve.

![check visualizations](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/24_1.png)

2. Scroll down to review the following:

	1. Review the key metrics for classifiers: Accuracy, Precision, Recall, F1 Score, and AUC
	2. Review the binary classifier’s Confusion Matrix

![confusion matrix](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-06/images/24_2.png)

#### Next Steps

Congratulations! You have trained and evaluated your first ensemble machine learning model. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 3.33 Walkthrough

![Video](https://www.youtube.com/watch?v=AhLfTUincPQ&feature=emb_logo)

### 3.34 Prelaunch Lab

**No notes here**

### 3.35 Lab: Train a Simple Classifier with Automated ML

#### Getting Started

1. If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![quickstart](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

2. If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following credentials:

Username:odl_user_92810@udacitylabs.onmicrosoft.com

Password:ghar27STM*5f

and Click on Sign in.

3. After sign-in please click on Next button in bottom right corner of lab guide.

#### Lab Overview

Automated machine learning picks an algorithm and hyperparameters for you and generates a model ready for deployment. There are several options that you can use to configure automated machine learning experiments.

Configuration options available in automated machine learning:
* Select your experiment type: Classification, Regression or Time Series Forecasting
*  Data source, formats, and fetch data
*  Choose your compute target
*  Automated machine learning experiment settings
*  Run an automated machine learning experiment
*  Explore model metrics
*  Register and deploy model

You can create and run automated machine learning experiments in code using the Azure ML Python SDK or if you prefer a no code experience, you can also create your automated machine learning experiments in Azure Machine Learning Studio.

In this lab, you learn how to create, run, and explore automated machine learning experiments in the Azure Machine Learning Studio without a single line of code. As part of this lab, we will be using the Flight Delays data set that is enhanced with the weather data. Based on the enriched dataset, we will use automated machine learning to find the best performing classification model to predict if a particular flight will be delayed by 15 minutes or more.

#### Exercise 1: Register Dataset with Azure Machine Learning studio

**Task 1: Upload Dataset**

1. In Azure portal, open the available machine learning workspace.
2. Select Launch now under the Try the new Azure Machine Learning studio message.

![launch](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/01a.png)

3. When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![SELECT COMPUTE](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started*

4. From the studio, select Datasets, + Create dataset, From web files. This will open the `Create dataset from web files` dialog on the right.

![select dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/04.png)

5. In the Web URL field provide the following URL for the training data file:
 `https://introtomlsampledata.blob.core.windows.net/data/flightdelays/flightdelays.csv`

6. Provide `flightdelays-automl` as the Name, leave the remaining values at their defaults and select Next.

![name of dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/05.png)

**Task 2: Preview Dataset**

1. On the Settings and preview panel, set the column headers drop down to All files have same headers.
2. Review the dataset and then select Next

![preview](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/06.png)

**Task 3: Select Columns**

1. Select columns from the dataset to include as part of your training data. Exclude the following columns: Path, Month, Year, Timezone, Year_R, Timezone_R, and then select Next

![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/07.png)

**Task 4: Create Dataset**

1. Confirm the dataset details and select Create

![create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/08.png)

#### Exercise 2: Setup New Automated Machine Learning Experiment

**Task 1: Create New Automated Machine Learning Experiment**

1. From the studio home, select Create new, Automated ML run

![automated](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/02.png)

2. This will open a Create a new automated machine learning experiment page.

**Task 2: Select Training Data**

1. Select the dataset `flightdelays-automl` and then select Next

![select dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/09.png)

**Task 3: Create a new Automated ML run**

1. Provide an experiment name: flight-delay
2. Select target column: ArrDel15
3. Select compute target: select the available compute
4. Select Next

![setup](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/10.png)

**Task 4: Setup Task type and Settings**

1. Select task type: Classification, and then select View additional configuration settings

![task type](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/11.png)

2. This will open the Additional configurations dialog.

3. Provide the following information and then select Save
	1. Primary metric: AUC weighted
	2. Exit criteria, Training job time (hours): 1
	3. Exit criteria, Metric score threshold: 0.7

![optim setup](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/12.png)

*Note that we are setting a metric score threshold to limit the training time. In practice, for initial experiments, you will typically only set the training job time to allow AutoML to discover the best algorithm to use for your specific data.*

#### Exercise 3: Start and Monitor Experiment

**Task 1: Start Experiment**

1. Select Finish to start running the experiment

![start experiment](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/13.png)

**Task 2: Monitor Experiment**

1. The experiment will run for about 30 min. Note that most of the time will be spent in the data preparation step and once the data preparation is done, the experiment will take an additional 1-2 minutes to complete.

2. In the Details tab, observe the run status of the job.

![run status](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/14.png)

3. Select the Models tab, and observe the various algorithms the AutoML is evaluating. You can also observe the corresponding AUC weighted scores for each algorithm.

![various algorithms](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/15.png)

*Note that we have set a metric score threshold to limit the training time. As a result you might see only one algorithm in your models list.*

4. Select Details and wait till the run status becomes Completed.

![details](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/16.png)

5. While you wait for the model training to complete, you can learn to view and understand the charts and metrics for your automated machine learning run by selecting [Understand automated machine learning results](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-understand-automated-ml).

#### Exercise 4: Review Best Model’s Performance

**Task 1: Review Best Model Performance**

1. The Details tab shows the Best model summary. Next, select Algorithm name to review the model details.

![details](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/17.png)

2. From the Model details tab, to view the various metrics to evaluate the best model performance, select View all other metrics.

![view other metrics](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/18_1.png)

3. Review the model performance metrics and then select Close.

![model performance](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/18_2.png)

4. Next, select Metrics to review the various model performance curves, such as Precision-Recall, ROC, Calibration curve, Gain & Lift curves, and Confusion matrix.

![review metrics](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-07/images/19.png)

#### Next Steps

Congratulations! You have trained and evaluated your first automated machine learning model. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 3.36 Walkthrough

![Video](https://www.youtube.com/watch?time_continue=2&v=GQA96QHGfyE&feature=emb_logo)

### 3.37 Lesson Summary

* In this lesson, you've learned to perform the essential data preparation and management tasks involved in machine learning:
	* Data importing and transformation
	* The use of datastores and datasets
	* Versioning
	* Feature engineering
	* Monitoring for data drift
* The second major area we covered in this lesson was model training, including:
	* The core model training process
	*  Two of the fundamental machine learning models: Classifier and regressor
	* The model evaluation process and relevant metrics
* The final part of the lesson focused on how to get better results by using multiple trained models instead of a single one. 
* In this context, you learned about ensemble learning and automated machine learning. You've learned how the two differ, yet apply the same general principle of "strength in numbers".
*  In the process, you trained an ensemble model (a decision forest) and a straightforward classifier using automated Machine Learning.


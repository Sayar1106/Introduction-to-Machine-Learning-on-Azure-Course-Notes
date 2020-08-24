# Introduction to Machine Learning on Azure

## Lesson 2

### 2.1 Lesson Overview

* Goal is to give a high-level introduction to the field of machine learning, including the broader context in which this branch of computer science exists.
* Topics to be covered:
	* What machine learning is and why it's so important in today's world
	* The historical context of machine learning
	*  The data science process
	*  The types of data that machine learning deals with
	* The two main perspectives in ML: the statistical perspective and the computer science perspective
	* The essential tools needed for designing and training machine learning models
	* The basics of Azure ML
	* The distinction between models and algorithms
	* The basics of a linear regression model
	*  The distinction between parametric vs. non-parametric functions
	* The distinction between classical machine learning vs. deep learning
	* The main approaches to machine learning
	* The trade-offs that come up when making decisions about how to design and train
machine learning models

### 2.2 What is Machine Learning?

* What is Machine Learning?
	* Machine Learning is a data science technique used to extract patterns from data allowing computers to identify related data, forecast future outcomes, behaviours, and trends.
* How is Machine Learning different from traditional programming?
	* Traditional Programming: Input of hardcoded rules and data is used to arrive at answers.
	* Machine Learning: Input of data and answers and come up with rules.

#### Quizzes:

![Question 1](https://imgur.com/XgbNxqJ.png)
![Question 2](https://i.imgur.com/wJs0uA9.png)
![Question 3](https://i.imgur.com/N31G5hX.png)
![Question 4](https://i.imgur.com/f1pWWcE.png)
![Question 5](https://i.imgur.com/gu5ZkyO.png)

### 2.3 Applications of Machine Learning

* Automate the recognition of disease
	* Used to spot diseases, reducing physician burnout.
	* [Google has trained a deep learning model to detect breast cancer](https://www.mercurynews.com/2017/03/03/google-computers-trained-to-detect-cancer/)
	* [Stanford researchers have used deep learning models to diagnose skin cancer.](https://news.stanford.edu/2017/01/25/artificial-intelligence-used-identify-skin-cancer/)
* Recommend next best actions for individual care plans
	* EMR(Electronic Medical Records) and EHRs(Electronic Health Records) have enabled digitization of patient data.
	* Machine Learning can be used to help build effective individual care plans.
	* [IBM Watson Oncology helps clinicians explore potential treatment options.](https://www.ibm.com/products/clinical-decision-support-oncology)
* Enable personalized, real-time banking experience with chatbots
	* Machine Learning is being used to intercept and handle common straightforward issues through chat and messaging services.
	* Customers simply type in a question and the bot engages to surface the answer.
	* [Article](https://www.drift.com/learn/chatbot/ai-chatbots/) about chatbot powered machine learning.
* Identify the next best action for the customer
	* Real-time insights that incorporate machine learning tools can help organizations assess likelihood of a deal closing or the level of customer loyalty.
	* [Personally-tailored recommendations powered](https://medium.com/@madasamy/introduction-to-recommendation-systems-and-how-to-design-recommendation-system-that-resembling-the-9ac167e30e95) by machine learning can engage and delight customers with information and offers that are relevant to them.
* Capture, prioritize, and route service requests to the correct employee, and improve response times
	* Busy government organizations gets innumerable service requests on an annual basis.
	* Machine learning tools can help to capture incoming service requests, to route them to the correct employee in real-time, to refine prioritization, and improve response times.
	* This [article](https://monkeylearn.com/blog/ticket-routing/) has more informations about ticket routing.

### 2.4 Brief History of Machine Learning

* 1950s
	*  AI was an emerging where the main focus was to build programs  to copy the way humans think and act.
* 1980s
	* The focus shifted towards specific areas of AI. One area was Machine Learning which is dealing with writing programs to identify patterns without explicitly being programmed to do so. 
	* One such class was Neural Nets which was inspired by the structure of the human brain.
	* Computing limitations limited the applicability of Neural Nets.
* 2000s and 2010s
	* Explosion of computing power such as GPUs brought Neural Nets back to the spotlight.
	* All of a sudden very large Neural Nets were being trained and achieved spectacular results in NLP and Computer Vision.
	* These Neural Nets were much larger and complex as opposed to those in the 1980s and thus, gave rise to the term Deep Learning.

![Brief History of Machine Learning](https://i.imgur.com/LWe7R9c.png)

#### Quizzes:

![IQuestion 1](https://i.imgur.com/QIsVQ6y.png)

### 2.5 The Data Science Process
* Collect Data
	* Retrieve files.
	* Query Databases.
	* Calling web services.
	* Scraping web pages.
* Prepare Data
	* Impute missing values.
	* Aggregate data metrics.
	* Visualize data and identify useful features.
* Training Model
	* Select Algorithm.
	* Train Validation, Test split.
	* Feature scaling, vectorization.
	* Train iteratively.
	* Check model performance on validation data.
	* Tune hyperparameters.
* Evaluate Model
	* Test and compare various models on test data using evaluation metrics.
* Deploy Model
	* Package model and dependencies and deploy.
	* Use proper versioning.
	* Use it with application or API.
	* Measure ongoing performance of the model.
* Re-train Model
	* Data environment changes affect model performance.
	* Re-train on fresh data.
	* Iterative procedure.

![Data Science Process](https://i.imgur.com/CSu4tvN.png)

#### Quizzes:

![Question 1](https://i.imgur.com/VKuTMjl.png)
![Question 2](https://i.imgur.com/OfFnAaR.png)
![Question 3](https://i.imgur.com/1Fhha74.png)

### 2.6 Common Types of Data

* Numerical
	* Integers or floats.
	* Sales Amounts, House Prices.
	* All data in machine learning eventually ends up being numerical, regardless of whether it is numerical in its original form, so it can be processed by machine learning algorithms. 
* Time-Series
	* Numerical data that is ordered by time.
	* Stock prices, Orange juice sales, energy demand forecasting.
* Categorical
	* Discrete values
	* Gender, Ethnicity (small cardinality), Product ID (large cardinality)
* Text
	* Words, sentences.
	* Examples: news articles.
	* Difficult to convert to numerical values.
* Images
	* Picture, snapshot or stream of video.
	* Difficult to convert to numerical values.

#### Quizzes:

![Question 1](https://i.imgur.com/6E3Xxhg.png)
![Question 2](https://i.imgur.com/YnkFhtP.png)

### 2.7 Tabular Data

* In machine learning, the most common type of data you'll encounter is tabular data—that is, data that is arranged in a data table. 
* This is essentially the same format as you work with when you look at data in a spreadsheet.
* All non-numerical data types (such as images, text, and categories) must eventually be represented as numbers.
* In machine learning, the numerical representation will be in the form of an array of numbers—that is, a vector.
* A vector is simply an array of numbers, such as `(1, 2, 3)`—or a nested array that contains other arrays of numbers, such as `(1, 2, (1, 2, 3))`.

#### Example of tabular data:

![Example](https://i.imgur.com/ai1dG0q.png)

#### Quizzes: 

![Question 1](https://i.imgur.com/BMFxmTy.png)
![Question 2](https://i.imgur.com/oNnjqnF.png)

### 2.8 Scaling Data

* Scaling data means transforming it so that the values fit within some range or scale, such as `0–100` or `0–1`.
* Why scale?
	* Imagine you have an image represented as a set of RGB values ranging from `0 to 255`.
	* Imagine you have an image represented as a set of RGB values ranging from `0 to 255.
	* This scaling process will not affect the algorithm output since every value is scaled in the same way.
	* It can also speed up the training process, because now the algorithm only needs to handle numbers less than or equal to `1`.
* Approaches to scaling
	* Standardization
		* Rescales  data so that it has a mean of `0` and a standard deviation of `1`.
	* Normalization.
		*  Rescales the data into the range `[0, 1]`.

#### Standardization formula:

![Standardization formula](https://i.imgur.com/CFNpDj3.png)

#### Standardization example:

![Standardization example](https://i.imgur.com/9JuiwdZ.png)

#### Normalization formula:

![Normalization formula](https://i.imgur.com/pavaNit.png)

#### Normalization example:

![Normalization example](https://i.imgur.com/UlMhGqs.png)

#### Quizzes:

![Question 1](https://i.imgur.com/wJvv8P8.png)
![Question 2 & 3](https://i.imgur.com/SEnLglQ.png)

### 2.9 Encoding Categorical Data

* Machine learning algorithms need to have data in numerical form.
* When we have categorical data, we need to encode it in some way so that it is represented numerically. 
* Approaches: 
	* Ordinal encoding
		* we simply convert the categorical data into integer codes ranging from `0` to (number of categories `– 1`). 
		* One of the potential drawbacks to this approach is that it implicitly assumes an order across the categories.
	* One hot encoding
		* We transform each categorical value into a column. 
		* If there are `n` categorical values,`n` new columns are added.
		* One drawback of one-hot encoding is that it can potentially generate a very large number of columns.

#### Ordinal encoding example:

![Ordinal encoding example](https://i.imgur.com/qIQFPrd.png)

#### One hot encoding example:

![One hot encoding example](https://imgur.com/FpKXqda.png)

#### Quizzes:

![Question 1 & 2](https://i.imgur.com/DaLZlvR.png)
![Question 3 & 4](https://i.imgur.com/kI7JpIR.png)

### 2.10 Image Data

* Another example of a data type that is commonly used as input in machine learning problems—but that isn't initially in numerical format.
* How to represent an image as numbers?
	* The number of channels required to represent the color is known as the color depth or simply depth.
	* Grayscale images
		*  Each pixel can be represented by a single number, which typically ranges from 0 to 255.
		* This value determines how dark the pixel appears (e.g., `0` is black, while `255` is bright white).
		* In an RGB image, `depth = 3`, because there are three channels (Red, Green, and Blue).
	* Colored images
		*  Each pixel can be represented by a vector of three numbers (each ranging from 0 to 255) for the three primary color channels: red, green, and blue.
		* These three red, green, and blue (RGB) values are used together to decide the color of that pixel.
		* For example, purple might be represented as 1`28, 0, 128` (a mix of moderately intense red and blue, with no green).
		* A grayscale image has `depth = 1`, because there is only one channel.
* Three things are required to reproduce an image:
	* Horizontal position of each pixel.
	* Vertical position of each pixel.
	* Color of each pixel.
* The size of the vector required for any given image would be the `height * width * depth` of that image.
* Other preprocessing steps:
	* Uniform aspect ratio (e.g., by making sure all of the input images are square in shape).
	* Normalized (e.g. subtract mean pixel value in a channel from each pixel value in that channel).
	* Rotation
	* Cropping
	* Resizing
	* Denoising
	* Centering the image

#### Quizzes:

![Question 1](https://i.imgur.com/fEkzVw7.png)
![Question 2](https://i.imgur.com/YfE7H3j.png)

### 2.11 Text Data

* One of the challenges that can come up in text analysis is that there are often multiple forms that mean the same thing.
	* The verb `to be` may show up as` is`, `am`, `are`, and so on.
	* A document may contain alternative spellings of a word, such as `behavior` vs. `behaviour`.
* Text normalization - process of transforming a piece of text into a canonical (official) form.
	* Lemmatization is an example of normalization.
	* A lemma is the dictionary form of a word and lemmatization is the process of reducing multiple inflections to that single dictionary form.
	*  Stop words are high-frequency words that are unnecessary (or unwanted) during the analysis. 
	* When you enter a query like `which cookbook has the best pancake recipe` into a search engine, the words `which` `and` `the` are far less relevant than `cookbook`,`pancake`, and `recipe`.
	* In this context, we might want to consider which and the to be stop words and remove them prior to analysis.
* Text vectorization - turning a piece of text into a vector.
	* After normalization we can take the next step of actually encoding it in a numerical form.
	* The goal here is to identify the particular features of the text that will be relevant to us for the 	particular task we want to perform.
	* Approaches:
		* Term Frequency-Inverse Document Frequency (TF-IDF) vectorization.
		* Word embedding, as done with Word2vec or Global Vectors (GloVe).
	* Brief example of TF-IDF:
		* The approach of TF-IDF is to give less importance to words that contain less information and are common in documents.
			* "the" and "this"
		* Give higher importance to words that contain relevant information and appear less frequently.
		* TF-IDF assigns weights to words that signify their relevance in the documents.
		* Each chunk of text gets a vector that is the length of the total number of words that we are interested in.
		* If the normalized text does not have the word in question, then the value in that position is `0`, whereas if it does have the word in question, it gets assigned to the importance of the word.
* Features Extraction
	* Vectors with length `n` can be visualized as a line in an `n` dimension space.
	* Any vector with the same length can be visualized in the same space.
	* How close one vector is to another can be calculated as vector distance.
	* If two vectors are close to each other, we can say the text represented by the two vectors have a similar meaning or have some connections.

#### Lemmatization example:

![Lemmatization example](https://i.imgur.com/ZRKv79X.png)

#### Normalization example:

![Normalization example](https://i.imgur.com/IvEL9Xe.png)

#### Vectorization example:

![Vectorization example](https://i.imgur.com/yfvEQuk.png)

#### TF-IDF example:

![TF-IDF example](https://i.imgur.com/B2UVQqI.png)

#### Quizzes:

![Question 1](https://i.imgur.com/5zPfKnk.png)
![Question 2&3](https://i.imgur.com/VxKok32.png)
![Question 4](https://i.imgur.com/7UIvTLR.png)
![Question 5](https://i.imgur.com/3hICklK.png)

### 2.12 Two Perspectives on ML

* Computer Science perspective:
	* We are using input features to create a program that can generate the desired output.
* Statistical perspective:
	* We are trying to find a mathematical function that, given the values of the independent variables can predict the values of the dependent variables.

#### Quizzes:

![Question 1](https://i.imgur.com/d3r7ftl.png)

### 2.13 The Computer Science Perspective

* For the rows in the table, we might call each row an entity or an observation about an entity.
* You'll also sometimes see a row of data referred to as an instance, in the sense that a row may be considered a single example (or instance) of data.
* For the columns in the table, we might refer to each column as a feature or attribute which describes the property of an entity.
* In a typical case of machine learning, you have some kind of input which you feed into the machine learning algorithm, and the algorithm produces some output.

Input example:

![Input example](https://i.imgur.com/wSmdopc.png)

#### Output example:

![Output example](https://i.imgur.com/m1ZN5L2.png)

#### Quizzes:

![Question 1](https://i.imgur.com/1iynnyU.png)
![Question 2](https://i.imgur.com/RePwQo2.png)		

### 2.14 The Statistical Perspective

* In statistics, you'll also see the data described in terms of independent variables and dependent variables.
* These names come from the idea that the value of one variable may depend on the value of some other variables.
	*  the selling `price` of a house is the dependent variable that depends on some independent variables—like the house's `location` and `size`.

#### Function examples:

![Function example 1](https://i.imgur.com/jc5JUAK.png)
![Function example 2](https://i.imgur.com/gCIcT4G.png)

### 2.15 The Tools for Machine Learning

* Libraries:
	* When you're working on a machine learning project, you likely will not want to write all of the necessary code yourself.
	* Instead, you'll want to make use of code that has already been created and refined. 
	*  A library is a collection of pre-written (and compiled) code that you can make use of in your own project. 
		* Numpy
		* Tensorflow
* Development environments:
	* A software application (or sometimes a group of applications) that provide a whole suite of tools designed to help you (as the developer or machine learning engineer) build out your projects.
		* Jupyter Notebooks
		* Visual Studio
* Cloud services
	* A service that offers data storage or computing power over the Internet.
	* In the context of machine learning, you can use a cloud service to access a server that is likely far more powerful than your own machine, or that comes equipped with machine learning models that are ready for you to use.
	* Read this article [Machine Learning as a Service — The Top Cloud Platform and AI Vendors](https://medium.com/appanion/machine-learning-as-a-service-the-top-cloud-platform-and-ai-vendors-2df45d51374d).

#### Notebook Paradigm

![Notebook Paradigm](https://i.imgur.com/n25C9Dcl.png)

#### Data Science: End-to-End with Azure

![Data Science: End-to-End with Azure](https://i.imgur.com/86UDGiSl.png)

#### Quizzes:

![Question 1](https://i.imgur.com/nyCH1nUl.png)

#### 2.16 Libraries for Machine Learning

* Core Framework and Tools
	* [Python](https://www.python.org/) is a very popular high-level programming language that is great for data science. Its ease of use and wide support within popular machine learning platforms, coupled with a large catalog of ML libraries, has made it a leader in this space.
	* [Pandas](https://pandas.pydata.org/) is an open-source Python library designed for analyzing and manipulating data. It is particularly good for working with tabular data and time-series data.
	* [NumPy](https://numpy.org/), like Pandas, is a Python library. NumPy provides support for large, multi-dimensional arrays of data, and has many high-level mathematical functions that can be used to perform operations on these arrays.
* Machine Learning and Deep Learning
	* [Scikit-Learn](https://scikit-learn.org/stable/) is a Python library designed specifically for machine learning. It is designed to be integrated with other scientific and data-analysis libraries, such as [NumPy](https://numpy.org/), [SciPy](https://numpy.org/), and [matplotlib](https://matplotlib.org/) (described below).
	* [Apache Spark](https://spark.apache.org/) is an open-source analytics engine that is designed for cluster-computing and that is often used for large-scale data processing and big data.
	* [TensorFlow](https://www.tensorflow.org/) is a free, open-source software library for machine learning built by Google Brain.
	* [Keras](https://keras.io/) is a Python deep-learning library. It provide an Application Programming Interface (API) that can be used to interface with other libraries, such as TensorFlow, in order to program neural networks. Keras is designed for rapid development and experimentation.
	* [PyTorch](https://pytorch.org/) is an open source library for machine learning, developed in large part by Facebook's AI Research lab. It is known for being comparatively easy to use, especially for developers already familiar with Python and a Pythonic code style.
* Data Visualization
	* [Plotly](https://plotly.com/) is not itself a library, but rather a company that provides a number of different front-end tools for machine learning and data science—including an open source graphing library for Python.
	* [Matplotlib](https://matplotlib.org/) is a Python library designed for plotting 2D visualizations. It can be used to produce graphs and other figures that are high quality and usable in professional publications. You'll see that the Matplotlib library is used by a number of other libraries and tools, such as SciKit Learn (above) and Seaborn (below). You can easily import Matplotlib for use in a Python script or to create visualizations within a Jupyter Notebook.
	* [Seaborn](https://seaborn.pydata.org/) is a Python library designed specifically for data visualization. It is based on matplotlib, but provides a more high-level interface and has additional features for making visualizations more attractive and informative.
	* [Bokeh](https://bokeh.org/) is an interactive data visualization library. In contrast to a library like matplotlib that generates a static image as its output, Bokeh generates visualizations in HTML and JavaScript. This allows for web-based visualizations that can have interactive features.

#### Quizzes:

![Question 1](https://i.imgur.com/MRXuFO7l.png)

### 2.17 Cloud Services for Machine Learning

* Core assets:
	* Datasets	
		* Define, version, and monitor datasets used in machine learning runs.
	* Experiments / Runs
		* Organize machine learning workloads and keep track of each task executed through the service.
	*Pipelines
		* Structured flows of tasks to model complex machine learning flows.
	* Models
		* Model registry with support for versioning and deployment to production.
	* Endpoints
		* Expose real-time endpoints for scoring as well as pipelines for advanced automation.
* Managing resources:
	* Compute
		* Manage compute resources used by machine learning tasks.
	* Environments
		* Templates for standardized environments used to create compute resources.
	* Datastores
		* Data sources connected to the service environment (e.g. blob stores, file shares, Data Lake stores, databases).
* Azure ML Workspace:
	* Automated ML	
		* Automate intensive tasks that rapidly iterate over many combinations of algorithms, hyperparameters to find the best model based on the chosen metric.
	* Designer	
		* A drag-and-drop tool that lets you create ML models without a single line of code.
	* Datasets
		* A place you can create datasets.
	* Experiments
		* A place that helps you organize your runs.
	* Models	
		* A place to save all the models created in Azure ML or trained outside of Azure ML.	
	* Endpoints
		* A place stores real-time endpoints for scoring and pipeline endpoints for advanced automation.
	* Compute 
		* A designated compute resource where you run the training script or host the service deployment.
	* Datastores
		* An attached storage account in which you can store datasets.

#### Quizzes:

![Question 1](https://i.imgur.com/Lpun7MAl.png)

### 2.18 Models vs. Algorithms

* Models are the specific representations learned from data
* Algorithms are the processes of learning

#### Relationship between algorithm and model

![Relationship between algorithm and model](https://i.imgur.com/rmlef6rl.png)

#### More About Machine Learning Algorithms

![More About Machine Learning Algorithms](https://i.imgur.com/MLVuU06l.png)

#### Quizzes:

![Question 1](https://i.imgur.com/lChiVjrl.png)

### 2.19 Prelauch Lab

** No Notes here**

### 2.20 Linear Regression

*  Linear regression is an algorithm that uses a straight line (or plane) to describe relationships between variables.

#### Simple Linear Regression

![Simple Linear Regression](https://i.imgur.com/8nyKhW4l.png)

#### Example of Simple Linear Regression:

![Example of Simple Linear Regression](https://i.imgur.com/hGO6QMJl.png)

#### Linear Regression in Machine Learning

![Linear Regression in Machine Learning](https://i.imgur.com/pFK6LhVl.png)

#### Multiple Linear Regression

![Multiple Linear Regression](https://i.imgur.com/2U0ivFVl.png)

#### Training a Linear Regression Model

![Training a Linear Regression Model](https://i.imgur.com/CxV4Slsl.png)

#### Preparing the Data

![Preparing the Data](https://i.imgur.com/npGU8Z3l.png)

#### Calculating the Coefficients

![Calculating the Coefficients](https://i.imgur.com/bjwAPqsl.png)

#### Quizzes:

![Question 1](https://i.imgur.com/pqFH7cCl.png)
![Question 2](https://i.imgur.com/9g4eoGXl.png)

### 2.21 Linear Regression: Check Your Understanding

#### Quizzes:

![Question 1](https://i.imgur.com/uLSq4Fgl.png)
![Question 2](https://i.imgur.com/LD91X5al.png)
![Question 3](https://i.imgur.com/Mz0u6pLl.png)
![Question 4](https://i.imgur.com/DF9C01Bl.png)

### 2.22 Lab Instructions

** No Notes here**

### 2.23 Lab: Train a Linear Regression Model

Getting Started

1. If you are already in Azure portal please skip the instructions and click on Next button in bottom right corner of lab guide.

![1](https://raw.githubusercontent.com/SpektraSystems/Microsoft-Cloud-Workshop/master/udacity/images/udacity-labguide.png)

2. If you are not logged in into azure portal , From the desktop click on the ML studio icon to sign in into the Machine Learning studio using following:

credentials:Username:odl_user_89027@udacitylabs.onmicrosoft.com

Password:qxxc56EPG*pG

and Click on Sign in.

3. After sign-in please click on Next button in bottom right corner of lab guide.

#### Lab Overview

Azure Machine Learning designer (preview) gives you a cloud-based interactive, visual workspace that you can use to easily and quickly prep data, train and deploy machine learning models. It supports Azure Machine Learning compute, GPU or CPU. Machine Learning designer also supports publishing models as web services on Azure Kubernetes Service that can easily be consumed by other applications.

In this lab, we will be using a subset of NYC Taxi & Limousine Commission - green taxi trip records available from Azure Open Datasets. The data is enriched with holiday and weather data. Based on the enriched dataset, we will learn to use the Azure Machine Learning Graphical Interface to process data, build, train, score, and evaluate a regression model to predict NYC taxi fares. To train the model, we will create Azure Machine Learning Compute resource. We will do all of this from the Azure Machine Learning designer without writing a single line of code.

#### Exercise 1:  Register Dataset with Azure Machine Learning studio

**Task 1: Upload Dataset**

1. In Azure portal, open the available machine learning workspace.

2. Select Launch now under the Try the new Azure Machine Learning studio message.

![launch instance](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/01a.png)

3. When you first launch the studio, you may need to set the directory and subscription. If so, you will see this screen:

![welcome](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/00.png)

*For the directory, select Udacity and for the subscription, select Azure Sponsorship. For the machine learning workspace, you may see multiple options listed. Select any of these (it doesn’t matter which) and then click Get started.*

4. From the studio, select Datasets, + Create dataset, From web files. This will open the Create dataset from web files dialog on the right.

![create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/04.png)

5. In the Web URL field provide the following URL for the training data file:

` https://introtomlsampledata.blob.core.windows.net/data/nyc-taxi/nyc-taxi-sample-data.csv`

6. Provide nyc-taxi-sample-data as the Name, leave the remaining values at their defaults and select Next.

![Finish creating dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/05.png)

** Task 2: Preview Dataset**

1. On the Settings and preview panel, set the column headers drop down to All files have same headers.

2. Scroll the data preview to right to observe the target column: totalAmount. After you are done reviewing the data, select Next.

![preview data](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/06.png)

**Task 3: Select Columns**

1. Select columns from the dataset to include as part of your training data. Leave the default selections and select Next

![select columns](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/07.png)

**Task 4: Create Dataset**

1. Confirm the dataset details and select Create.

![create dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/08.png)

#### Exercise 2: Create New Training Pipeline

**Task 1: Open Pipeline Authoring Editor**

1. From the studio, select Designer, +. This will open a visual pipeline authoring editor.

![open pipeline editor](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/09.png)

**Task 2: Setup Compute Target**

1. In the settings panel on the right, select Select compute target.

![Setup compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/10.png)

2. In the Set up compute target editor, select the available compute, and then select Save.

*Note: If you are facing difficulties in accessing pop-up windows or buttons in the user interface, please refer to the Help section in the lab environment.*

![save compute](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/11.png)

**Task 3: Add Dataset**

1. Select Datasets section in the left navigation. Next, select My Datasets, nyc-taxi-sample-data and drag and drop the selected dataset on to the canvas.

![add dataset](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/12.png)

**Task 4: Split Dataset**

1. Select Data Transformation section in the left navigation. Follow the steps outlined below:

	1. Select the Split Data prebuilt module

	2. Drag and drop the selected module on to the canvas

	3. Fraction of rows in the first output dataset: 0.7

	4. Connect the Dataset to the Split Data module

![data transformation](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/13.png)

*Note that you can submit the pipeline at any point to peek at the outputs and activities. Running pipeline also generates metadata that is available for downstream activities such selecting column names from a list in selection dialogs.*

**Task 5: Initialize Regression Model**

1. Select Machine Learning Algorithms section in the left navigation. Follow the steps outlined below:

	1. Select the Linear Regression prebuilt module

	2. Drag and drop the selected module on to the canvas

![add model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/14.png)

**Task 6: Setup Train Model Module**

1. Select Model Training section in the left navigation. Follow the steps outlined below:

	1. Select the Train Model prebuilt module

	2. Drag and drop the selected module on to the canvas

	3. Connect the Linear Regression module to the first input of the Train Model module

	4. Connect the first output of the Split Data module to the second input of the Train Model module

	5. Select the Edit column link to open the Label column editor

![add train model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/15.png)

2. The Label column editor allows you to specify your Label or Target column. Type in the label column name totalAmount and then select Save.

![add labels](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/16.png)

**Task 7: Setup Score Model Module**

1. Select Model Scoring & Evaluation section in the left navigation. Follow the steps outlined below:

	1. Select the Score Model prebuilt module
	
	2. Drag and drop the selected module on to the canvas

	3. Connect the Train Model module to the first input of the Score Model module

	4. Connect the second output of the Split Data module to the second input of the Score Model module

![setup score model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/17.png)

*Task 8: Setup Evaluate Model Module*

1. Select Model Scoring & Evaluation section in the left navigation. Follow the steps outlined below:

	1. Select the Evaluate Model prebuilt module

	2. Drag and drop the selected module on to the canvas

	3. Connect the Score Model module to the first input of the Evaluate Model module

![score model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/18.png)

#### Exercise 3: Submit Training Pipeline

**Task 1: Create Experiment and Submit Pipeline**

1. Select Submit to open the Setup pipeline run editor.

![submit run](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/19.png)

Please note that the button name in the UI is changed from Run to Submit.

2. In the Setup pipeline run editor, select Experiment, Create new and provide New experiment name: designer-run, and then select Submit.

![run experiment](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/20.png)

3. Wait for pipeline run to complete. It will take around 8 minutes to complete the run.

4. While you wait for the model training to complete, you can learn more about the training algorithm used in this lab by selecting [Linear Regression module](https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-module-reference/linear-regression).

#### Exercise 4: Visualize Training Results

**Task 1: Visualize the Model Predictions**

1. Select Score Model, Outputs, Visualize to open the Score Model result visualization dialog.

![select model scoring](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/21.png)

2. Observe the predicted values under the column Scored Labels. You can compare the predicted values (Scored Labels) with actual values (totalAmount).

![observe predicted values](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/22.png)

**Task 2: Visualize the Evaluation Results**

1. Select Evaluate Model, Outputs, Visualize to open the Evaluate Model result visualization dialog.

![visualize model](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/23.png)

2. Evaluate the model performance by reviewing the various evaluation metrics, such as Mean Absolute Error, Root Mean Squared Error, etc.

![evaluate](https://raw.githubusercontent.com/solliancenet/udacity-intro-to-ml-labs/master/aml-visual-interface/lab-01/images/24.png)

#### Next Steps

Congratulations! You have trained and evaluated your first machine learning model. You can continue to experiment in the environment but are free to close the lab environment tab and return to the Udacity portal to continue with the lesson.

### 2.24 Walkthrough

[Video](https://www.youtube.com/watch?time_continue=6&v=-UgmbgLY5fc&feature=emb_logo)

### 2.25 Learning a function 

* We can generally think of a machine learning algorithm as a process for learning, and models as specific representations that we train using data.
* Machine learning algorithms aim to learn a target function `(f)` that describes the mapping between data input variables `(X)` and an output variable `(Y)`.
* The core goal is to learn a useful transformation of the input data that gets us closer to the expected output.
* Since the process extrapolates from a limited set of values, there will always be an error `e`.
* The variable`e` is called **irreducible error** because no matter how good we get at estimating the target function (ff), we cannot reduce this error.
* Note that the irreducible error we're discussing here is different from the model error we talked about earlier in the lesson.
* Irreducible error is caused by the data collection process—such as when we don't have enough data or don't have enough data features.
* In contrast, the model error measures how much the prediction made by the model is different from the true output.
* The model error is generated from the model and can be reduced during the model learning process.

#### Quizzes:

![Question 1](https://i.imgur.com/Xv2Dw6p.png)
![Question 2](https://i.imgur.com/ODDqtub.png)

### 2.26 Parametric vs. Non-parametric

* Based on the assumptions about the shape and structure of the function they try to learn, machine learning algorithms can be divided into two categories: 
	* **Parametric Machine Learning Algorithms**
		* Parametric machine learning algorithms make assumptions about the mapping function and have a fixed number of parameters. 
		* No matter how much data is used to learn the model, this will not change how many parameters the algorithm has.
		* With a parametric algorithm, we are selecting the form of the function and then learning its coefficients using the training data.
		* Example:
			* Linear Regression
		*  Benefits:
			* Simpler and easier to understand; easier to interpret the results
			* Faster when talking about learning from data
			* Less training data required to learn the mapping function, working well even if the fit to data is not perfect	
	* **Nonparametric Machine Learning Algorithms**
		* Non-parametric algorithms do not make assumptions regarding the form of the mapping function between input data and output.
		* Consequently, they are free to learn any functional form from the training data.
		* Example:
			* K-Nearest Neighbors
		* Benefits:
			* High flexibility, in the sense that they are capable of fitting a large number of functional forms.
			* Power by making weak or no assumptions on the underlying function
			* High performance in the prediction models that are produced
		* Limitations:
			* More training data is required to estimate the mapping function
			* Slower to train, generally having far more parameters to train
			* Overfitting the training data is a risk; overfitting makes it harder to explain the resulting predictions.

#### Quizzes:

![Question 1](https://i.imgur.com/AtA3Xkn.png)
![Question 2](https://i.imgur.com/nOkl9dx.png)
![Question 3](https://i.imgur.com/sy6t63C.png)

### 2.27 Classical ML vs. Deep Learning
 
* All deep learning algorithms are machine learning algorithms but not all machine learning algorithms are deep learning algorithms.
* Deep learning algorithms are based on neural networks and the classical ML algorithms are based on classical mathematical algorithms, such as linear regression, logistic regression, decision tree, SVM, and so on.
* **Deep learning advantages**:
	* Suitable for high complexity problems.
	* Better accuracy, compared to classical ML.
	* Better support for big data.
	* Complex features can be learned .
* **Deep learning disadvantages**:
	* Difficult to explain trained data.
	* Require significant computational power.
* **Classical ML advantages**:
	* More suitable for small data.
	* Easier to interpret outcomes.
	* Cheaper to perform.
	* Can run on low-end machines.
	* Does not require large computational power.
* **Classical ML disadvantages**:
	* Difficult to learn large datasets.
	* Require feature engineering.
	* Difficult to learn complex functions.

Quizzes:

![Question 1](https://i.imgur.com/fKXSt6e.png)
![Question 2](https://i.imgur.com/JvDIdFN.png)

### 2.28 Approaches to Machine Learning

* There are three main approaches to machine learning:
	* **Supervised learning** - Learns from data that contains both the inputs and expected outputs
		*  **Classification**: Outputs are categorical.
		* **Regression**: Outputs are continuous and numerical.
		* **Similarity learning**: Learns from examples using a similarity function that measures how similar two objects are.
		* **Feature learning**: Learns to automatically discover the representations or features from raw data.
		* **Anomaly detection**: A special form of classification, which learns from data labeled as normal/abnormal.
	* **Unsupervised learning** - Learns from input data only; finds hidden structure in input data.
		* **Clustering**: Assigns entities to clusters or groups.
		* **Feature learning**: Features are learned from unlabeled data.
		* **Anomaly detection**: Learns from unlabeled data, using the assumption that the majority of entities are normal. 
	* **Reinforcement learning** - Learns how an agent should take action in an environment in order to maximize a reward function.
		* **Markov decision process**: A mathematical process to model decision-making in situations where outcomes are partly random and partly under the control of a decision-maker. Does not assume knowledge of an exact mathematical model.
* The main difference between reinforcement learning and other machine learning approaches is that reinforcement learning is an active process where the actions of the agent influence the data observed in the future, hence influencing its own potential future states.
* In contrast, supervised and unsupervised learning approaches are passive processes where learning is performed without any actions that could influence the data.

#### Quizzes:

![Question 1](https://i.imgur.com/T9gyyRj.png)
![Question 2](https://i.imgur.com/b4CbKvg.png)
![Question 3](https://i.imgur.com/1zdCbmW.png)
![Question 4](https://i.imgur.com/3O0pTwO.png)

### 2.29 The Trade-Offs

* **Bias vs. Variance**
	* **Bias**: 
		* Bias measures how inaccurate the model prediction is in comparison with the true output. 
		* It is due to erroneous assumptions made in the machine learning process to simplify the model and make the target function easier to learn. 
		* High model complexity tends to have a low bias. 
	* **Variance**:
		* Variance measures how much the target function will change if different training data is used. 
		* Variance can be caused by modeling the random noise in the training data. 
		* High model complexity tends to have a high variance.
	* As a general trend, parametric and linear algorithms often have high bias and low variance, whereas non-parametric and non-linear algorithms often have low bias and high variance.
* **Overfitting vs. Underfitting**
	* **Overfitting**:
		* Overfitting refers to the situation in which models fit the training data very well, but fail to generalize to new data.
	* **Underfitting**:
		* Underfitting refers to the situation in which models neither fit the training data nor generalize to new data.
* **Bias vs. Variance Trade-off** 
	* The **prediction error** can be viewed as the sum of model error (error coming from the model) and the irreducible error (coming from data collection).
	* **Low bias**:
		* Low bias means fewer assumptions about the target function.
		* Having fewer assumptions can help generalize relevant relations between features and target outputs.
		* Example:
			* KNN
			* Decision Trees 
	* **High bias**:
		* high bias means more assumptions about the target function.
		* Having more assumptions can potentially miss important relations between features and outputs and cause underfitting.
		* Example:
			* Linear Regression  
	* **Low variance**:
		*  Low variance indicates changes in training data would result in similar target functions. 
		* Example:
			* Linear Regression
	* **High variance**:
		*  High variance indicates changes in training data would result in very different target functions. 
		* High variance suggests that the algorithm learns the random noise instead of the output and causes overfitting.
		* Example:
			* Support Vector Machines (SVM)
	* The goal of training machine learning models is to achieve low bias and low variance. The **optimal model complexity** is where bias error crosses with variance error.
* **Dealing with Overfitting vs. Underfitting**:
	*  [k-fold cross-validation](https://machinelearningmastery.com/k-fold-cross-validation/): 
		* It splits the initial training data into k subsets and train the model k times. In each training, it uses one subset as the testing data and the rest as training data.
	* **Validation dataset**: 
		* hold back a validation dataset from the initial training data to estimatete how well the model generalizes on new data.
	* **Simplify the model**: 
		* For example, using fewer layers or less neurons to make the neural network smaller.
use more data.
	* **Reduce dimensionality** :
		* Reduce dimensionality in training data such as PCA: it projects training data into a smaller dimension to decrease the model complexity.
	* **Early stopping**: 
		* Stop the training early when the performance on the testing dataset has not improved after a number of training iterations.

#### Bias-Variance Trade-Off

![Bias-Variance Trade-Off](https://i.imgur.com/4u32iq1.png)

#### Overfitting & Underfitting

![Overfitting & Underfitting](https://i.imgur.com/t1ruJzq.png)

#### Quizzes:

![Question 1](https://i.imgur.com/74puBG8.png)
![Question 2 & 3](https://i.imgur.com/QmTjHXE.png)
![Question 4](https://i.imgur.com/Do1hGxW.png)


### 2.30 Lesson Summary

* Here are the main topics we covered:
	* What machine learning is and why it's so important in today's world
	* The historical context of machine learning
	* The data science process
	* The types of data that machine learning deals with
	* The two main perspectives in ML: the statistical perspective and the computer science perspective
	* The essential tools needed for designing and training machine learning models
	* The basics of Azure ML
	* The distinction between models and algorithms
	* The basics of a linear regression model
	* The distinction between parametric vs. non-parametric functions
	* The distinction between classical machine learning vs. deep learning
	* The main approaches to machine learning
	* The trade-offs that come up when making decisions about how to design and training machine learning models

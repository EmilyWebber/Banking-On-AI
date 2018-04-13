## Getting Started

### Download, Upload, and Unzip the Dataset
1. Download the data from this link: https://www.kaggle.com/c/springleaf-marketing-response/data
	- Click on the file `test.csv.zip` to initiate the download. The file is 150 MB zipped, so it make take a minute.

2. Navigate to your Sagemaker Notebook instance.
	- Look at the folder listings in your web browser. 
	- Click 'Upload'
	- Now navigate to your Downloads folder
	- Click on `test.csv.zip`
	- Click OK.
	- Click the blue `Download` box.
		- Sagemaker Notebook instances are designed to host only the notebook, not large datasets. Because this sample of data is just under 1 GB, we can still work with it on the notebook instance itself.
		- For datasets that are much larger than this, you have a few options. We recommend either using another set of AWS tools designed for handling large data sets, or expanding the size of your notebook instance through adding an EFS volume to it. 
		- The blue progress bar should show you the progress of your data set. Uploading this zip file took me a few minutes.
		
3. Navigate to your Sagemaker Notebook Terminal, and unzip the file with the command `unzip test.csv.zip` inside of the directory where you uploaded the data. You can type `ls` again if you want to after the file has finished inflating to make sure it has successfully unzipped.

### Open a new Juyter Notebook and access the data
1. Navigate back to the list of the folders in your web browswer inside of the Sagemaker Notebook instance.

2. If you don't see `test.csv`, try refreshing the page with the button at the top right-hand side of the page, or review the steps above to make sure you have successfully downloaded and uploaded the data.

3. Click `New`, and then `conda_python3`. This will open a new Python 3 IPython notebook. 

4. Give your new notebook a name by clicking on `Untitled` at the top of the screen and naming it whatever you like.

5. Import some Python libraries to give yourself access to the tools available in Python Anaconda. We'll start with the Pandas Library, which you can read about here: https://pandas.pydata.org/.
	- Import the library by typing `import pandas as pd` in the first cell of your notebook. 
	- Then run the cell by hitting `shift enter`, or clicking the `Run` button at the top of the notebook.

6. Import your dataset. You'll create a Pandas dataframe by specifying the csv file with your test data. 
	- Type `df = pd.read_csv("test.csv")` in the first cell, and run this cell. 
	- This line will take some time to run, because it is loading your csv into a Pandas dataframe, and holding this dataframe in the RAM of the notebook instance.
	- You'll know the cell has competed running when the asterisk has turned into a number. 
	- You should see a pink warning bar open, as shown below. This pink bar is notifying you that your data has a variety of types. That is, you have data from the real world, and it needs to be cleaned.

[ insert the pink warning box image ]

7. Because this is a workshop, we've already gone through the work of cleaning your data for you. You'll just need to copy the cleaning script from the repository into the folder with your notebook. 

[ insert information about copying my python cleaning script into their folder ]

8. You'll have to import the file into your notebook, with `from preprocess import clean_data`. Then type `df = clean_data(df)` in another cell. This is re-assigning the variable name `df` by calling the function `clean_data()`, and passing the old `df` into the function as an argument.
	- If you want to see how we performed the cleaning, open up the Python script `preprocess.py` to follow the logic.

7. Now type `df.head()` in a new cell to see visually what some of your rows and columns look like.

### Perform Some Preliminary Analysis
1. Now that you have loaded your data into a Pandas Dataframe, and after you have successfully cleaning it with the call `clean_data(df)`, feel free to play with any of the analysis tools that are available. You can review our notebook from this morning, and copy over any analysis code that you feel is relevant. You can look through the Pandas library documentation to see other analysis suggestions. Consider this an active work session to learn about what your dataset is.

2. The purpose of performing this analysis is to make decisions about which columns (features) are relevant for building your machine learning model. If you are doing a real machine learning project, typically you can spend a lot of time in this phase. In data science communities, this phase is called feature engineering.

3. If you'd like to see our feature engineering and anaylsis, see this notebook: 

[ add in my feature analysis notebook ]

### Prepare to Build Your Model
After your team has decided which columns they want to include, or if you have decided to use all of them as a first pass at building the model, you'll need to prepare to build your model. This mean taking the following steps:

- Import the Sagemaker SDK to transform the data into Record I/O Wrapped Protobuf for Linear Learner
- Copy the data to your S3 bucket 
- Declare the containers variable that can specify the model path for each of the regions
- Copy the line about creating a Sagemaker model, by specifying the hyperparameters and then the model configuration
- Run the cell to train the model


### 


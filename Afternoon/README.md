# Competition Guidelines

Your company, **Banking On AI**, has just decided that they want to use machine learning to send targeted advertisements. You have seen some examples of using ML models to send direct mailers, but now it's your turn to build these models.

**Your mission**: Find the most customers who are likely to open a bank account via direct mail targeting. 

Your team is used to performing this analysis by hand. Previously, you would have done extensive analysis on your existing customers, determining who they are, where they live, and what they like to do with their free time. You would write a report, making a recommendation about where to find new customers like your historical ones. Finally, you would perform a similar analysis on a set of potential customers, identifying areas of overlap, and sending mailers to these customers. 

Today, you are going to use machine learning to perform the analysis. You will use a labeled data set and a machine learning algorithim to train a model, and then you will use this model to make predictions about which customer will respond to the direct mailing. Finally, you will choose to only submit a mailer to the customers with the strongest predictions.

### We recommend you consider the following workflow:
- Access the data, perform preliminary analysis, and make sure you have a clear understanding of the data attributes and labeled components.
- Load your historical data into a Sagemaker model, noting customer who have and have not opened bank accounts
- Train a Sagemaker model, noting your model's accuracy, precision and recall
- Use the model to make predictions about who is most likely to open a new bank account

We'll award the team winners who successfully predict customers who open bank accounts. We are holing back a portion of the data, the "validation set," with the labels for each of these customers. Your mission is to send us predictions for each of these customers by 4:30 pm.

Each team will need to submit their predictions in this format (csv):
	- 'row_id, classification, confidence level'

The winner will be the team who finds the most customers who will open a bank account, or who has the highest "recall" for their model. If we all find the same customers, then everybody wins.

## Learning Objectives
A full machine learning solution can take months to build out and perfect. Obviously we can't do all of that inside the scope of a single afternoon, but we can accomplish some key learning objectives:
- See a few of the steps necessary in going from messy, real-world data to that which is clean, normalized, and ready for modeling
- Think about what it means to have labeled data, and why it is important
- Train a model in Sagemaker, learning how to distribute that data over multiple instances
- Send predictions against the model, to understand what it means to submit a prediction and get a result back.

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





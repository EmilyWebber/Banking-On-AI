# Competition Guidelines

Your company, **Banking On AI**, has just decided that they want to use machine learning to send targeted advertisements. You have seen some examples of using ML models to send direct mailers, but now it's your turn to build these models.

**Your mission**: Find the most customers who are likely to open a bank account via direct mail targeting. 

Your company is used to performing this analysis by hand. Previously, you would have done extensive analysis on your existing customers, determining who they are, where they live, and what they like to do with their free time. You would write a report, making a recommendation about where to find new customers like your historical ones. Finally, you would perform a similar analysis on a set of potential customers, identifying areas of overlap, and sending mailers to these customers. 

Today, you are going to use machine learning to find the new customers. You will use a labeled data set and a machine learning algorithim to train a model, and then you will use this model to make predictions about which customer will respond to the direct mailing. Finally, you will choose to only submit a mailer to the customers with the strongest predictions.

### Your team is ahead of the game!
Your team is in luck! You've already spent some time building a direct mailing model in Python, so you are familiar with the workflow. However, this time the data set is larger. You have more rows to train your model with, which means you will want to distribute your analysis over multiple instances.

### Learning how to distribute your training jobs
First, we recommend opening up the **data_distribution_types.ipynb** notebook to familarize yourself with the various ways of distributing data with Amazon Sagemaker.

### Create your own notebook
Next, we'll ask you to create a new notebook. You'll download the larger dataset, and use examples from both the xgboost direct mailing example from this morning and the data distribution notebook to create your own model. 

Download the data with these lines:
`!wget https://archive.ics.uci.edu/ml/machine-learning-databases/00222/bank.zip
!unzip bank.zip`

[ insert image from downloading the new data]

## Your Submission
By 4:30 today, we'd like to see your new notebook. You can submit it here:

[ insert a link to my s3 bucket ]

You'll be scored by the following guidelines:
- The largest number of buying customers identified (recall)
- The least amount of time to build a model
- The fastest submissions
- Great analysis

## Learning Objectives
A full machine learning solution can take months to build out and perfect. Obviously we can't do all of that inside the scope of a single afternoon, but we can accomplish some key learning objectives:
- See a few of the steps necessary in going from messy, real-world data to that which is clean, normalized, and ready for modeling
- Think about what it means to have labeled data, and why it is important
- Train a model in Sagemaker, learning how to distribute that data over multiple instances
- Send predictions against the model, to understand what it means to submit a prediction and get a result back.

Now click on **Getting Started** and you're ready to start modeling!

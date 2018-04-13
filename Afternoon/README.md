# Competition Guidelines

Your company, **Banking On AI**, has just decided that they want to use machine learning to send targeted advertisements. You have seen some examples of using ML models to send direct mailers, but now it's your turn to build these models.

**Your mission**: Find the most customers who are likely to open a bank account via direct mail targeting. 

You have two ways of doing this:

(1) Classic method: Analysis
- Perform analysis on existing customers who have bank accounts. Determine who they are, where they live, and what they like to do with their free time. 
- Then write a report, where you make a recommendation about these customers.
- Look through your new list of customers, analyze them, and determine who meets that crieria.
- Lastly, send out the mailers.
Upside: all of the analysis is in your hands, it's a workflow you're very comfortable with.
Downside: might be slow, and is prone to human bias.

(2) Machine Learning
- Load your historical data into a Sagemaker model, noting customer who have and have not opened bank accounts
- Train a Sagemaker model, noting your model's accuracy, precision and recall
- Use the model to make predictions about who is most likely to open a new bank account

We'll award the team winners who successfully predict customers who open bank accounts. We are holing back a portion of the data, the "validation set," with the labels for each of these customers. Your mission is to send us predictions for each of these customers by 4:30 pm.

Each team will need to submit their predictions in this format (csv):
	- row_id, classification, confidence level

The winner here will be the team who finds the most customers who will open a bank account, or who has the highest "recall" for their model.

## Learning Objectives
A full machine learning solution can take months to build out and perfect. Obviously we can't do all of that inside the scope of a single afternoon, but we can accomplish some key learning objectives:
- See a few of the steps necessary in going from messy, real-world data to that which is clean, normalized, and ready for modeling
- Break the data into X and Y, think about what that means and why it is important
- Train a model in Sagemaker, learning how to distribute that data over multiple instances
- Send predictions against the model, to understand what it means to submit a prediction and get a result back.

## Note
Check back here for answers as the afternoon progresses. I will release the solutions so no one in the workshop is left without the tools they need to suceede. 

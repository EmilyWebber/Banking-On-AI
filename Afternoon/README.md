# Competition Guidelines

Competition Guidelines:  

	- Your company, "Banking On AI," has just decided that they want to use machine learning to send targeted advertisements. You have seen some examples of using ML models to send direct mailers, but now it's your turn to build these models.

	Your mission: find the most customers who are likely to open a bank account via direct mail targeting. 

	You have two ways of doing this:

	(A) 
	- Classic method: perform analysis on existing customers who have bank accounts. Determine who they are, where they live, and what they like to do with their free time. 
	- Then write a report, where you make a recommendation about these customers.
	- Look through your new list of customers, analyze them, and determine who meets that crieria.
	- Lastly, send out the mailers.
	Upside: all of the analysis is in your hands, it's a workflow you're very comfortable with.
	Downside: might be slow, and is prone to human bias.

	(B) 
	- Load your historical data into a Sagemaker model, noting customer who have and have not opened bank accounts
	- Train a Sagemaker model, noting your model's accuracy, precision and recall
	- Use the model to make predictions about who is most likely to open a new bank account

We'll award the team winners who successfully predict customers who open bank accounts. We are holing back a portion of the data, the "validation set," with the labels for each of these customers. Your mission is to send us predictions for each of these customers by 4:30 pm.

I need the submission in this format (csv):
	- row_id, classification, confidence level

I have a script that will read through these submissions

The winner here will be the team who finds the most customers who will open a bank account, or who has the highest "recall" for their model.

Note: check back here for answers as the afternoon progresses. I'm setting a timer for myself, and hoping that you all can accomplish what I've done before I release the answers. If not, 

Obviously this is going to be a much more simplified version, because it's not really possible to build a production machine learning system inside of 4 hours. 

TRY just using the notebook from this morning:
	- how far does it get you?
	- how much do you have to modify?
	- What if you want to try a different algorithim?
	- What if you want to use a different set of features? 

Learning Objectives:

	- I want to give them cleaned data, which I should already have from running through the Kaggle repo script
	- I want them to break it into X and Y, so they learn how to think about that and what it means
	- I want them to train a model, and know how to distribute that model over multiple instances
	- I want them to send predictions against that model, to understand what it means to submit a prediction and get a result back

What about submission results?
	- I will have my own validation data. Notice how it DOES NOT a Y label. That is because you will use the ML model to PREDICT a Y for each document in the row. 
	- Each team

If you are interested, here is a very nice solution to this example, but I don't expect you to use this.

	- But I CAN pull from this to

		(1) just clean the data and rewrite it
		(2) put it into sagemaker
		(3) distribute it over 3 instances for training, see how quickly we can train it, what if we distribute it over only 2 instances?
		(4) send predictions against it

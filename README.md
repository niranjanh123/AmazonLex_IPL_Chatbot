# AmazonLex_IPL_Chatbot
Chatbot Creation using Amazon Lex, Lambda and DynamoDb

Amazon Lex :
It’s a service that allows users to create a user interface which allows them to interact via text or speech.
It Provides support for Natural Language Processing(NPL) and Automatic Speech Recognition(ASR).
For more information use this link: 
https://docs.aws.amazon.com/lex/latest/dg/what-is.html

Lambda:
Lambda is a serverless solution that provides you with compute options as and when you need them without having to setup the underlying infrastructure.
To get more information use this Link: https://docs.aws.amazon.com/lambda/latest/dg/welcome.html

DynamoDB:
It’s a NoSQL database which helps you to easily setup a Database in just a few clicks.
To get more information use this link: 
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html

Feature of IPL Chatbot:
1.	You have the option to view all the teams 
2.	You have the option to view a specific team based on its ID
3.	You have the option to delete a team by specifying its ID

Steps to implement the IPL chatbot app:
1.	 Create a Dynamo DB table
a.	Click on the Create table option.
b.	Enter table name
c.	Enter Partition Key(Required), Selection key is optional
d.	Click on the table name and select explore table items
e.	Click on the Create item option which as at the bottom and now you should be able the table item.


2.	Create a Lambda function:
a.	Click on the create function option under Lambda service.
b.	Select Author from scratch as the template as you will be adding a custom function.
c.	Provide the function name.
d.	Select Python as the Runtime option.
e.	Click on the create function option.

Before you work on the code section, it’s necessary to provide access to Dynamo DB
a.	Select the Configuration tab->permissions
b.	Select the Role name.
c.	The IAM will open up and you should be able to add the new permissions by selecting Add Permission option and select attach policies.
d.	In the search bar you can search for Dynamodb and you should be able to select “AmazonDynamoDbFullAccess”.
Note: Always provide only necessary permission for any role to follow the principle of least privilege.

Also, you will have to change the timeout from 3 seconds (default) to maybe 10 seconds as it takes more than 3 seconds for the execution of the function.
a.	Select the Configuration tab->General Configuration
b.	Click on the edit option and change the timeout option as per your needs.

       Paste the Lambda function from the file name “Lamda code for Lex Integration”
        Deploy and create a new version.

3.	Creation of Chatbot using Lex:
Create a new Bot
a.	Create a blank bot.
b.	Provide bot name.
c.	Select a new role option for Lex.
d.	You can select the No option under COPPA.
e.	The rest of the settings can be left as it is and you can create the bot.
 
Create Intents as per your requirement:
a.	Click on Add Intent and add the name of your Intent.
b.	You can provide the intent utterances (all the words or phrases that will trigger this intent).
c.	You can add slots in case you need to take inputs from users.
d.	You can opt for the Confirmation section which will ask the user if they want to proceed with the intent or cancel the operation.
e.	Fulfillment section is where you need to integrate your Lambda function. You can do that by selecting advanced options and checking the option “Use a Lambda function for fulfillment”.


4.	Testing the Bot
a.	Once all the intents are created you need to Build the Intents.
b.	Once the build is successful you can now test the Bot by selecting the Test option
c.	You will have to attach the Lambda function to test the chatbot. You can do that by selecting the Setting option and selecting the Lambda function and its version.
d.	You can now test the Chabot by interacting with it.
e.	To get more details on the flow you can either inspect option or use the Cloudwatch option for Lambda.

For any doubts feel free to reach out to me on niranjanhari123@gmail.com
Feel free to play around and would be happy to collaborate.

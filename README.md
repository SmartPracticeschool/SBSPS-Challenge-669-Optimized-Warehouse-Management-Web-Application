# SBSPS-Challenge-669-Optimized-Warehouse-Management-Web-Application
A Machine Learning Model Hosted on a Web Application to predict the future orders, 10 weeks in advance, of a food delivery service.
Invoking the developer's liberty, I named the hypothetical food delivery service as The Czar's.

# Uniqueness quotient:
1. A dataset containing the desired target, i.e. Number of orders, along with other independent attributes, such as meal id, center id,
week number, checkout price, base price, email marketing and homepage marketing, is obtained from Kaggle.
2. The Machine learning model, set up after proper pipeline selection, is used to predict the number of orders for subsequent 10 weeks,
given a set of relevant data such as meal id, centre id, etc.
3. A news feed widget is made available for the user to scroll through Global news in general and food related news and recipies in
particular.
4. A youtube widget to show some food videos, to keep the user engaged.
5. A Meal ID & Center ID info excel sheet, both hosted live on Google sheets platform, embedded in the ABOUT Tab of the Web Application.
The purpose of these sheets is to provide the user with useful data, which otherwise will be too cumbersome to remember.
6. An interactive Chat bot, known as The Czar bot, is present for the sole purpose of assistance to the user. Apart from business related
information, The Czar bot is also receptive of both positive and negative feedback, and is designed keeping in mind the importance of the
mental health and well being of the users.
7. An interactive Dashboard hosted within the Web Application, will provide a better understanding about the relation between the target
attribute and the independent attributes.
   7.1 The Basic interpretation tab is for the user to begin to understand the nature of the dependencies.
   7.2 The Advanced interpretation is for a user who has already developed an understanding for the aforesaid dataset.
8. The Colour combination and backgroung image selection has been done keeping in mind the general reception of an individual along with
an effort at being soothing to the eyes.

# Problem Statement:
A food delivery service has to deal with a lot of perishable raw materials which makes it all, the most important factor for such a
company is to accurately forecast daily and weekly demand. Too much inventory in the warehouse means more risk of wastage, and not
enough could lead to out-of-stocks - and push customers to seek solutions from your competitors. The replenishment of majority of raw
materials is done on weekly basis and since the raw material is perishable, the procurement planning is of utmost importance.
Therefore, developing a Machine Learning Model to predict the demand of goods for the next 10 weeks or in the future Mobile / 
Web Application to Interact with the ML Model deployed on IBM Cloud, will surely do wonders in reducing the wastage during procurements.

# Proposed Solution:
According to the UN's Food and Agricultural Organization, a massive one third of the total amount of food produced globally is wasted, 
which is worth over $750 billion. India currently ranks 7th in terms of overall food wastage. Thus, pre predicted number of orders would 
significantly reduce the wastage during procurement.
The software solution to the problem solution being:
•	IBM Watson Machine Learning instance: Helps predict the desired number of orders as per the changing independent variables, using algorithms. 
Connected through REST APIs and storing metadata in Cloudant DB.
•	News feed: Using iframe source code to embed e-newspaper in the Web Application. It helps the user get a better understanding of the food world.
•	Youtube Videos: Keeps the user interested in the Web App through colourful display of vibrant food items.
•	IBM Watson Cognos Embed: Connected through shareable preview link, this creates and hosts a live interactive dashboard, using uploaded datasets,
enhances the understanding of the user.
•	IBM Watson Assistant: Connected through REST APIs, this helps create and host Chat bots in Web App.
•	NODE RED: Visual Flow editor, used to host the Web Application.

# Architechture of the Web Application:

<image src="Web Application/Web App architecture.png">

# Technology Stack used:

o	IBM Watson Studio Machine Learning instance:
1.	Server type: REST
2.	Programming Language: Python
3.	App: Jupyter Notebook
4.	Hosted: NODE RED
5.	Database: Cloudant DB
6.	API Endpoints: Mentioned in service credentials

o	IBM Watson Assistant:
1.	Server type: REST
2.	Programming Language: Python
3.	App: Chat Bot
4.	Hosted: NODE RED
5.	Database: Cloudant DB
6. Algorithms used: Fuzzy logic, Natural Language Processing, Speech Processing.
6.	API Endpoints: Mentioned in service credentials

o	IBM Watson-Cognos Embed:
1.	Server type: REST
2.	Programming Language: Python
3.	App: Dashboard
4.	Hosted: NODE RED
5.	Database: Cloudant DB
6.	API Endpoints: Mentioned in service credentials

o	NODE RED:
1.	Server type: NodeJS Project (Web-APP + REST Server)
2.	Programming Language: Python, HTML, PHP, CSS, Javascript.
3.	App: NODE RED
4.	Database: Cloudant DB

# Implementation Details:

### Module 1: IBM Watson Studio Machine Learning Instance:


#### Creation:

The Machine Learning model is the heart of our project, since the central idea of predicting the number of orders and thereby reducing
the wastage will be computed by the Machine Learning Model.
Therefore, the model has be fitted with a dataset, and different pipelines have to be tested in order to select the best pipeline.
The best pipeline being that which has the maximum accuracy, in our case, the maximum accuracy being that of 76.2% 

#### Hosting:

After selecting the desired Machine Learning Model, the next step is to host it in the Web Application. This process is accomplished 
through the NODE RED flow editor, using various nodes such as,
Form node.	http in node.	http request node.	Function node.	Debug node.	 Template node.
After the successful configuration of the aforementioned nodes in a required manner, the flow needs to be deployed in order to see the 
web app in action.

#### Process flow:

The user feeds the User interface input option with essential data so as to get the requisite number of orders for subsequent 10 weeks 
and the given week. After the data is filled and submitted, the data is fed to the Model, using NODE RED API Connections and the 
subsequent output generated is displayed in the UI of the web app.

<image src="Machine Learning Model/ML Model Working-1.png">
<image src="Testing/ML 1.1-1.png">
<image src="Testing/ML 1.2-1.png">

### Module 2: IBM Watson Assistant:

#### Objective:

For the user to have a better experience while using the Web Application, inclusion of an interactive chat bot was crucial. The Chat bot
not only helps the user get a better experience through inputs of business related data, but it also gives feedback to the user and 
itself acknowledges feedback, shares jokes and is appreciative of human interaction, since, our goal has also been to promote mental 
health.

#### Creation:

The Watson Assistant Skill section has intents to analyze user input sentences, entities to analyze user input key words and dialogs, 
to reciprocate an output.
It all depends upon an individual, as to how and where to drive the anticipated conversation, using fuzzy logic, NLP and SP.

#### Hosting:

The Czar bot is hosted using APIs entered in the NODE RED flow, containing the Chat bot Node, along with a variety of function, template
and audio nodes, and a form node.

#### Process Flow:

As the user submits the enquiry through the user interface on the chat bot widget in the Web App, the NODE RED sends the enquiry to the
Chat bot and reverts back with a prompt reply along with an audio reply of the same.

<image src="IBM-Assistant-Chatbot/Chatbot Working Depiction-1.png">
<image src="Testing/The Czar bot test 1.1-1.png">
<image src="Testing/The Czar bot test 1.3-1.png">

### Module 3: IBM Watson Cognos Embed:

#### Creation:
A live interactive dashboard is created for the user to get a better understanding of the dataset. The dataset used to create the 
Machine Learning model, is uploaded to the dashboard and subsequent charts and flows, depicting the relation between the target attribute
to the independent attributes, are designed and implemented.

There are two parts to the dashboard,

o	The Basic interpretation tab is for the user to begin to understand the nature of the dependencies.
o	The Advanced interpretation is for a user who has already developed an understanding for the aforesaid dataset. 
#### Hosting:
The NODE RED Template node, along with the shareable preview link of the Cognos dashboard is used to embed the dashboard into the Web Application.

### Module 4: Web App: User Interface:


#### Our Motivation:

This section contains an article depiction from a popular and trusted newspaper, used to solidify the user’s knowledge base and thereby
get a better understanding of the business in general and our objective in particular.

#### Essential info:

Used to feed the user with essential data that he might need for computation of the predictions using the ML model, which otherwise would’ve
been cumbersome to memorize.

#### News feed:

Provides a daily dosage of Global news in general and food related news and recipes in  particular.

#### Youtube Video:

Used for users who don’t read much news and are more drawn towards audio visual representation.








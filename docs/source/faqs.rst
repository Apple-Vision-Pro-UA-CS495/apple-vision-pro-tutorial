FAQs
=======================

| **Question: Can I change the model being ran?**
| **Answer:** 
| From the app, no you cannot change which model is used, but in general yes. To change the model, change the model name in the server.py file and upload the update server.py to the EC2 instance. Then start the server with updated code and the new model will be used. Alternatively copy the server.py file and change the model name then upload the newfile to the EC2 instance then you can change which model is used simply by choosing which program to run when starting server. 

| **Question: I tried using the app but the picture is not getting feedback, how can I fix this?**
| **Answer:** 
| Dr. Crawford has requested that the EC2 instance remain stopped unless being used to reduce cost. In order to receive feedback you will have to start up the server which communicates with the models.

| **Question: The speech function says it cannot see what my image, why is this?**
| **Answer:** 
| The program offers speech functionality as well as image analysis through Hugging Face models to act as assistants to the user. These two features, however, are seperate so asking one to access the
| other is not viable.

| **Question: Why is the model saying the image is something it is not?**  
| **Answer:**
| The Google Vision Transform (ViT) model, while thorough, does not contain classes for all objects, furthermore it adjusts poorly to background noise. However, the model performance is not important as the goal of this project was to make an application allowing the Apple Vision Pro to run machine learning models through the use of cloud computing. If you are trying to get more accurate readings of images         specifically, it may be a good idea to find another image classification model that fits your needs better and update the server.py code like described in Question 1.


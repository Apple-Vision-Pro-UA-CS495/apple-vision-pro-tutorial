FAQs
=======================

Q: Can I change the model being ran?
A: From the app, no you cannot change which model is used, but in general yes. To change the model, change the model name in the server.py file and upload the update server.py to the EC2 instance. Then start server with updated code and the new model will be used. Alternatively copy the server.py file and change the model name then upload the newfile to the EC2 instance then you can change which model is used simply by choosing which program to run when starting server.

Q: I tried using the app but the picture are not getting feedback, how can I fix this?
A: Dr. Crawford has requested that the EC2 instance remain stopped unless being used to reduce cost. In order, to receive feedback you will have to start up the server which communicates to the models.

Q: The speech function says it cannot see what my image, why is this?
A: The program offers speech functionality as well as image analysis through Hugging Face models to act as assitants to the user. These two features, however, are seperate so asking one to access the other is not viable. 

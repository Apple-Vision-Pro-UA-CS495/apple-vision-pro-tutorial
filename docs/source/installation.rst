.. _installation:

Installation
=======================

Requirements
------------

To develop a visionOS app, you would need: 

- A Mac with Apple silicon chip  
- Xcode 15.0+  
- The visionOS Simulator  

Install Xcode and visionOS Simulator
------------------------------------

#. To install Xcode, open App Store on your Mac and search for ``"Xcode"``. Then, click on the ``"Get"`` button to download it.

#. Once Xcode is installed, launch Xcode and a dialog will appear to show which simulator runtime you may install.  
   Select ``"visionOS"`` with the most current version and click the ``"Download & Install"`` button.

   .. image:: /Xcode.png
      :width: 400
      :alt: Xcode and visionOS Simulator Installation

Install visionOS App: Discover
------------------------------

#. Open the ``"Terminal"`` on your Mac and navigate to a directory where you want the visionOS app to be.

#. Clone the Repository:

   .. code-block:: console

      git clone https://github.com/Apple-Vision-Pro-UA-CS495/apple-vision-pro-main.git

Install the Dependency in the visionOS App
------------------------------------------

#. Add the Lottie Library to the app

   - Copy this link: https://github.com/airbnb/lottie-spm  
   - Follow this GIF to add the dependency

     .. image:: /_static/gifs/Add_Dependency.gif
        :width: 800
        :alt: Add Dependency

Run the visionOS app
--------------------

#. Start the AWS EC2 Instance

   .. image:: /_static/gifs/Start_Instance.gif
      :width: 800
      :alt: Start the AWS EC2 Instance GIFs

#. Start the server

   - For Windows, run this command in the terminal:

     .. code-block:: console

        ssh -i {path_to_pem_file}\aws_pem.pem ec2-user@{IP_address} 
        cd app
        uvicorn server:app --host 0.0.0.0 --port 8000

   - For Mac, run this command in the terminal:

     .. code-block:: console

        ssh -i {path_to_pem_file}/aws_pem.pem ec2-user@{IP_address} 
        cd app
        uvicorn server:app --host 0.0.0.0 --port 8000

     .. image:: /_static/gifs/Start_Server.gif
        :width: 800
        :alt: Start the server GIF

#. Start visionOS app

   - Open ``"Discover.xcodeproj"`` in Xcode

     .. image:: /_static/gifs/Discover.xcodeproj.png
        :width: 800
        :alt: Discover.xcodeproj file

   - Make sure the OpenAI API Key is in the Scheme. If it is not, then add the API Key

     .. image:: /_static/gifs/Add_OpenAI_Key.gif
        :width: 800
        :alt: Add the OpenAI Key

   - Select visionOS simulator as the target device  
   - Press Cmd + R or click the Run button in Xcode to build and run

     .. image:: /_static/gifs/Start_App.gif
        :width: 800
        :alt: Start the visionOS app GIF

#. When you are done, make sure to stop the server and stop the EC2 instance to save money

Backend Setup Guide
-------------------

This section provides a guide for when you want to create a new EC2 Instance and get it up and running.

Local Setup
-----------

#. Create Python virtual environment  
#. Install dependencies  
#. Use this command to run the server:

   .. code-block:: console

      uvicorn server:app --host 0.0.0.0 --port 8000 --reload

#. Run the ``client.py`` file to test

EC2 Setup
---------

#. Create an EC2 instance in AWS

   - Recommend using t2.xlarge due to dependency size  
   - Set a static IP address  
   - Allow inbound traffic to ports 8000, 22, and 443

#. Start EC2 instance in AWS

#. In terminal run:

   - For Windows:

     .. code-block:: console

        ssh -i {path_to_pem_file}\aws_pem.pem ec2-user@{IP_address} 

   - For Mac:

     .. code-block:: console

        ssh -i {path_to_pem_file}/aws_pem.pem ec2-user@{IP_address} 

#. Download ``server.py`` file and ``requirements.txt`` from our  
   `data processing repo <https://github.com/Apple-Vision-Pro-UA-CS495/data-processing-main/>`_

#. Move these files from local into EC2 using SCP:

   .. code-block:: console

      scp -i {path_to_pem_file}\aws_pem.pem {path_to_file}\file ec2-user@{IP_address}

#. Install dependencies in EC2 using pip:

   .. code-block:: console

      pip install -r requirements.txt

#. Run:

   .. code-block:: console

      uvicorn server:app --host 0.0.0.0 --port 8000

#. Hit server with this link: ``ws://{IP address}:8000/ws``

#. When you are done, make sure to stop the server and stop the EC2 instance to save money

#. For future use, you can just spin up the EC2 instance, ssh in, and run the uvicorn command to start the server again

#. Run tests in EC2: move ``test.py`` into EC2

   - Install pytest using pip:

     .. code-block:: console

        pip install pytest

   - Then run:

     .. code-block:: console

        pytest test.py

Installation
=====

.. _Requirements:

Requirements
------------

To develop a visionOS app, you would need: 

  * A Mac with Apple silicon chip
  * Xcode 15.0+
  * The visionOS Simulator

Install Xcode and visionOS Simulator
----------------

#. To install Xcode, open App Store on your Mac and search for ``"Xcode"``. Then, click on ``"Get"`` button to download it. 

#. Once Xcode is installed, launch the Xcode and a dialog will appear to show which simulator runtime you may install. Select ``"visionOS"`` with the most current version and click ``"Download & Install"`` button. 

.. image:: /Xcode.png
  :width: 400
  :alt: Xcode and visionOS Simulator Installtion

Install visionOS App: Discover
----------------

#. Open the ``"Terminal"`` on your Mac and navigate to a directory where you want the visionOS app to be. 

#. Clone the Repository

.. code-block:: console

   git clone https://github.com/Apple-Vision-Pro-UA-CS495/apple-vision-pro-main.git

Run the visionOS app
----------------

#. Open ``"Discover.xcodeproj"`` in Xcode

#. Select visionOS simulator as the target device

#. Press Cmd + R or click the Run button in Xcode to build and run.

Backend Setup Guide
----------------

This section provides a guide for getting the backend server up and running.

Local Setup
----------------

#. Create Python virtual environment
#. Install dependencies
#. Use this command to run the server: ``uvicorn server:app --host 0.0.0.0 --port 8000 --reload``
#. Run the client file to test

EC2 Setup
----------------

#. Create an EC2 instance in AWS
  - Recommend using t2.xlarge due to dependency size
  - Set a static IP address
  - Allow inbound traffic to port 8000, 22, and 443
#. Start EC2 instance in AWS
#. In terminal run: ``ssh -i {path_to_pem_file}\aws_pem.pem ec2-user@{IP_address}`` (This is for windows CMD)
#. Move server file and requirements.txt from local into EC2 using SCP: ``scp -i {path_to_pem_file}\aws_pem.pem {path_to_file}\file ec2-user@{IP_address}``
#. Install dependencies in EC2 using pip: ``pip install -r requirements.txt``
#. Run: ``uvicorn server:app --host 0.0.0.0 --port 8000``
#. Hit server with this link: wss://{IP address}:8000/wss
#. When you are done, make sure to stop the server and stop the EC2 instance to save money
#. For future use, can just spin up EC2 instance and ssh in and run uvicorn command to start up server again
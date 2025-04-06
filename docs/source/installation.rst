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

#. Once Xcode is installed, launch the Xcode and a dialog will appear to show which simulator runtime you may install. Select ``"visionOS"`` 
with the most current version and click ``"Download & Install"`` button. 

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

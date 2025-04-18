.. _usage:

Usage
=======================

***************
Features
***************

- Display a splash view when the app is loaded at the first time 

    .. image:: /_static/gifs/Splash_View.gif
        :width: 800
        :alt: Splash Screen

- Select an image from Photo app and send selected image to AWS EC2 instance via WebSocket. Then, receive response and display result to the Apple Vision Pro 

    .. image:: /_static/gifs/Photo_Feature.gif
        :width: 800
        :alt: Select Image and Submit Image

- Use speech-to-text to capture text from user. Then, send the text to OpenAI and display the result. 

    .. image:: /_static/gifs/SpeechRecognition.gif
        :width: 800
        :alt: Speech Recognition and OpenAI Connection

Assuming AWS EC2 instance is already running

***************
How to Use
***************

- Open the visionOS app called ``Discover`` on the Apple Vision Pro 
- Click on ``Select photo`` button to access the ``Photo`` app on the headset 
- Pick a photo and then click on ``Submit Image`` send the photo to AWS EC2 and receive response on the headset.
- Press ``Speak Now`` and ``Start Recording`` to record speech and convert to text. Select ``Send Request`` to send it to OpenAI and receive response. 

***************
Live Demo
***************

.. raw:: html

   <iframe width="640" height="360"
        src="https://www.youtube.com/embed/ihywh1OfG-Y"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen>
   </iframe>

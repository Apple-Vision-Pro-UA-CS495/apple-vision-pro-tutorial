Modification/Extension
======================

This section outlines the modifications and extensions for the app, including both front-end and back-end changes, dependencies, testing procedures, and more.

---

Modifications/Extensions for Front End
-----------------------------------

1. **Implement Main Camera Usage to Take Pictures in Real-Time**
   - Get **Apple Developer** access.
   - Create a new file for **Main Camera** code.
   - Create a new file for the **view** of the Main Camera.

2. **Have Vision Pro Read Response Back from OpenAI**
   - Use **AVSpeechSynthesizer** to have Vision Pro read aloud the response from OpenAI.

3. **Change OpenAI Model**
   - In the **Discover app** inside the **Views** file, there is a file named `OpenAIService` where you can change the model from `"gpt-4o"` to the desired OpenAI model.

4. **Change AI Model**
   - You could use other AI models like **Claude**, **Deepseek**, or **Gemini**.

5. **Get Voice and Image Selections to Work Together and Implement with PuppyPy**
   - Ensure that both the voice and image functionalities work in tandem and integrate them with the **PuppyPy** project.

---

Modifications/Extensions for Back End
--------------------------

1. **Change the Learning Model**
   - In the `data-processing-main`, the model is named `"google/vit-base-patch16-224"` in the file `server2.py`.
   - Replace the model name with the desired Hugging Face model from **Image Classification**:  
     `https://huggingface.co/models?sort=trending`

---

Dependencies
------------

1. After installing the application, the **Lottie Library** will be located in the **Package dependencies** on the left side of XCode.
2. In `data-processing-main`, there are `requirements.txt` and `requirements2.txt` for the backend.

---

Backlog
-------

- The backlog is located in our **GitHub**.
- Go to **Projects**, click on **CS 495 - Apple Vision Pro**, and the backlog will appear.

---

Style Expectations
------------------

- Any other animations should be used from the **Lottie Library** dependency downloaded.
- Follow **architecture styles**.

---

Tests
-----

1. **Front End**:
   - **Discover Tests** goes here.
   - **No framework for visionOS**, so only **logical testing** is allowed (unit testing is not supported).

2. **Back End**:
   - Open a new bash shell and run `source .venv/Scripts/activate` to activate the virtual environment.
   - Run the `test.py`

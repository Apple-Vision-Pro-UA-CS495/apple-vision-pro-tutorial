Modification / Extension
========================

Front‑End Modifications / Extensions
------------------------------------

1. **Implement Main Camera usage to take pictures in real time**

   - Obtain **Apple Developer** access.  
   - Create a file that contains the **Main Camera** code.  
   - Create a view file that presents the Main Camera output.

2. **Have Vision Pro read responses from OpenAI**

   - Use **AVSpeechSynthesizer** to speak the assistant’s reply aloud.

3. **Change the OpenAI model**

   - In the *Discover* app, open `Views/OpenAIService` and replace  
     `"gpt-4o"` with the desired model name.

4. **Use a different AI provider**

   - Possible alternatives: **Claude**, **DeepSeek**, **Gemini**, …  

5. **Combine voice and image pipelines, then integrate with PuppyPy**

   - Make sure voice‑originating queries and image selections work together.

Back‑End Modifications / Extensions
-----------------------------------

1. **Replace the image‑classification model**

   - File: `data-processing-main/server2.py`  
     Current model → `"google/vit-base-patch16-224"`
   - Pick any Hugging Face *image‑classification* model:  
     https://huggingface.co/models?sort=trending  
   - Change the string and restart the server.

Dependencies
------------

1. After installing the app, the **Lottie** library appears under  
   *Package Dependencies* in Xcode.

2. Back‑end Python packages are listed in  
   `data-processing-main/requirements.txt` and `requirements2.txt`.

Backlog
-------

The backlog is maintained in **GitHub Projects**:

*Navigate → Projects → **CS 495 – Apple Vision Pro***.

Style Expectations
------------------

* Use only animations that ship with the **Lottie** dependency.  
* Follow the project’s architecture / coding‑style guidelines.

Tests
-----

### Front end

VisionOS currently has **no unit‑test framework**; perform logic / manual testing only.

### Back end

Activate the virtual environment and run `pytest`:

.. code-block:: console

   $ source .venv/Scripts/activate
   $ pytest test.py -v

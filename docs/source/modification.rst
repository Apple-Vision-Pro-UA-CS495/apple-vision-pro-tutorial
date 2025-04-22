Modification / Extension
========================

Front‑End Modifications / Extensions
------------------------------------

1. **Implement Main Camera usage to take pictures in real time**

   - Obtain **Apple Developer** access.  
   - Create the file that contains the **Main Camera** code.  
   - Create the SwiftUI view that presents the Main Camera output.

2. **Have Vision Pro read responses from OpenAI**

   - Use **AVSpeechSynthesizer** to speak the assistant’s reply aloud.

3. **Change the OpenAI model**

   - In *Discover* ▸ `Views/OpenAIService`, replace `"gpt-4o"` with the desired
     model name.

4. **Use a different AI provider**

   - Possible alternatives: **Claude**, **DeepSeek**, **Gemini**, …

5. **Combine voice and image pipelines, then integrate with PuppyPy**

   - Make sure voice‑originating queries and image selections work together.

Back‑End Modifications / Extensions
-----------------------------------

1. **Replace the image‑classification model**

   - File: `data-processing-main/server2.py`  
     Current model: ``"google/vit-base-patch16-224"``
   - Pick any Hugging Face *image‑classification* model:  
     https://huggingface.co/models?sort=trending  
   - Change the string and restart the server.

Dependencies
------------

- After installing the app, the **Lottie** library appears under *Package Dependencies* in Xcode.  
- Backend Python packages are listed in
  `data-processing-main/requirements.txt` and `requirements2.txt`.

Backlog
-------

The backlog lives in **GitHub Projects**  
(*Projects ▸ CS 495 – Apple Vision Pro*).

Style Expectations
------------------

- Use only animations that ship with the **Lottie** dependency.  
- Follow the project’s architecture / coding‑style guidelines.

Tests
-----

### Front end

VisionOS currently has **no unit‑test framework**; perform logic / manual testing only.

### Back end

.. code-block:: console

   # activate venv
   source .venv/Scripts/activate
   # run tests
   pytest test.py -v

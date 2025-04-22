Modification / Extension
========================

Front‑End Modifications / Extensions
------------------------------------

1. **Implement Main‑Camera capture in real time**

   - Obtain an **Apple Developer** account.
   - Add a Swift file that contains the Main‑Camera code.
   - Add a SwiftUI view that presents the Main Camera output.

2. **Have Vision Pro read OpenAI responses aloud**

   - Use **AVSpeechSynthesizer** to speak the assistant’s reply.

3. **Change the OpenAI model**

   - In *Discover* ▸ `Views/OpenAIService` replace the string
     ``"gpt-4o"`` with the desired model name.

4. **Use a different AI provider**

   - Possible alternatives: **Claude**, **DeepSeek**, **Gemini**.

5. **Combine voice + image pipelines and integrate with PuppyPy**

   - Ensure the two features work together before linking them to PuppyPy.

Back‑End Modifications / Extensions
-----------------------------------

1. **Replace the image‑classification model**

   - File: `data-processing-main/server2.py`  
     Current model: ``"google/vit-base-patch16-224"``
   - Pick a Hugging Face image‑classification model:  
     <https://huggingface.co/models?sort=trending>
   - Change the string and restart the server.

Dependencies
------------

- After installing the app, the **Lottie** library appears under
  *Package Dependencies* in Xcode.
- Backend packages are listed in
  `data-processing-main/requirements.txt` and `requirements2.txt`.

Backlog
-------

The backlog is on **GitHub Projects** → *CS 495 – Apple Vision Pro*.

Style Expectations
------------------

- Use only the animations that ship with the **Lottie** dependency.
- Follow the project’s architecture / coding‑style rules.

Tests
-----

### Front end

VisionOS has **no unit‑test framework**; perform manual / logic tests only.

### Back end

.. code-block:: console

   # activate venv
   source .venv/Scripts/activate
   # run tests
   pytest test.py -v

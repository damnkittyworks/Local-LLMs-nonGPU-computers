# Running llama.cpp on an Intel Mac

---
**Things to Know**
* This guide details how to download and use a pre-built llama.cpp binary for macOS along with a 7B weight model on an Intel Mac.
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creeator of llama.cpp, they can be found at this website: https://github.com/ggerganov/llama.cpp
* Device used: 2018 MacBook Pro, 2.3 GHZ Quad-Code Inter Core i5, 8GB RAM, macOS 14.3.1
* Dependencies: Aside from the downloading the binary and the model, no extra installs are needed.
---
## Download and Set Up
1. On the Mac, open the Home folder by using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>H</kbd>. 
2. Inside the Home folder, create a new folder and name it “llama.cpp”. Create another new folder and name it “Models.”

    <img width="728" alt="Intel-Mac-Create-Folders-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/44075f5f-daac-4269-9e1f-de32da6ef98e">

3. Open a web browser and go to the following webpage: https://github.com/ggerganov/llama.cpp/releases
4. On the webpage, download the latest llama-b1-bin-macos-x64.zip file. The b2589 release was the latest version when I downloaded it.

    <img width="730" alt="Intel-Mac-Download-llamacpp-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/51bbba5f-10bc-40be-8352-01cce474a079">

5. Extract the zip. Open the build folder, then open the bin subfolder. Select all the files and move them into the newly created “llama.cpp” folder in the Home folder.

    <img width="730" alt="Intel-Mac-Move-llamacpp-Files-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/25a7137a-9220-4679-9def-1c81e333dc37">

6. Go to the following webpage: https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.2-GGUF
7. Search for the Q4_K_M model and download it.

    <img width="730" alt="Mistral-7B-HF-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/bbfbcdf9-377f-4284-ad04-a3b7b1ae32ec">

8. Move the downloaded Q4_K_M model from the Downloads folder into the newly created “Models” folder in the Home folder.

    <img width="730" alt="Intel-Mac-Move-Model-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/0bcff990-d054-4b50-a250-66a38e2103be">

9. Open the Spotlight search by using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Spacebar</kbd>.
10. Type “Terminal” and click it to launch the application.
    <img width="601" alt="Intel-Mac-Spotlight-Terminal-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/3e1a2061-efc7-4e11-834d-8e637ab81cb5">

11. In the Terminal window, paste the following command and press the return key: `cd llama.cpp`
    
    <img width="595" alt="Intel-Mac-cd1_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/2b7da531-aa9c-4523-9bdf-930fbf4bbbea">

12. Next, paste the following command and press return: `./server -m ~/Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf -ngl 0`
    
    <img width="595" alt="Intel-Mac-cd2_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/68b992f8-04a9-4ebf-bf24-a580953ec3a4">

    1. If a "server cannot be opened" message is displayed, click Cancel:
      <img width="266" alt="Intel-Mac-Server-Popup1-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/9b0268df-1494-4cf3-b466-426b09ace95d">
       
    2. Open the System Settings and choose Privacy & Security.
    3. Scroll down to the Security section.
    4. Click "Allow Anyway".
     <img width="719" alt="Intel-Mac-Allow-Anyway-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/d611845d-f9cc-4c0c-a2f1-11e8cb3ca72f">
          
    5. Bring forward the Terminal window. Paste the following command and press return: `./server -m ~/Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf -ngl 0`.
    6. Another popup will appear. Click Open.
      <img width="266" alt="Intel-Mac-Server-Popup2-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/92e1ff8d-e186-4c3c-a262-5669cf38a51c">

13. Wait about 15 seconds until the terminal window shows text that reads “all slots are idle”.

    <img width="590" alt="Intel-Mac-all-slots-idle-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/91452518-c314-4ee2-a71a-c08b66f21d5f">


14. Open a web browser and enter this localhost address: http://127.0.0.1:8080. The page displays the interface for chatting with the model.

    <img width="842" alt="Intel-Mac-Chat" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/9c5ef262-cd3c-4928-9ebf-8ff4ad97cf59">

15. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llama.cpp again in the future
The next time you want to run llama.cpp, just follow these steps:
1. Open the Terminal application.
2. In the Terminal window, paste the following command and press the return key: `cd llama.cpp` 
3. Next, paste the following command and press return: `./server -m ~/Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf -ngl 0`
4. Open a web browser and enter this localhost address: http://127.0.0.1:8080
5. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

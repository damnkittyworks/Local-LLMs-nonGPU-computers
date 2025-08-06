# Running llama.cpp on Linux Mint
** IMPORTANT - August 2025 - these instructions are outdated! I will update this page in the next couple of weeks. **
---
**Things to Know**
* This guide details how to download and use llama.cpp with a 8B model on a Intel i7 laptop with 8 GB RAM and Linux Mint.
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llama.cpp, they can be found at this website: https://github.com/ggerganov/llama.cpp
* Devices tested: HP 15-ac121dx, i3-5010U, 8GB RAM, Linux Mint 21.3 Cinnamon (fresh install)
* Dependencies: Aside from the downloading the Ubuntu binary and the model, no extra installs are needed
---
## Download and Set Up
1. On the laptop, open the Home folder by using the keyboard shortcut <kbd>Super</kbd> + <kbd>E</kbd>. Alternatively, click on the Files icon in the lower left corner of the screen. 
2. Inside the Home folder, create a new folder and name it “llama.cpp”. Create another new folder and name it “Models.”

    ![linux-L37B_create-folders](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/3a208109-3b53-46d3-b521-73959823cf69)

    
3. Open a web browser and go to the following webpage: https://github.com/ggerganov/llama.cpp/releases
4. On the webpage, download the latest Ubuntu binary.

    
    ![linux-L37B_download-cpp](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/60a1a6bb-ed15-485e-84a5-c72a89991874)


5. Extract the zip. Select all the files and move them into the newly created “llama.cpp” folder in the user directory.

     ![linux-L37B_move-cpp](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/b9c04502-287b-4b28-8008-95e2265ac2bc)


6. Go to the following webpage: https://huggingface.co/bartowski/Meta-Llama-3-8B-Instruct-GGUF/tree/main
7. Search for the Q4_K_M model and download it.

    ![linux-L37B_download-L38B](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/f2ee2820-4ea5-4de9-a958-e9e0df5f91fa)



8. Move the downloaded Q4_K_M model from the Downloads folder into the newly created “Models” folder in the user directory.

    
    ![linux-L37B_move-gguf](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/219e7a2a-d26e-4b3b-bfa2-d1f598b88a08)



9. Launch the Terminal application using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.
    

10. In the termnal window, paste the following command and press the return key: `cd llama.cpp`
    
    ![linux-L37B_cd-llamacpp](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/8ebd4f17-c429-407c-a1ea-6d9de39fdc87)



11. Next, paste the following command and press return: `./server -m ../Models/Meta-Llama-3-8B-Instruct-Q4_K_M.gguf`
    
     ![linux-L37B_cd-models](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/3a3b00a4-f16a-4ebc-a75a-5ecf14b6982e)




12. Wait a few seconds until the terminal window shows text that reads “all slots are idle”.

    
    ![linux-L37B_idle](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/4a5cb805-a8de-4e97-a071-6565870fc038)



13. Open a web browser and enter this localhost address: http://127.0.0.1:8080. The page displays the interface for chatting with the model.
14. Type a message into the field at the bottom of the window. Click Send.

    
    ![linux-L37B_chatwindow](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/226c0f5d-cf4e-40b2-9862-ca2daf28af32)


15. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llama.cpp again in the future
The next time you want to run llama.cpp, just follow these steps:
1. Launch the Terminal application.
2. In the terminal window, paste the following command and press the return key: `cd llama.cpp` 
3. Next, paste the following command and press return: `./server -m ../Models/Meta-Llama-3-8B-Instruct-Q4_K_M.gguf`
4. Open a web browser and enter this localhost address: http://127.0.0.1:8080
5. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

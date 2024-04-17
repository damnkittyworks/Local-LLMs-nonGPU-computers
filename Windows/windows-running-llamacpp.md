# Running llama.cpp on Windows 10/11
---
**Things to Know**
* This guide details how to download and use llamafile with a 7B model on a Windows 10 or 11 computer with 16 GB RAM. (<s>I do not know if laptops with only 8 GB RAM will be able to run the 7B model. You might need to download a smaller model such as Phi-2.</s> I've tested the instructions on an Intel Core i3 8GB RAM laptop. In my opinion, the speed is okay for chatting purposes, ~1.5 tk/s. It's like watching someone type slowly.)
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llama.cpp, they can be found at this website: https://github.com/ggerganov/llama.cpp
* Devices tested: HP ZBook 17 G4, Intel Xeon E3-1505M, 64GB RAM, Windows 10 Pro (fresh reset); Dell Latitude 5580, i7-7820HQ, 32GB RAM, Windows 11; HP 15-ac121dx, i3-5010U, 8GB RAM, Windows 10; HP 15-ac121dx, i3-5010U, 16GB RAM, Windows 10
* Dependencies: Aside from the downloading the prebuilt Windows binary and the model, the Microsoft Visual C++ Redistributable is required (https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170)
---
## Download and Set Up
1. On the computer, navigate to the user directory, C:\Users\\{username}. 
2. Inside the Home folder, create a new folder and name it “llama.cpp”. Create another new folder and name it “Models.”

    ![windows-llamacpp-create-folders-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/e8e8bb35-15fa-44da-a24d-aafa691e31ed)

    
3. Open a web browser and go to the following webpage: https://github.com/ggerganov/llama.cpp/releases
4. On the webpage, download the latest Windows binary for your computer. For the the HP ZBook, the avx2-x64 zip file was appropriate. The b2589 release was the latest version when I downloaded it.

    ![windows-llamacpp-download-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/f06285f4-f5a8-4966-b78a-c68c5148d5f1)


5. Extract the zip. Select all the files and move them into the newly created “llama.cpp” folder in the user directory.

   ![windows-llamacpp-move-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/467ec36b-5d28-4d56-aa91-074070c55a9c)


6. Go to the following webpage: https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.2-GGUF
7. Search for the Q4_K_M model and download it.

    ![windows-download-hf-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/f03ed6da-2cd3-43b8-b2b1-95a7791234e9)


8. Move the downloaded Q4_K_M model from the Downloads folder into the newly created “Models” folder in the user directory.

    
    ![windows-move-hf-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/45e6754d-e422-47cc-9fee-3398be60164b)


9. Click the Start button, then type cmd in the search bar. Click on the Command Prompt app in the results to launch it.
    

10. In the command prompt window, paste the following command and press the return key: `cd llama.cpp`
    
    ![windows-llamacpp-cd1-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/15026dde-cd8c-4f1e-a2f1-73e8d50f4d4f)


11. Next, paste the following command and press return: `.\server -m ../Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf`
    
     ![windows-llamacpp-cd2-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/c42e8811-3fcb-4a1a-b36b-60340cc9deac)


    1. If one of these errors appear, the Microsoft Visual C++ Redistributable needs to be installed (https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170)
       
        ![MSVCP140](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/2ae6f92f-7582-49c1-9a75-0ff3e20804a4)

        ![VCRUNTIME140_1](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/8f9e11af-cd94-4b8f-8256-47468f2a6bd1)



12. Wait a few seconds until the terminal window shows text that reads “all slots are idle”.

    
    ![windows-all-slots-idle-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/4210e9ad-ada5-4c4e-8096-f05fa3245e9e)


13. Open a web browser and enter this localhost address: http://127.0.0.1:8080. The page displays the interface for chatting with the model.
14. Type a message into the field at the bottom of the window. Click Send.

    ![windows-llamacpp-chat-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/48870514-326a-4475-9c4e-dbeccb0ff357)


15. To exit the chat, go back to the command prompt window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llama.cpp again in the future
The next time you want to run llama.cpp, just follow these steps:
1. Open the Command Prompt application.
2. In the command prompt window, paste the following command and press the return key: `cd llama.cpp` 
3. Next, paste the following command and press return: `.\server -m ../Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf`
4. Open a web browser and enter this localhost address: http://127.0.0.1:8080
5. To exit the chat, go back to the command prompt window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

# Running llamafile on Windows 10/11

---
**Things to Know**
* This guide details how to download and use llamafile with a 7B model on a Windows 10 or 11 computer with 16 GB RAM. (I do not know if laptops with only 8 GB RAM will be able to run the 7B model. You might need to download a smaller model such as Phi-2.)
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llamafile, they can be found at this website: https://github.com/Mozilla-Ocho/llamafile
* Devices tested: HP ZBook 17 G4, Intel Xeon E3-1505M, 64GB RAM, Windows 10 Pro (fresh reset) and Dell Latitude 5580, i7-7820HQ, 32GB RAM, Windows 11
* Dependencies: Aside from downloading the llamafile and the model, no extra installs are needed.
---
## Download and Set Up
1. On the computer, navigate to the user directory, C:\Users\\{username}. 
2. Inside the folder, create a new folder and name it “llamafile”. Create another new folder and name it “Models.”
   
   ![windows-lf-create-folders-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/eed1d03a-73fb-4bde-904f-6d520f8870ef)



3. Open a web browser and go to the following webpage: https://github.com/Mozilla-Ocho/llamafile/releases
4. Download the latest llamafile. The 0.7 release was the latest version when I downloaded it.
   
   ![windows-lf-download-lf-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/18201621-ecda-4c4e-9d1d-f168810b3c88)


5. Move the llamafile from the Downloads folder into the newly created “llamafile” folder in the user directory.
   
   ![windows-lf-move-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/32183844-2af2-4c8c-914c-e281bd7213ab)

6. Display the properties. Add ".exe" to the end of the filename. Click OK.

   ![windows-lf-type-exe-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/826181f3-8012-436b-944c-0547ba940d62)


7. Go to the following webpage: https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.2-GGUF
8. Search for the Q4_K_M model and download it.

    ![windows-download-hf-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/3a377720-62b8-4aa5-9a8e-7ed1f5d199a3)


9. Move the downloaded Q4_K_M model from the Downloads folder into the newly created “Models” folder in the user directory.

   ![windows-lf-move-hf-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/a67b23fe-f855-46dd-a912-801e59a16ec4)


10. Click the Start button, then type "cmd" in the search bar. Click on the Command Prompt app in the results to launch it.

11. In the command prompt window, paste the following command and press the Enter key: `cd llamafile`
    
    ![windows-lf-cd1-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/ae2a188c-720a-405e-9d60-ddf572f94637)



12. Next, paste the following command and press Enter: `llamafile-0.7 -m ../Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf`
    
    
    ![windows-lf-cd2-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/7b4b6692-44c9-466c-bb2a-d8cfc7ff6c4f)


13. Wait a few seconds. A web browser window will automatically open to this localhost address: http://127.0.0.1:8080.
14. Type a message into the field at the bottom of the window. Click Send.
    
    ![windows-lf-chat-20240408](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/03ff9581-a7b8-4cff-91ac-abaa11d3744e)


15. To exit the chat, go back to the command prompt window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llamafile again in the future
The next time you want to run llamafile, just follow these steps:
1. Launch the Command Prompt application.
2. In the Command Prompt window, paste the following command and press the Enter key: `cd llamafile` 
3. Next, paste the following command and press Enter: `llamafile-0.7 -m ../Models/mistral-7b-instruct-v0.2.Q4_K_M.gguf`
5. To exit the chat, go back to the Command Prompt window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

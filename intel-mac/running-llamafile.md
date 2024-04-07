# Running llamafile on an Intel Mac

---
**Things to Know**
* This guide details how to download and use llamafile with a 7B weight model on an Intel Mac.
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llamafile, they can be found at this website: https://github.com/Mozilla-Ocho/llamafile
* Device used: 2018 MacBook Pro, 2.3 GHZ Quad-Code Inter Core i5, 8GB RAM, macOS 14.3.1 (fresh install)
* Dependencies: Aside from downloading the llamafile, no extra installs are needed.
---
## Download and Set Up
1. On the Mac, open the Home folder by using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>H</kbd>. 
2. Inside the Home folder, create a new folder and name it “llamafile”.
   
    <img width="728" alt="Intel-Mac-lf-Create-Folder-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/a2fede48-9b18-4814-b69e-744bc9fb4a3e">

4. Open a web browser and go to the following webpage: https://huggingface.co/jartine/Mistral-7B-Instruct-v0.2-llamafile
5. Search for the Q4_K_M model and download it.
   
   <img width="583" alt="Intel-Mac-lf-HF-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/36b76a4e-9f1b-4dc5-a382-afe880a34ecc">

8. Move the downloaded Q4_K_M model from the Downloads folder into the newly created “llamafile” folder in the Home folder.
   
   <img width="730" alt="Intel-Mac-Move-File_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/effe6cf4-10dc-4e4c-aa03-b440023498dc">

10. Open the Spotlight search by using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Spacebar</kbd>.
10. Type “Terminal” and click it to launch the application.
    
    <img width="601" alt="Intel-Mac-Spotlight-Terminal-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/3e1a2061-efc7-4e11-834d-8e637ab81cb5">

12. In the Terminal window, paste the following command and press the return key: `cd llamafile`
    
    <img width="593" alt="Intel-Mac-lf-cd1_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/90d6bcb4-d48e-4a74-8fb1-579d071ecece">

14. Next, grant permissions to run the file. Paste the following command and press return: `chmod +x mistral-7b-instruct-v0.2.Q4_K_M.llamafile`
    
    <img width="593" alt="Intel-Mac-lf-cd2_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/9f2a5dec-eae9-47a1-952e-61790e01dae0">

12. Paste the following command and press return: `./mistral-7b-instruct-v0.2.Q4_K_M.llamafile`
    
    <img width="593" alt="Intel-Mac-lf-cd3_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/9aa5f09c-e0bb-42c2-bfc9-f10615cd3698">

14. Wait about 1 minute and a web browser window will automatically open this localhost address: http://127.0.0.1:8080.
15. Type a message into the field at the bottom of the window. Click Send.
    
    <img width="889" alt="Intel-Mac-lf-chat_20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/b57945b3-457b-4dfc-8b78-8006434e29dd">

16. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llamafile again in the future
The next time you want to run llamafile, just follow these steps:
1. Open the Terminal application.
2. In the Terminal window, paste the following command and press the return key: `cd llamafile` 
3. Next, paste the following command and press return: `./mistral-7b-instruct-v0.2.Q4_K_M.llamafile`
5. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

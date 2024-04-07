# Running llamafile on a Dell Intel Core i7 with Linux Mint

---
**Things to Know**
* This guide details how to download and use llamafile with a 7B weight model on an Intel i7 laptop.
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llamafile, they can be found at this website: https://github.com/Mozilla-Ocho/llamafile
* Device used: Dell Intel Core i7-7820 HQ CPU @2.9GHz x 4, 32GB RAM, Linux Mint 21.3 Cinnamon (fresh install)
* Dependencies: Aside from downloading the llamafile, no extra installs are needed.
---
## Download and Set Up
1. On the laptop, open the Home folder by using the keyboard shortcut <kbd>Super</kbd> + <kbd>E</kbd>. Alternatively, click on the Files icon in the lower left corner of the screen. 
2. Inside the Home folder, create a new folder and name it “llamafile”.
   
   ![linux-lf-create-folder-20240407](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/6e691528-1f61-4737-9153-3d24e99b1979)


3. Open a web browser and go to the following webpage: https://huggingface.co/jartine/Mistral-7B-Instruct-v0.2-llamafile
4. Search for the Q4_K_M model and download it.
   
   <img width="583" alt="Intel-Mac-lf-HF-20240407" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/36b76a4e-9f1b-4dc5-a382-afe880a34ecc">

5. Move the downloaded Q4_K_M model from the Downloads folder into the newly created “llamafile” folder in the Home folder.
   
   ![linux-lf-move-20240407](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/443cc6ed-b7e6-4d56-8b6c-f77d70e405f8)


6. Launch the Terminal application using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.

7. In the Terminal window, paste the following command and press the Enter key: `cd llamafile`
    
    ![linux-lf-cd1-20240407](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/44826b15-78d8-4da8-9f06-2cc9bdaccec6)


8. Next, paste the following command and press Enter: `./mistral-7b-instruct-v0.2.Q4_K_M.llamafile`
    
    ![linux-lf-cd2-20240407](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/592aa02c-b584-4b8f-a8e0-6c0dd284b0f2)


9. Wait a few seconds. A web browser window will automatically open to this localhost address: http://127.0.0.1:8080.
10. Type a message into the field at the bottom of the window. Click Send.
    
    ![linux-lf-chat-20240407](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/f7508cba-4420-402b-854f-9b4b5e8402fc)

11. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llamafile again in the future
The next time you want to run llamafile, just follow these steps:
1. Launch the Terminal application.
2. In the Terminal window, paste the following command and press the Enter key: `cd llamafile` 
3. Next, paste the following command and press Enter: `./mistral-7b-instruct-v0.2.Q4_K_M.llamafile`
5. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

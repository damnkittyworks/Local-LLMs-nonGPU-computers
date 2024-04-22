# Running the Llama 3 70B llamafile on a HP ZBook G4 (Xeon E3-1505M, 64GB RAM) with Linux Mint

---
**Things to Know**
* This guide details how to download and use the Llama 3 70B Q4_0 llamafile on a Xeon E3-1505M 64GB RAM laptop.
*   IMPORTANT: To run the Llama 70Bb llamafile, your computer must meet or exceed the minimum system requirements of a Xeon E3-1505M processor, 64GB RAM and equivalent spefifications.
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llamafile, they can be found at this website: https://github.com/Mozilla-Ocho/llamafile
* Device used: HP ZBook 17 G4, 3GHz Xeon E3-1505M, 64GB RAM, NVIDIA Quadro P5000 graphics card, Linux Mint 21.3 Cinnamon (fresh install)
* Dependencies: Aside from downloading the llamafile, you will need to install the NVIDIA driver and the CUDA toolkit. Links are below.
---
## Download and Set Up
1. On the laptop, open the Home folder by using the keyboard shortcut <kbd>Super</kbd> + <kbd>E</kbd>. Alternatively, click on the Files icon in the lower left corner of the screen. 
2. Inside the Home folder, create a new folder and name it “llamafile”.
   
   
    ![linux-L370B_create-folder](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/c4d507e3-c8b3-43dd-8bd5-cb620e979903)


3. Open a web browser and go to the following webpage: https://huggingface.co/jartine/Meta-Llama-3-70B-Instruct-llamafile/blob/main/Meta-Llama-3-70B-Instruct.Q4_0.llamafile
4. Search for the Q4_0 model and download it. (If your computer has better specs than mine, feel free to try other quants like 5Q or 8Q.)
   
   ![linux-L370B_download_llamafile](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/1451f55d-f553-4539-81f6-6863458a7b85)


5. Move the downloaded Q4_0 model from the Downloads folder into the newly created “llamafile” folder in the Home folder.
   
   
    ![move](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/3d4e9c28-944c-41b9-93ff-7a5184fc0550)


6. Launch the Terminal application using the keyboard shortcut <kbd>Cmd</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.

7. In the Terminal window, paste the following command and press the Enter key: `cd llamafile`
    
    ![linux-lf-cd1-20240407](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/44826b15-78d8-4da8-9f06-2cc9bdaccec6)


8. Next, paste the following command and press Enter: `./Meta-Llama-3-70B-Instruct.Q4_0.llamafile`
    
    ![linux-L370B_run-no-gpu](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/76e610fd-4afa-421e-bb74-b127a8ea21ae)


9. Wait a few seconds. A web browser window will automatically open to this localhost address: http://127.0.0.1:8080.
10. Type a message into the field at the bottom of the window. Click Send.
    
     ![linux-L370B_chat-window](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/548abfa7-9ffc-49f7-8550-7918f5321b80)


11. The speed for CPU only is slow. I'm getting around 0.6 tokens/second.

    ![linux-L370B_speed-no-gpu](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/d9684ed8-b025-4546-88be-40d066d3278a)

    
12. My laptop has an NVIDIA Quadro P5000 graphics card so I will use the GPU too. First, install the NVIDIA driver through the Linux Device Manager.

    ![linux-L370B_driver-manager-install](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/fd5494d3-ea7e-4b47-8f5f-4f5977e177c5)


13. Next, follow the instructions on this webpage to install the CUDA Toolkit. https://developer.nvidia.com/cuda-downloads

    ![linux-L370B_cuda-toolkit](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/d02e8826-9496-4e1c-87ee-c3b7b6c7dd25)


14. After restarting your computer, launch Terminal. Enter  `cd llamafile` , then enter `./Meta-Llama-3-70B-Instruct.Q4_0.llamafile -ngl 30`

    ![linux-L370B_run-cuda-30](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/735bbdd6-9fc1-480b-83d0-c2e8571e0714)

    The speed is a little bit faster using the "-ngl 30" parameter. 

      ![linux-L370B_speed-gpu](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/56278f33-1095-4c85-b5fe-0c73fb17d3ea)

    I tried "-ngl 35" but that resulted in an out of memory error.

      ![linux-L370B_run-cuda-35](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/8004a2c5-469e-44cf-a034-b9036774b6e2)

  
15. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

## Running llamafile again in the future
The next time you want to run llamafile, just follow these steps:
1. Launch the Terminal application.
2. In the Terminal window, paste the following command and press the Enter key: `cd llamafile` 
3. Next, paste the following command and press Enter: `.//Meta-Llama-3-70B-Instruct.Q4_0.llamafile -ngl 30`
5. To exit the chat, go back to the Terminal window and press <kbd>Ctrl</kbd> + <kbd>C</kbd>.

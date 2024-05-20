# Running llama.cpp on Android
---
**Things to Know**
* This guide details how to download and use llama.cpp with a 3B model on a Samsung S20 5G with 8 GB RAM.
* These instructions were written with simplicity in mind so anyone can follow along, even for those who are not tech whizzes. As such, the steps may not be the most advanced or optimized for tech experts.
* Original instructions: For those interested in exploring the original instructions provided by the creator of llama.cpp, they can be found at this webpage: https://github.com/ggerganov/llama.cpp?tab=readme-ov-file#build-on-android-using-termux
* Devices tested: Samsung S20 5G with 8 GB RAM on Android 12
* Dependencies: Termux, compilation dependencies( git, make, clang)
---
## Download and Set Up
1. On the smartphone, create a new folder and name it “Models.”

    ![Android_Termux_createFolder](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/40d29f63-5b03-4d50-b684-92b5c838c2e8)

    
2. Open a web browser and go to the to download Termux: https://f-droid.org/en/packages/com.termux/
3. On the webpage, download Termux APK versioon 0.118.0.

    
    <img width="617" alt="Android_Termux_downloadTermux" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/258ad11c-62d7-4433-a3ac-8b2d65b37c38">



4. Navigate to the Downloads folder, then click on the apk file to install it. Note: If your the phone displays a message that it isn’t allowed to install unknown apps, update the Settings to allow it. On my phone, I enabled installs from “My Files”. Once I Enabled it, a popup asked if I wanted to install Termux.

    ![Android_Termux_install_unknown_apps](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/cbbf9a4b-464d-4d71-8ca0-fa644896d2cb)


5. Launch Termux.
6. Enter `apt update && apt upgrade`. Enter Y and press Return when asked (you might need too do this a few times).


    ![Android_Termux_apt](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/aa02f0f1-7d96-48dd-b14a-fa65ea9f308d)



7. Enter `pkg install git && pkg install make && pkg install clang`. Press Y and Return when asked. You’ll be asked a couple of times.

    ![Android_Termux_installGit](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/0fc37b01-d7c5-46c3-b562-6e56777699e0)

   
8. Enter `git clone https://github.com/ggerganov/llama.cpp` and press return.

    ![Android_Termux_git_clone](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/e9b0eeb0-4ded-4206-a02b-d3b1383df4f3)


9. Enter `cd llama.cpp`.


    ![Android_Termux_cd_llama](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/b71838dc-a5ce-4db0-ad5b-4427043fb345)

10. Enter `make`. The build will take about 5 minutes.
   
    ![Android_Termux_make](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/9f5c97e7-38c7-4816-bbde-fd2ff9e424df)


11. Go to this webpage and download the Q8_0 file. https://huggingface.co/bartowski/Phi-3-mini-4k-instruct-GGUF/tree/main
   
    <img width="581" alt="Android_Termux_download_gguf" src="https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/b483617b-a85c-4749-9e15-110daec638ae">


12. Move the .gguff file to the Models folder created in step 1.


    ![Android_Termux_move_gguf](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/ba244173-f59c-419f-9bf5-5b40481ae383)



13. Allow Termux to access the Models folder. Open Settings, go to Apps, click on Termux. Under the Permissions, allow it to access Files and media.

    ![Android_Termux_allow_permissions](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/79002732-d865-4f36-abd0-f1af60615dc3)



14. Launch Termux. In the termnal window, paste the following command and press the return key: `cd llama.cpp`.

    ![Android_Termux_cd_llama](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/d5c0992d-11f1-4803-a78c-54935ced5934)

    
15. Next, paste the following command and press return: `./server -m /storage/emulated/0/models/Phi-3-mini-4k-instruct-Q8_0.gguf -t 3`
    

    ![Androd_Termux_server](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/160662e1-dcb4-4d79-b0ec-0117be88df29)



16. Wait a few seconds until the terminal window shows text that reads “all slots are idle”.

      ![Android_Termux_idle](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/9d73f881-56cc-4b85-b73d-362f3c939f3c)


17. Open a web browser and enter this localhost address: http://127.0.0.1:8080. The page displays the interface for chatting with the model.
18. Type a message into the field at the bottom of the window. Click Send.

    ![Android_Termux_browser](https://github.com/damnkittyworks/Local-LLMs-nonGPU-computers/assets/161262078/50c16d65-234f-4ae9-8807-eb8a2576bee0)


19. To exit the chat, go back to the Terminal window and enter Ctrl + C.

## Running llama.cpp again in the future
The next time you want to run llama.cpp, just follow these steps:
1. Launch the Termux application.
2. In the terminal window, paste the following command and press the return key: `cd llama.cpp` 
3. Next, paste the following command and press return: `./server -m /storage/emulated/0/models/Phi-3-mini-4k-instruct-Q8_0.gguf -t 3`
4. Open a web browser and enter this localhost address: http://127.0.0.1:8080
5. To exit the chat, go back to the Terminal window and press Ctrl + C.
